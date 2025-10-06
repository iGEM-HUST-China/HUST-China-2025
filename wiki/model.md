---
title: Model
permalink: /model/
feature_text: |
feature_image: "https://static.igem.wiki/teams/5569/description/modl.webp"
excerpt: ""
images02:
  - src: https://static.igem.wiki/teams/5569/model/m5.webp
    alt: Global HADDOCK score distribution (boxplot)
    caption: **Figure 4a.** Global HADDOCK score distribution across peptide–enzyme complexes (boxplot).
  - src: https://static.igem.wiki/teams/5569/model/m4.webp
    alt: Enzyme-wise HADDOCK score comparison (barplot)
    caption: **Figure 4b.** Enzyme-wise HADDOCK score comparison across target enzymes (barplot). 
---

## Our Model

Engineering peroxisomal protein targeting and rewiring central carbon metabolism in *Yarrowia lipolytica* poses a formidable design challenge: the import efficiency of linker–signal peptides, the catalytic bottleneck imposed by pathway rate-limiting enzymes, and the nonlinear dynamics of growth under complex carbon sources are deeply intertwined. Trial-and-error approaches alone cannot efficiently resolve this multi-layered problem.

To bridge this gap, we established a **hierarchical in silico pipeline** that acts as a digital twin of our PICasSO-inspired engineering strategy, enabling rational design and predictive prototyping.

### Molecular Layer — Peptide–Enzyme Docking

At the molecular interface, we employed **HADDOCK-based peptide–enzyme docking** to interrogate the binding determinants of classical and extended PTS1 variants (*SKL*, *GGGSSKL*, *TYWIRFSKL*). These simulations uncovered the energetic and structural principles that govern efficient recognition by **PEX5** and defined rational rules for designing import signals.

### Enzyme Layer — AI-Guided Sequence Redesign

To relieve metabolic bottlenecks, we targeted the **rate-limiting enzyme of the MVA pathway**. Using **ProteinMPNN**, we performed *de novo* sequence redesign to generate optimized variants, followed by **Rosetta FastRelax** refinement to minimize conformational strain energy. This computational protein engineering strategy yielded enzyme variants with enhanced stability and binding properties, thereby providing a robust starting point for experimental implementation.

### Systems Layer — Machine Learning Growth Modeling

To connect molecular insights with systems-level behavior, we constructed a **machine learning–driven growth modeling framework**. Experimental OD₆₀₀ kinetics were first parameterized using **Gompertz** and **spline** fits, extracting μₘₐₓ, λ, and K. These kinetic features, combined with medium composition variables, were used to train **Random Forest** and **XGBoost** models capable of forecasting growth performance under novel carbon-source combinations. This predictive capacity enables extrapolation beyond measured conditions and provides a quantitative basis for rational medium optimization.

### Integration and Impact

By fusing **molecular docking**, **AI-guided enzyme redesign**, and **machine learning–based systems modeling** into a unified framework, our model enables *in silico* prototyping of peroxisomal targeting and metabolic rewiring. This **model-driven strategy** transforms the traditional **Design–Build–Test–Learn (DBTL)** cycle into a **predictive, knowledge-**
## PART 1 · Our Model Overview

**One-sentence summary:** We built a digital-twin pipeline for our project.

- **Docking** identifies efficient linker–signal peptide combinations for peroxisomal import.
- **AI-driven redesign** of the MVA pathway’s rate-limiting enzyme yields more stable and more active variants.
- **Machine learning** predicts growth performance under new carbon sources.


## PART 2 · Linker–Signal Peptide System Docking

- Simulated interactions of *SKL*, *GGGSSKL*, and *TYWIRFSKL* with MVA-pathway enzymes using **HADDOCK**.
- Identified the **structural** and **energetic** principles governing efficient **PEX5**-mediated import.
- Generated **docking clusters** to guide selection of linker–signal peptide combinations.


## PART 3 · Computational Enzyme Engineering

- Focused on the **MVA pathway’s rate-limiting enzyme** as the metabolic bottleneck.
- Applied **ProteinMPNN** for amino-acid sequence redesign; selected the sequence with the **lowest frustration energy** using **Frustratometer2**.
- Refined conformations with **Rosetta FastRelax** to obtain stable, high-activity variants.


## PART 4 · Machine Learning Growth Modeling

- Collected **OD₆₀₀** growth data under multiple culture conditions.
- Extracted kinetic parameters (**μₘₐₓ**, **λ**, **K**) via **Gompertz** and **spline** fits.
- Trained **Random Forest** and **XGBoost** models to predict growth under novel carbon-source conditions.

{% include figure.html image="https://static.igem.wiki/teams/5569/model/m02.webp" caption="Figure1. MODEL PEPLINE" %}

# I. Linker–Signal Peptide System Docking

**Signal-peptide & linker selection · Molecular docking · Energy analysis**

## Background & Rationale

Peroxisomal protein import relies on **peroxisomal targeting signals (PTS)** and their cytosolic receptors.  
Two major types exist: **PTS1**, a canonical C-terminal tripeptide such as –SKL, and **PTS2**, a nonapeptide motif near the N-terminus.  
Among these, **PTS1** is the most conserved and widely used signal across eukaryotes.

The cytosolic receptor **PEX5** specifically recognizes PTS1-containing proteins, forming a transient **receptor–cargo complex**.  
This complex docks at the peroxisomal membrane through interactions with **PEX13** and **PEX14**, which together constitute the import machinery.  
After cargo translocation, **PEX5** is recycled to the cytosol for subsequent transport cycles.

To engineer efficient peroxisomal targeting in *Yarrowia lipolytica*, we incorporated the classical **PTS1 (–SKL)** signal at the C-terminus of peptides.  
Beyond the minimal SKL motif, we designed two extended variants—**GGGSSKL** and **TYWIRFSKL**—to systematically evaluate how linker length and composition affect **PEX5** recognition.  
The design rationale was that a **flexible linker (GGGS)** could increase accessibility of the SKL motif, while an **aromatic-rich segment (TYWIRF)** might provide additional stabilizing interactions.

These three peptide designs were fused to the eight key enzymes of the **MVA pathway** (*Erg8, Erg9, Erg10, Erg13, Erg20, Hmgr, Idi,* and *Merg12*), providing the foundation for subsequent molecular docking analysis.

 *An animation illustrates this process: enzyme–SKL forms a complex with PEX5, which then docks with PEX14 and PEX13; IDRs of PEX13 undergo liquid–liquid phase separation to generate a transient liquid cavity that facilitates import.*

<!-- ========================================================= -->
<!-- ✅ MathJax Configuration for Centered Equations -->
<!-- ========================================================= -->
<script>
window.MathJax = {
  tex: {
    inlineMath: [['$', '$'], ['\\(', '\\)']],
    displayMath: [['$$', '$$'], ['\\[', '\\]']]
  },
  svg: {
    fontCache: 'global',
    displayAlign: 'center',   // ✅ Center equations
    displayIndent: '0em'
  },
  chtml: {
    displayAlign: 'center',   // ✅ also ensures center alignment in HTML mode
    displayIndent: '0em'
  }
};
</script>
<script async src="https://cdn.jsdelivr.net/npm/mathjax@3/es5/tex-svg.js"></script>


# II. Molecular Docking

## Energy Terms and Scoring Principles

The HADDOCK docking protocol is fundamentally a physics-based and restraint-driven platform. It evaluates docking poses by combining several key energy terms:

- **van der Waals interactions**: Describing repulsion and attraction between atoms, preventing steric clashes while capturing hydrophobic stabilization.  

<div style="display:flex; justify-content:center;">

$$
E_{\text{vdW}} = \sum_{i<j} \varepsilon_{ij} \!\left[ \left( \frac{r_{\min,ij}}{r_{ij}} \right)^{12} - 2 \left( \frac{r_{\min,ij}}{r_{ij}} \right)^6 \right]
$$

</div>

- **Electrostatics**: Coulombic interactions between charged residues, essential for PEX5 recognition of signal peptides.  

<div style="display:flex; justify-content:center;">

$$
E_{\text{elec}} = \sum_{i<j} \frac{k_e\,q_i q_j}{\varepsilon(r_{ij})\,r_{ij}}, \quad k_e \approx 332\ \text{kcal·Å·mol}^{-1}\text{·e}^{-2}
$$

</div>

- **Desolvation energy**: Reflecting the free-energy change of amino acid residues when buried at the interface. Hydrophobic burial is favorable, while polar residues require compensating hydrogen bonds or salt bridges.  

<div style="display:flex; justify-content:center;">

$$
E_{\text{desolv}} = \sum_{i,j} S_i V_j \exp\left(-\frac{r_{ij}^2}{2\sigma^2}\right)
$$

</div>

- **Ambiguous Interaction Restraints (AIRs)**: Experimentally derived or hypothesized distance restraints that bias docking toward biologically relevant solutions.  

<div style="display:flex; justify-content:center;">

$$
E_{\text{air}} = \sum_k W_k \big(\langle d_k^{-6}\rangle^{-1/6} - d_{0,k}\big)^2
$$

</div>

At different docking stages (rigid body, semi-flexible refinement, water refinement), these energy terms are combined with varying weights into the final HADDOCK score. Additionally, **Buried Surface Area (BSA)** is used to quantify the size and compactness of the interface.  

<div style="display:flex; justify-content:center;">

$$
\text{Score} = w_{\text{vdW}} E_{\text{vdW}} + w_{\text{elec}} E_{\text{elec}} + w_{\text{desolv}} E_{\text{desolv}} + w_{\text{air}} E_{\text{air}}
$$

</div>

*(Optional reporting term: − 0.01 × BSA may be included to account for interface compactness.)*

Thus, HADDOCK scoring integrates both atomic-level physical interactions and experimental restraints, rather than relying on geometry alone.


## Structure Preparation

To systematically investigate peroxisomal targeting, we collected structural information for the eight key enzymes of the *Yarrowia lipolytica* MVA pathway (*Erg8, Erg9, Erg10, Erg13, Erg20, Hmgr, Idi, Merg12*). Experimental structures were retrieved from the PDB database, and missing structures were completed by homology modeling.  

We designed three C-terminal signal peptide tags: the canonical SKL motif, the flexible extended GGGSSKL, and the aromatic-rich TYWIRFSKL. These tags were fused to the eight enzymes, and complete inputs were generated with AlphaFold predictions.


## Docking Workflow

Docking simulations were performed with HADDOCK 2.4 for PEX5 against each enzyme–peptide fusion. In total, 24 independent jobs (3 peptides × 8 enzymes) were executed. Each job produced ~300 poses at the rigid-body stage (it0), yielding ~14,400 initial poses overall. After semi-flexible refinement (it1) and water refinement, 2,880 water-refined models were retained, consistent with the typical ~1:5 (it1:it0) selection ratio.  

Clustering by interface RMSD reduced the dataset to ~192 representative complexes. Based on HADDOCK scores, buried surface area (BSA), and conformational diversity, 24 best-performing complexes were selected for downstream energy analysis and visualization.


## Definition of Active Residues

To focus docking on biologically relevant regions, active residues were explicitly defined. For PEX5, the TPR repeat hot-spot residues (364, 398, 438, 469, 476, 501, 507, 585) were selected. For the MVA enzymes, the C-terminal linker + SKL regions were defined as active sites, reproducing the natural recognition of PTS1 signals by PEX5.


## Scoring and Visualization

Docking results were evaluated with the HADDOCK scoring function, which integrates van der Waals, electrostatics, desolvation, and restraint energies, combined with BSA to quantify interface size (Figure 1).  

Representative complexes were visualized in PyMOL and ChimeraX to illustrate hydrogen-bond networks and structural overlays. The results confirmed the plausibility of docking poses and highlighted distinct recognition patterns between the minimal and extended signal peptides at the PEX5 interface.


{% include figure.html image="https://static.igem.wiki/teams/5569/model/m1.webp" caption="Figure3. Molecular_docking" %}

# III. Energy Analysis

To comprehensively evaluate docking outcomes, we analyzed both global scores and underlying energetic contributions.

Boxplot comparisons across all peptide–enzyme complexes revealed a clear hierarchy: the extended **TYWIRFSKL** consistently achieved the most favorable HADDOCK scores, the canonical **SKL** reproducibly ranked lowest, and **GGGSSKL** showed intermediate values. This ordering was robust across replicates and reflected a systematic advantage for the aromatic-rich extension.

When HADDOCK scores were resolved for each enzyme partner (barplot analysis), the same pattern emerged: **TYWIRFSKL** outperformed **SKL** in nearly every case, often with large margins, whereas **GGGSSKL** tracked between the two. These results demonstrate that the effect is not restricted to a single target but represents a general enhancement of binding across the enzyme panel.

{% include figure2.html images=page.images02 %}


We next examined the energetic basis for these differences. Donut plots visualizing HADDOCK scoring weights highlighted distinct stabilization mechanisms. For **TYWIRFSKL**, improved binding arose primarily from enhanced electrostatics and van der Waals packing, which favor tighter and more specific interfaces. By contrast, **SKL** complexes relied disproportionately on desolvation contributions, reflecting weaker direct interactions and more solvent-mediated stabilization. **GGGSSKL** again showed an intermediate profile, suggesting that the flexible linker partially compensates but cannot substitute for the aromatic contacts.

{% include figure.html image="https://static.igem.wiki/teams/5569/model/m3.webp" caption="**Figure 5.** Energetic decomposition showing relative contributions of electrostatics, vdW, and desolvation terms (donut plots)." %}

Finally, we integrated all docking metrics—including **HADDOCK score**, **vdW**, **electrostatics**, **desolvation**, **buried surface area (BSA)**, and **Z-score**—into a standardized heatmap to compare complexes on a unified scale. To enable cross-metric comparison, terms where “lower is better” were inverted, and each column was z-score normalized. This approach eliminated differences in physical units and revealed the relative performance landscape.

<div style="display:flex; justify-content:center;">

$$
Z = \frac{x - \mu}{\sigma}
$$

</div>

{% include figure.html image="https://static.igem.wiki/teams/5569/model/m2.webp" caption="**Figure 6.** Standardized heatmap of HADDOCK-derived energetic and interfacial metrics." %}

In this analysis, **TYWIRFSKL** complexes consistently clustered toward favorable energetic and interfacial signatures, with larger BSA and stronger vdW/electrostatics contributions. In contrast, **SKL** complexes grouped together at the unfavorable end of the spectrum, with lower BSA and weaker interactions.

Together, these multi-layered analyses converge on the conclusion that aromatic extension of the **SKL** motif enhances recognition, increases buried surface area, and stabilizes peptide–enzyme interactions through stronger packing and electrostatics, providing a mechanistic rationale for its superior docking performance.

# IV. Limitations and Future Perspectives

Despite providing valuable insights into peptide–enzyme recognition, this study has several limitations.  

First, HADDOCK predictions are highly dependent on the quality of input structures.  
Homology-modeled enzymes and AlphaFold-predicted peptide fusions may carry local inaccuracies, and the definition of active residues remains partly subjective—both factors potentially bias docking outcomes and cluster rankings.  

Second, docking represents molecular interactions in a static framework.  
Conformational flexibility, induced-fit effects, and large-scale domain motions prevalent in the cellular environment cannot be fully captured.  
Moreover, macromolecular crowding, ionic strength, and post-translational modifications—critical determinants of peroxisomal import—were not considered in the present computational setup.  

Third, the HADDOCK scoring function is based on empirical weighting.  
While the composite score provides a useful trend indicator, it may not accurately reflect the true energetic balance under physiological conditions.  
The dominance of electrostatic and van der Waals contributions observed here warrants validation through more rigorous, force-field–based simulations.  

Finally, the functional relevance of docking preferences remains to be experimentally verified.  
In vitro binding assays and in vivo peroxisomal import experiments will be required to confirm whether the enhanced affinity of **TYWIRFSKL** indeed translates into improved targeting efficiency.  

Future work will address these limitations by:  
- refining top-performing complexes with long-timescale molecular dynamics simulations under near-physiological conditions;  
- incorporating explicit solvent and macromolecular crowding models to capture cellular complexity;  
- coupling computational predictions with biochemical and cellular assays to validate binding preferences and import outcomes.  


## References

1. Gould SJ, Keller GA, Hosken N, Wilkinson J, Subramani S. *A conserved tripeptide sorts proteins to peroxisomes.* **J Cell Biol.** 1989;108(5):1657–1664.  
2. Brocard C, Hartig A. *Peroxisome targeting signal 1: Is it really a simple tripeptide?* **Biochim Biophys Acta.** 2006;1763(12):1565–1573.  
3. Lametschwandtner G, Brocard C, Fransen M, Van Veldhoven PP, Berger J, Hartig A. *The difference in recognition of PTS1 and PTS2 signals is conserved between yeast and mammals.* **EMBO J.** 1998;17(21):5948–5958.  
4. Neuberger G, Maurer-Stroh S, Eisenhaber B, Hartig A, Eisenhaber F. *Prediction of peroxisomal targeting signal 1–containing proteins from amino acid sequence.* **J Mol Biol.** 2003;328(3):581–592.  
5. Dominguez C, Boelens R, Bonvin AMJJ. *HADDOCK: A protein–protein docking approach based on biochemical or biophysical information.* **J Am Chem Soc.** 2003;125(7):1731–1737.  
6. van Zundert GCP, Rodrigues JPG, Trellet M, Schmitz C, Kastritis PL, Karaca E, *et al.* *The HADDOCK2.4 web server: user-friendly integrative modeling of biomolecular complexes.* **J Mol Biol.** 2016;428(4):720–725.  
7. Rodrigues JPG, Trellet M, Schmitz C, Kastritis PL, Karaca E, Melquiond ASJ, Bonvin AMJJ. *Clustering biomolecular complexes by residue contacts similarity.* **Proteins.** 2012;80(7):1810–1817.  
8. van Zundert GCP, Bonvin AMJJ. *Modeling protein–protein complexes using the HADDOCK webserver.* **Methods Mol Biol.** 2014;1137:163–179.  





