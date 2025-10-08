---
title: Model
permalink: /model/
feature_text: |
feature_image: "https://static.igem.wiki/teams/5569/description/modl.webp"
excerpt: ""
images02:
  - src: https://static.igem.wiki/teams/5569/model/m5.webp
    alt: Global HADDOCK score distribution (boxplot)
    caption: Figure 4a. Global HADDOCK score distribution across peptide–enzyme complexes (boxplot).
  - src: https://static.igem.wiki/teams/5569/model/m4.webp
    alt: Enzyme-wise HADDOCK score comparison (barplot)
    caption: Figure 4b. Enzyme-wise HADDOCK score comparison across target enzymes (barplot). 
---

## Our Model TriScale

Engineering peroxisomal protein targeting and rewiring central carbon metabolism in *Yarrowia lipolytica* poses a formidable design challenge: the import efficiency of linker–signal peptides, the catalytic bottleneck imposed by pathway rate-limiting enzymes, and the nonlinear dynamics of growth under complex carbon sources are deeply intertwined. Trial-and-error approaches alone cannot efficiently resolve this multi-layered problem.

To bridge this gap, we established a **hierarchical in silico pipeline** that acts as a digital twin of our PICasSO-inspired engineering strategy, enabling rational design and predictive prototyping.



#### Integration and Impact
<br>
By fusing **molecular docking**, **AI-guided enzyme redesign**, and **machine learning–based systems modeling** into a unified framework, our model enables *in silico* prototyping of peroxisomal targeting and metabolic rewiring. This **model-driven strategy** transforms the traditional **Design–Build–Test–Learn (DBTL)** cycle into a predictive, knowledge-guided process, substantially reducing experimental overhead while accelerating the path toward high-yield, industrially robust strains.



## PART 1 · Linker–Signal Peptide System Docking

- Simulated interactions of *SKL*, *GGGSSKL*, and *TYWIRFSKL* with MVA-pathway enzymes using **HADDOCK**.
- Identified the **structural** and **energetic** principles governing efficient **PEX5**-mediated import.
- Generated **docking clusters** to guide selection of linker–signal peptide combinations.


## PART 2 · Computational Enzyme Engineering

- Focused on the **MVA pathway’s rate-limiting enzyme** as the metabolic bottleneck.
- Applied **ProteinMPNN** for amino-acid sequence redesign; selected the sequence with the **lowest frustration energy** using **Frustratometer2**.
- Refined conformations with **Rosetta FastRelax** to obtain stable, high-activity variants.


## PART 3 · Machine Learning Growth Modeling

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
<script async src="https://gitlab.igem.org/2025/hust-china/-/tree/main/wiki/static/model/js/tex-svg.js"></script>


# 1.1 Molecular Docking

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

# 1.2 Energy Analysis

To comprehensively evaluate docking outcomes, we analyzed both global scores and underlying energetic contributions.

Boxplot comparisons across all peptide–enzyme complexes revealed a clear hierarchy: the extended **TYWIRFSKL** consistently achieved the most favorable HADDOCK scores, the canonical **SKL** reproducibly ranked lowest, and **GGGSSKL** showed intermediate values. This ordering was robust across replicates and reflected a systematic advantage for the aromatic-rich extension.

When HADDOCK scores were resolved for each enzyme partner (barplot analysis), the same pattern emerged: **TYWIRFSKL** outperformed **SKL** in nearly every case, often with large margins, whereas **GGGSSKL** tracked between the two. These results demonstrate that the effect is not restricted to a single target but represents a general enhancement of binding across the enzyme panel.

{% include figure2.html images=page.images02 %}


We next examined the energetic basis for these differences. Donut plots visualizing HADDOCK scoring weights highlighted distinct stabilization mechanisms. For **TYWIRFSKL**, improved binding arose primarily from enhanced electrostatics and van der Waals packing, which favor tighter and more specific interfaces. By contrast, **SKL** complexes relied disproportionately on desolvation contributions, reflecting weaker direct interactions and more solvent-mediated stabilization. **GGGSSKL** again showed an intermediate profile, suggesting that the flexible linker partially compensates but cannot substitute for the aromatic contacts.

{% include figure.html image="https://static.igem.wiki/teams/5569/model/m3.webp" caption="Figure 5. Energetic decomposition showing relative contributions of electrostatics, vdW, and desolvation terms (donut plots)." %}

Finally, we integrated all docking metrics—including **HADDOCK score**, **vdW**, **electrostatics**, **desolvation**, **buried surface area (BSA)**, and **Z-score**—into a standardized heatmap to compare complexes on a unified scale. To enable cross-metric comparison, terms where “lower is better” were inverted, and each column was z-score normalized. This approach eliminated differences in physical units and revealed the relative performance landscape.

<div style="display:flex; justify-content:center;">

$$
Z = \frac{x - \mu}{\sigma}
$$

</div>

{% include figure.html image="https://static.igem.wiki/teams/5569/model/m2.webp" caption="Figure 6. Standardized heatmap of HADDOCK-derived energetic and interfacial metrics." %}

In this analysis, **TYWIRFSKL** complexes consistently clustered toward favorable energetic and interfacial signatures, with larger BSA and stronger vdW/electrostatics contributions. In contrast, **SKL** complexes grouped together at the unfavorable end of the spectrum, with lower BSA and weaker interactions.

Together, these multi-layered analyses converge on the conclusion that aromatic extension of the **SKL** motif enhances recognition, increases buried surface area, and stabilizes peptide–enzyme interactions through stronger packing and electrostatics, providing a mechanistic rationale for its superior docking performance.

# 1.3 Limitations and Future Perspectives

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



# II. Protein Design and Optimization

## 2.1 Background

3-Hydroxy-3-methylglutaryl-CoA reductase (HMGR) is the rate-limiting enzyme of the mevalonate (MVA) pathway, catalyzing the reduction of HMG-CoA to mevalonate — a crucial control point for isoprenoid, sterol, and lipid biosynthesis. The structural stability and catalytic efficiency of HMGR therefore exert a decisive influence on downstream metabolic flux and product accumulation.  

In *Yarrowia lipolytica*, HMGR is a membrane-associated enzyme composed of an N-terminal transmembrane and sterol-binding domain and a C-terminal cytosolic catalytic domain. Because full-length HMGR is difficult to express and fold in heterologous systems, we employed a truncated soluble variant (tHMGR) that lacks the sterol-binding and transmembrane regions but retains the core catalytic domain. This truncation preserves enzymatic activity while significantly improving solubility and expression stability.  

To enhance thermodynamic stability without compromising catalytic function, we developed a structure-guided protein design framework integrating ProteinMPNN, Frustratometer2, and Rosetta FastRelax, enabling systematic sequence exploration and energy refinement of tHMGR — laying a computational foundation for rational enzyme optimization in the MVA pathway.  


## 2.2 Theoretical Principles

### (1) ProteinMPNN

ProteinMPNN is a graph-based sequence design model built upon message passing neural networks (MPNNs).  
The protein backbone is represented as a residue graph, where nodes correspond to residues and edges encode geometric relationships.  
By iteratively passing messages between nodes, the model learns spatial dependencies that govern residue identity.  

Trained on large-scale protein structure–sequence datasets, ProteinMPNN can rapidly sample diverse and stable sequences conditioned on a fixed backbone, efficiently balancing sequence diversity and thermodynamic stability.  


### (2) Frustratometer2

Frustratometer2 quantitatively characterizes the frustration of a protein’s energy landscape — a measure of energetic conflict among local interactions.  
Using molecular mechanics potentials and perturbation analysis, it classifies interactions as minimally, neutral, or highly frustrated, thereby evaluating both local and global energetic smoothness.  

Reducing local frustration typically enhances folding cooperativity and thermodynamic stability.  


### (3) Rosetta FastRelax

Rosetta FastRelax is an all-atom refinement protocol within the Rosetta suite.  
By iteratively minimizing energy and repacking side-chains while maintaining the global fold, it eliminates steric clashes and achieves energetically favorable conformations.  

FastRelax is typically employed as a post-design refinement step to further optimize candidate structures, ensuring physical plausibility and thermodynamic robustness.  

## 2.3 Design Workflow

To systematically explore the sequence landscape of tHMGR, we established a three-step design–optimization workflow (Figure 2-1):  

1 **Sequence Sampling:**  
ProteinMPNN generates approximately 100 candidate sequences conditioned on the tHMGR backbone.  

2 **Energy Evaluation:**  
Each sequence is analyzed using Frustratometer2 to quantify local and global frustration, selecting those with smooth energy landscapes.  

3 **Structure Relaxation:**  
Selected candidates are refined by Rosetta FastRelax to remove steric conflicts and minimize total energy at the atomic level.  

This pipeline enables iterative coupling of generative modeling and physics-based refinement, ensuring both sequence diversity and structural stability in tHMGR design.  

{% include figure.html image="https://static.igem.wiki/teams/5569/model/m6-2.webp" caption=" Figure 7. Integrated pipeline for sequence design and energy optimization of tHMGR." %}

## 2.4 Results and Validation

The workflow successfully generated a set of structurally compatible and energetically optimized tHMGR variants.  
All ProteinMPNN-designed sequences aligned well with the target backbone, confirming the feasibility of conditional sequence generation.  

Frustratometer2 analysis revealed that several designed variants exhibited a slight reduction (~2%) in highly frustrated regions and a corresponding increase in minimally frustrated contacts compared with the wild-type template.  

After Rosetta FastRelax refinement, the total energy decreased by approximately 15–25%, and the local energy landscape in the core folding regions became smoother (Figure 2-3).  
During the relaxation process, the backbone RMSD gradually converged from 14.52 Å to 1.34 Å (calculated over 2796 atoms).  
The RMSD values for the five relaxation cycles were 14.52, 5.10, 2.75, 2.08, and 1.67 Å respectively (Figure 2-4), illustrating the progressive elimination of energetic strain through iterative minimization and side-chain repacking.  

The final RMSD of ~1.3 Å indicates that structural refinement mainly affected local regions—particularly side chains and flexible loops—while maintaining the global fold.  
In the interactive NGLView visualization, the pre-relaxation model (grey) and post-relaxation model (cyan) clearly demonstrate local rearrangements and reduced steric clashes, confirming the effectiveness of the FastRelax refinement.  

Top-ranked variants were subsequently selected for experimental validation of folding stability and catalytic activity.  

<div class="video">
<iframe title="HUST-China: Alignment of t-HMGR before and after optimization (2025)" width="460" height="215" src="https://video.igem.org/videos/embed/joCRDYNNTRjtMv2kHZpHLe" allow="fullscreen" sandbox="allow-same-origin allow-scripts allow-popups allow-forms" style="border: 0px;"></iframe>
</div>

###  t-HMGR Structure Alignment (Interactive Viewer)

<iframe
  src="https://static.igem.wiki/teams/5569/model/t-HMGR_alignment_blue_gray.html"
  width="100%"
  height="600"
  style="border:none; border-radius:8px; box-shadow:0 0 10px rgba(0,0,0,0.1);">
</iframe>




## 2.5 Biological Interpretation

From an energy-landscape perspective, the reduction of frustration indicates fewer energetic barriers along the folding pathway, resulting in a smoother folding funnel and more stable energy minima.  
During the design process, the core catalytic region of tHMGR was deliberately preserved; all mutations were restricted to peripheral or non-conserved sites to maintain the geometry of catalytic residues and cofactor-binding motifs.  
This rational constraint ensured that structural optimization did not compromise enzymatic activity, achieving a balance between stability enhancement and functional retention.  
Interestingly, several low-frustration regions were located near the catalytic pocket, suggesting that local stabilization may further fine-tune the catalytic microenvironment and improve functional efficiency.  


## 2.6 Limitations and Future Work

Although the integrated framework performed effectively for rational optimization of tHMGR, several limitations remain.  
First, ProteinMPNN operates on static backbones and does not capture conformational flexibility.  
Second, Frustratometer2 relies on classical potentials lacking quantum and solvent effects.  
Third, FastRelax focuses on energy minimization without explicitly constraining catalytic kinetics.  

Future extensions include:  
1 Incorporating molecular dynamics simulations to represent conformational dynamics;  
2 Developing multi-objective optimization strategies to balance thermodynamic stability and catalytic activity;  
3 Integrating experimental feedback loops to achieve closed-cycle computational–experimental co-design.  



# III. Machine Learning Growth Modeling

## Background

Understanding the quantitative relationship between environmental factors and microbial growth dynamics is essential for optimizing bioprocesses and designing predictive cultivation strategies.  
In this study, *Yarrowia lipolytica* was chosen as a model organism owing to its exceptional environmental tolerance and remarkable lipid-producing capacity, making it a versatile chassis for metabolic engineering.  

Traditionally, microbial growth is described using the four-parameter Gompertz equation, which captures the characteristic sigmoidal trajectory of a batch culture.  
Its parameters—initial biomass (A), carrying capacity (K), maximum specific growth rate (μₘₐₓ), and lag-phase duration (λ)—offer direct physiological interpretation, reflecting cell density, growth potential, metabolic activity, and adaptation time, respectively.  

However, this classical fitting approach is inherently phenomenological and condition-specific: each growth curve is fitted independently under a fixed environment, and the obtained parameters cannot be generalized to new combinations of pH or temperature.  
To overcome this limitation, we established a hybrid modelling framework that integrates mechanistic growth equations with machine-learning regression, enabling the model to learn the mapping between culture conditions (pH, T) and Gompertz parameters.  

This combined approach allows not only quantitative prediction of unseen conditions but also rational optimization of environmental variables—bridging the gap between empirical growth curves and data-driven bioprocess design.  

## 3.2 Data Acquisition

To construct a comprehensive dataset linking environmental variables to growth behavior, we continuously monitored OD₆₀₀ of *Yarrowia lipolytica* cultivated under systematically varied conditions.  
Each culture was measured in triplicate across eleven time points spanning 0–80 h. At every time point, OD₆₀₀ was recorded both before and after centrifugation, and the difference was taken as the effective OD, thereby eliminating background interference from medium turbidity and yielding cleaner growth profiles.  

The experimental design combined two environmental factors—pH and temperature—with twelve distinct carbon sources, including oleic acid, glycerol, and recycled cooking oil.  
Sixteen pH–temperature combinations were tested in total: twelve evenly spaced factorial conditions for model training and four intermediate, non-equidistant points for testing generalization to unseen environments.  

Altogether, the dataset contained approximately 6,000 high-resolution measurements, providing a robust quantitative foundation for Gompertz parameter fitting and machine-learning regression.  

## 3.3 Modelling and Prediction

To transform the experimental OD₆₀₀ trajectories into interpretable kinetic descriptors, we first applied the Gompertz equation to fit all growth curves using non-linear least squares  

{% include figure.html image="https://static.igem.wiki/teams/5569/model/m7.webp" caption=" Figure 7. Gompertz model fitting of Y. lipolytica growth under varied carbon-source conditions." %}

This classical model captures the sigmoidal microbial growth pattern and provides four biologically meaningful parameters: the initial biomass (A), the carrying capacity (K), the maximum specific growth rate (μₘₐₓ), and the lag-phase duration (λ). 

<div style="display:flex; justify-content:center; margin-top:1em; margin-bottom:1em;">

$$
y(t) = A + (K - A) \cdot \exp\left[-\exp\left(\frac{\mu_{\max} \cdot e}{K - A}(\lambda - t) + 1\right)\right]
$$

</div>


Each fit produced smooth trajectories and 95 % confidence intervals, providing robust parameter estimates.  

{% include figure.html image="https://static.igem.wiki/teams/5569/model/m8.webp" caption=" Figure 7. Gompertz model fitting with 95% confidence intervals across multiple carbon sources." %}

The fitted parameters were then reformulated as a multi-output regression task, with environmental conditions (pH, temperature, substrate) serving as inputs and the Gompertz parameter vector as outputs.  
Model training minimized the L2 loss function , ensuring consistency between predicted and fitted parameters.  

<div style="display:flex; justify-content:center; margin-top:1em; margin-bottom:1em;">

$$
E_{\text{HADDOCK}} = w_{\text{vdw}}E_{\text{vdw}} + w_{\text{elec}}E_{\text{elec}} + w_{\text{desolv}}E_{\text{desolv}} + w_{\text{AIR}}E_{\text{AIR}}
$$

</div>


For decision-tree models, node splits were determined by maximizing variance reduction (Figure 3-4).  
Two ensemble-tree algorithms were benchmarked:  

<div style="display:flex; justify-content:center; margin-top:1em; margin-bottom:1em;">

$$
E_{\text{desolv}} = \sum_{i,j} S_i S_j \exp(-r_{ij}^2 / 2\sigma^2)
$$

</div>


- **Random Forest** — aggregates multiple decision trees through a bagging strategy to reduce variance and improve robustness;  
- **XGBoost** — applies boosting to iteratively fit residuals while optimizing a regularized objective . The regularization term penalizes overly complex tree structures and large weights, thereby enhancing generalization.  

<div style="display:flex; justify-content:center; margin-top:1em; margin-bottom:1em;">

$$
E_{\text{air}} = \sum_k W_k (d_k - d_{0,k})^2
$$

</div>

<div style="display:flex; justify-content:center; margin-top:1em; margin-bottom:1em;">

$$
\text{Score} = w_{\text{vdW}}E_{\text{vdW}} + w_{\text{elec}}E_{\text{elec}} + w_{\text{desolv}}E_{\text{desolv}} + w_{\text{air}}E_{\text{air}} - w_{\text{BSA}}\cdot\text{BSA}
$$

</div>

Training was conducted under five-fold cross-validation, with predictive performance evaluated using the coefficient of determination (R²) and root-mean-square error (RMSE).  
To ensure biological plausibility, we incorporated an empirical constraint based on the 10%→90% rise width of the Gompertz curve .  
<div style="display:flex; justify-content:center; margin-top:1em; margin-bottom:1em;">

$$
y(t) = A + (K - A)\exp\!\left[-\exp\!\left(\frac{\mu_{\max} e}{K - A}(\lambda - t) + 1\right)\right]
$$

</div>

In specific scenarios, μₘₐₓ was recalculated from this constraint , further improving the physiological interpretability of predictions.  
<div style="display:flex; justify-content:center; margin-top:1em; margin-bottom:1em;">

$$
L = \frac{1}{n}\sum_{i=1}^{n}(y_i - \hat{y}_i)^2
$$

</div>


In summary, this tri-layer modelling framework — **mechanistic fitting**, **data-driven regression**, and **empirical constraint** — ensures both interpretability and generalization, providing a robust tool for predictive modelling and optimization of microbial growth curves.  
This hybrid approach bridges mechanistic insight with data-driven flexibility, enabling rational environmental optimization in bioprocess design.  

{% include figure.html image="https://static.igem.wiki/teams/5569/model/m9.webp" caption=" Figure 7. Environmental adjustment of lipid growth curve (pH 6.0, 30 °C)." %}

### 3.4 Results and Model Verification

After completing curve fitting and machine learning training, we systematically evaluated the overall performance and extrapolation capability of the model. All 144 growth curves (12 environmental conditions × 12 substrates) were successfully fitted without any failure, demonstrating the strong adaptability and numerical stability of the Gompertz equation within this system. The fitted curves closely overlapped with the experimental measurements, accurately capturing the initiation, exponential, and stationary phases of the typical sigmoidal growth pattern, confirming that the model can robustly describe microbial growth under diverse conditions.

{% include figure.html image="https://static.igem.wiki/teams/5569/model/m10-3.webp" caption=" Figure 7. System evaluation of growth fitting and model prediction." %}

To assess the model’s generalization ability, fivefold cross-validation was conducted on the training dataset, and an independent test set was constructed for unseen conditions. The training dataset included combinations of pH 4.5, 5.5, 6.5, and 7.5 with temperatures of 24 °C, 28 °C, and 32 °C, while the test dataset comprised four new conditions (pH 6.0 and 6.8 × 26 °C and 30 °C). Cross-validation results showed that the Random Forest model achieved the best overall accuracy, with an average RMSE of approximately 0.0609 and R² of 0.93, whereas XGBoost yielded slightly higher error with a normalized RMSE of around 0.12. The predicted values of the four Gompertz parameters (A, K, μₘₐₓ, and λ) exhibited strong linear correlation with the fitted results, indicating that the model successfully learned the nonlinear mapping between environmental variables and growth kinetics.
{% include figure.html image="https://static.igem.wiki/teams/5569/model/m11.webp" caption=" Figure 7. Predicted vs. true values for Gompertz parameters.." %}

In the independent test set, the predicted growth curves almost completely overlapped with the experimentally fitted ones. The onset of the exponential phase and the stationary plateau were consistent across curves, with deviations in onset time and maximum specific growth rate remaining within ±5 %. These results indicate that the learned mapping relationships can reliably extend to unseen environmental conditions, demonstrating excellent extrapolation performance.

{% include figure.html image="https://static.igem.wiki/teams/5569/model/m12.webp" caption=" Figure 7. Predicted vs. actual growth curve (unseen condition, 26 °C)." %}

The reliability of the model was further confirmed through multiple validation strategies. Leave-one-condition-out analysis showed that removing any single condition still yielded predictions with an average R² above 0.9. Residual analysis revealed a normal distribution of prediction errors across different pH and temperature combinations, without systematic bias. Moreover, bootstrap resampling demonstrated that 90 % prediction intervals successfully encompassed over 90 % of the true parameter values, confirming the robustness and statistical confidence of the model.

In summary, the combined “prediction + constraint” framework preserves biophysical interpretability while enabling accurate extrapolation to unseen environmental conditions. The model exhibits high stability, generalization, and physiological plausibility, providing a reliable quantitative foundation for subsequent metabolic modeling and cultivation optimization.

### 3.5 Biological Interpretation

The four kinetic parameters (A, K, μₘₐₓ, λ) extracted from the model provide clear insights into how *Yarrowia lipolytica* responds to different environmental conditions. Both pH and temperature exhibited strong nonlinear effects on growth dynamics. At pH 5.5–6.5 and 28 °C, the yeast achieved its highest maximum specific growth rate (μₘₐₓ) and the shortest lag-phase duration (λ), indicating this region represents the physiological optimum where metabolic activity and growth are most synchronized. This trend is consistent with previous reports on the optimal pH range for lipid accumulation, suggesting that the conditions favoring rapid population growth also coincide with enhanced biosynthetic activity.

When the environment deviated from this range (pH < 5 or > 7), μₘₐₓ decreased sharply while λ increased, indicating that both acidic and alkaline stresses delayed metabolic activation and slowed biomass expansion. Under alkaline conditions in particular, the model predicted that λ could increase by 1.5–2 fold, implying that membrane integrity and enzyme activity are compromised under pH stress.

Temperature exerted a clear influence on the carrying capacity (K). Above 28 °C, K gradually declined, suggesting that elevated temperatures induced early stationary phases and reduced total biomass yield. Conversely, between 24–28 °C, K remained stable at high levels, implying that moderate temperatures promote prolonged and balanced population growth.

**Table 3-1. Model predictions versus actual Gompertz parameters on independent test set**

<div style="font-size:12px; overflow-x:auto;">
<style>
th {
  vertical-align: top;   /* 🔹让表头文字贴在格子上边缘 */
  text-align: center;    /* 🔹水平居中（可选） */
}
</style>
<table>
<thead>
<tr>
<th>Group</th><th>Target</th><th>pH</th><th>Temperature </th>
<th>A_pd</th><th>K_pd</th><th>μₘₐₓ_pd</th><th>λ_pd</th>
<th>A_ac</th><th>K_ac</th><th>μₘₐₓ_ac</th><th>λ_ac</th>
</tr>
</thead>
<tbody>
<tr><td>1</td><td>Oleic_1:1</td><td>6.0</td><td>26.0</td><td>0.013</td><td>0.801</td><td>0.048</td><td>8.932</td><td>0.012</td><td>0.719</td><td>0.048</td><td>8.955</td></tr>
<tr><td>1</td><td>Oleic_1:3</td><td>6.0</td><td>26.0</td><td>0.028</td><td>0.507</td><td>0.072</td><td>8.471</td><td>0.027</td><td>0.451</td><td>0.072</td><td>8.558</td></tr>
<tr><td>1</td><td>Oleic_1:5</td><td>6.0</td><td>26.0</td><td>0.024</td><td>0.566</td><td>0.047</td><td>5.003</td><td>0.039</td><td>0.503</td><td>0.046</td><td>5.000</td></tr>
<tr><td>1</td><td>Linoleic_1:1</td><td>6.0</td><td>26.0</td><td>0.021</td><td>0.267</td><td>0.100</td><td>6.653</td><td>0.019</td><td>0.210</td><td>0.100</td><td>6.775</td></tr>
<tr><td>1</td><td>Linoleic_1:3</td><td>6.0</td><td>26.0</td><td>0.041</td><td>0.346</td><td>0.075</td><td>5.006</td><td>0.039</td><td>0.306</td><td>0.074</td><td>5.000</td></tr>
<tr><td>1</td><td>Linoleic_1:5</td><td>6.0</td><td>26.0</td><td>0.030</td><td>0.435</td><td>0.073</td><td>7.381</td><td>0.020</td><td>0.385</td><td>0.073</td><td>7.495</td></tr>
<tr><td>1</td><td>Alpha-linolenic_1:1</td><td>6.0</td><td>26.0</td><td>0.018</td><td>0.234</td><td>0.100</td><td>6.450</td><td>0.014</td><td>0.179</td><td>0.100</td><td>6.475</td></tr>
<tr><td>1</td><td>Alpha-linolenic_1:3</td><td>6.0</td><td>26.0</td><td>0.029</td><td>0.125</td><td>0.100</td><td>7.265</td><td>0.024</td><td>0.103</td><td>0.100</td><td>7.264</td></tr>
<tr><td>1</td><td>Alpha-linolenic_1:5</td><td>6.0</td><td>26.0</td><td>0.023</td><td>0.140</td><td>0.100</td><td>6.397</td><td>0.020</td><td>0.281</td><td>0.100</td><td>6.562</td></tr>
<tr><td>1</td><td>YPD</td><td>6.0</td><td>26.0</td><td>0.014</td><td>0.186</td><td>0.100</td><td>5.896</td><td>0.013</td><td>0.145</td><td>0.100</td><td>5.995</td></tr>
<tr><td>1</td><td>Lipid</td><td>6.0</td><td>26.0</td><td>0.049</td><td>0.552</td><td>0.100</td><td>10.861</td><td>0.044</td><td>0.496</td><td>0.100</td><td>10.875</td></tr>
<tr><td>1</td><td>Lipid-fatase</td><td>6.0</td><td>26.0</td><td>0.000</td><td>0.476</td><td>0.049</td><td>6.881</td><td>0.000</td><td>0.418</td><td>0.049</td><td>6.908</td></tr>
<tr><td>2</td><td>Oleic_1:1</td><td>6.0</td><td>30.0</td><td>0.018</td><td>0.818</td><td>0.048</td><td>8.920</td><td>0.014</td><td>0.799</td><td>0.048</td><td>8.862</td></tr>
<tr><td>2</td><td>Oleic_1:3</td><td>6.0</td><td>30.0</td><td>0.029</td><td>0.513</td><td>0.072</td><td>8.487</td><td>0.032</td><td>0.501</td><td>0.071</td><td>8.482</td></tr>
<tr><td>2</td><td>Oleic_1:5</td><td>6.0</td><td>30.0</td><td>0.042</td><td>0.568</td><td>0.047</td><td>5.005</td><td>0.049</td><td>0.558</td><td>0.046</td><td>5.000</td></tr>
<tr><td>2</td><td>Linoleic_1:1</td><td>6.0</td><td>30.0</td><td>0.021</td><td>0.258</td><td>0.100</td><td>6.667</td><td>0.022</td><td>0.233</td><td>0.100</td><td>6.720</td></tr>
<tr><td>2</td><td>Linoleic_1:3</td><td>6.0</td><td>30.0</td><td>0.042</td><td>0.347</td><td>0.075</td><td>5.006</td><td>0.047</td><td>0.338</td><td>0.075</td><td>5.000</td></tr>
<tr><td>2</td><td>Linoleic_1:5</td><td>6.0</td><td>30.0</td><td>0.020</td><td>0.435</td><td>0.073</td><td>7.399</td><td>0.022</td><td>0.427</td><td>0.071</td><td>7.246</td></tr>
<tr><td>2</td><td>Alpha-linolenic_1:1</td><td>6.0</td><td>30.0</td><td>0.017</td><td>0.224</td><td>0.100</td><td>6.452</td><td>0.015</td><td>0.199</td><td>0.100</td><td>6.476</td></tr>
<tr><td>2</td><td>Alpha-linolenic_1:3</td><td>6.0</td><td>30.0</td><td>0.029</td><td>0.122</td><td>0.100</td><td>7.270</td><td>0.028</td><td>0.115</td><td>0.100</td><td>7.233</td></tr>
<tr><td>2</td><td>Alpha-linolenic_1:5</td><td>6.0</td><td>30.0</td><td>0.032</td><td>0.328</td><td>0.100</td><td>6.426</td><td>0.039</td><td>0.312</td><td>0.100</td><td>6.439</td></tr>
<tr><td>2</td><td>YPD</td><td>6.0</td><td>30.0</td><td>0.014</td><td>0.178</td><td>0.100</td><td>5.912</td><td>0.014</td><td>0.161</td><td>0.100</td><td>5.859</td></tr>
<tr><td>2</td><td>Lipid</td><td>6.0</td><td>30.0</td><td>0.059</td><td>0.555</td><td>0.100</td><td>10.858</td><td>0.052</td><td>0.551</td><td>0.100</td><td>10.920</td></tr>
<tr><td>2</td><td>Lipid-fatase</td><td>6.0</td><td>30.0</td><td>0.000</td><td>0.477</td><td>0.048</td><td>6.840</td><td>0.000</td><td>0.465</td><td>0.047</td><td>6.592</td></tr>
<tr><td>3</td><td>Oleic_1:1</td><td>6.8</td><td>26.0</td><td>0.013</td><td>0.824</td><td>0.048</td><td>8.922</td><td>0.010</td><td>0.613</td><td>0.048</td><td>8.943</td></tr>
<tr><td>3</td><td>Oleic_1:3</td><td>6.8</td><td>26.0</td><td>0.029</td><td>0.519</td><td>0.072</td><td>8.478</td><td>0.023</td><td>0.386</td><td>0.072</td><td>8.549</td></tr>
<tr><td>3</td><td>Oleic_1:5</td><td>6.8</td><td>26.0</td><td>0.043</td><td>0.574</td><td>0.047</td><td>5.004</td><td>0.033</td><td>0.430</td><td>0.046</td><td>5.000</td></tr>
<tr><td>3</td><td>Linoleic_1:1</td><td>6.8</td><td>26.0</td><td>0.021</td><td>0.259</td><td>0.100</td><td>6.664</td><td>0.016</td><td>0.179</td><td>0.100</td><td>6.808</td></tr>
<tr><td>3</td><td>Linoleic_1:3</td><td>6.8</td><td>26.0</td><td>0.042</td><td>0.351</td><td>0.075</td><td>5.006</td><td>0.034</td><td>0.261</td><td>0.073</td><td>5.000</td></tr>
<tr><td>3</td><td>Linoleic_1:5</td><td>6.8</td><td>26.0</td><td>0.021</td><td>0.443</td><td>0.073</td><td>7.386</td><td>0.017</td><td>0.328</td><td>0.074</td><td>7.548</td></tr>
<tr><td>3</td><td>Alpha-linolenic_1:1</td><td>6.8</td><td>26.0</td><td>0.027</td><td>0.227</td><td>0.100</td><td>6.450</td><td>0.012</td><td>0.152</td><td>0.100</td><td>6.508</td></tr>
<tr><td>3</td><td>Alpha-linolenic_1:3</td><td>6.8</td><td>26.0</td><td>0.029</td><td>0.123</td><td>0.100</td><td>7.269</td><td>0.021</td><td>0.088</td><td>0.100</td><td>7.288</td></tr>
<tr><td>3</td><td>Alpha-linolenic_1:5</td><td>6.8</td><td>26.0</td><td>0.036</td><td>0.329</td><td>0.100</td><td>6.410</td><td>0.030</td><td>0.240</td><td>0.100</td><td>6.668</td></tr>
<tr><td>3</td><td>YPD</td><td>6.8</td><td>26.0</td><td>0.013</td><td>0.180</td><td>0.100</td><td>5.899</td><td>0.011</td><td>0.124</td><td>0.100</td><td>5.800</td></tr>
<tr><td>3</td><td>Lipid</td><td>6.8</td><td>26.0</td><td>0.030</td><td>0.566</td><td>0.100</td><td>10.859</td><td>0.038</td><td>0.423</td><td>0.100</td><td>10.868</td></tr>
<tr><td>3</td><td>Lipid-fatase</td><td>6.8</td><td>26.0</td><td>0.000</td><td>0.484</td><td>0.048</td><td>6.845</td><td>0.002</td><td>0.355</td><td>0.051</td><td>7.187</td></tr>
<tr><td>4</td><td>Oleic_1:1</td><td>6.8</td><td>30.0</td><td>0.031</td><td>0.828</td><td>0.048</td><td>9.012</td><td>0.028</td><td>0.907</td><td>0.048</td><td>8.950</td></tr>
<tr><td>4</td><td>Oleic_1:3</td><td>6.8</td><td>30.0</td><td>0.029</td><td>0.520</td><td>0.072</td><td>8.947</td><td>0.027</td><td>0.453</td><td>0.072</td><td>8.950</td></tr>
<tr><td>4</td><td>Oleic_1:5</td><td>6.8</td><td>30.0</td><td>0.043</td><td>0.576</td><td>0.047</td><td>5.007</td><td>0.041</td><td>0.539</td><td>0.047</td><td>5.000</td></tr>
<tr><td>4</td><td>Linoleic_1:1</td><td>6.8</td><td>30.0</td><td>0.022</td><td>0.259</td><td>0.100</td><td>6.675</td><td>0.022</td><td>0.229</td><td>0.100</td><td>6.784</td></tr>
<tr><td>4</td><td>Linoleic_1:3</td><td>6.8</td><td>30.0</td><td>0.041</td><td>0.352</td><td>0.075</td><td>5.010</td><td>0.040</td><td>0.331</td><td>0.074</td><td>5.000</td></tr>
<tr><td>4</td><td>Linoleic_1:5</td><td>6.8</td><td>30.0</td><td>0.022</td><td>0.446</td><td>0.073</td><td>7.391</td><td>0.020</td><td>0.402</td><td>0.073</td><td>7.472</td></tr>
<tr><td>4</td><td>Alpha-linolenic_1:1</td><td>6.8</td><td>30.0</td><td>0.018</td><td>0.228</td><td>0.100</td><td>6.458</td><td>0.016</td><td>0.186</td><td>0.100</td><td>6.489</td></tr>
<tr><td>4</td><td>Alpha-linolenic_1:3</td><td>6.8</td><td>30.0</td><td>0.029</td><td>0.124</td><td>0.100</td><td>7.278</td><td>0.025</td><td>0.107</td><td>0.100</td><td>7.266</td></tr>
<tr><td>4</td><td>Alpha-linolenic_1:5</td><td>6.8</td><td>30.0</td><td>0.035</td><td>0.331</td><td>0.100</td><td>6.436</td><td>0.032</td><td>0.289</td><td>0.100</td><td>6.459</td></tr>
<tr><td>4</td><td>YPD</td><td>6.8</td><td>30.0</td><td>0.014</td><td>0.183</td><td>0.100</td><td>5.915</td><td>0.013</td><td>0.151</td><td>0.100</td><td>5.904</td></tr>
<tr><td>4</td><td>Lipid</td><td>6.8</td><td>30.0</td><td>0.061</td><td>0.557</td><td>0.100</td><td>10.863</td><td>0.055</td><td>0.522</td><td>0.100</td><td>10.881</td></tr>
<tr><td>4</td><td>Lipid-fatase</td><td>6.8</td><td>30.0</td><td>0.000</td><td>0.479</td><td>0.048</td><td>6.842</td><td>0.000</td><td>0.442</td><td>0.047</td><td>6.701</td></tr>
</tbody>
</table>
</div>


> **RMSE:** 0.0609  **R²:** 0.9333  
> The model shows close agreement between predicted and actual Gompertz parameters across unseen pH–temperature conditions.




Together, these findings demonstrate that the model successfully captured the multidimensional physiological responses of *Y. lipolytica* to environmental variation. The inverse relationship between μₘₐₓ and λ reflects the trade-off between metabolic activation and adaptation, while the decline of K at higher temperatures highlights energy and stability constraints under heat stress. Overall, this interpretation confirms the biological validity of the model and provides quantitative guidance for optimizing culture conditions.

### 3.6 Limitations and Future Work

Although the hybrid modelling framework developed in this study demonstrated high accuracy and interpretability in predicting and optimizing microbial growth, several limitations remain.  
First, the Gompertz equation assumes a single sigmoidal phase and does not account for substrate depletion, nutrient limitation, or metabolic reprogramming.  
As a result, its descriptive capacity may decline when *Yarrowia lipolytica* undergoes secondary growth or stress-induced recovery under complex substrate conditions.  
Second, the machine-learning module currently relies on static environmental inputs (pH, temperature, substrate type), without incorporating temporal features or process factors such as dissolved oxygen or C/N ratio.  
This allows the model to capture global growth trends but limits its ability to represent short-term transitions or regulatory responses.

Future extensions will focus on two directions:  
(1) introducing dynamic modelling approaches, such as sequence-to-sequence architectures or neural ordinary differential equations (Neural ODEs), to describe multi-phase growth and stress-response processes;  
and (2) expanding the dataset to include multiple carbon sources and nutrient regimes, enabling the construction of a multidimensional predictive model that learns substrate adaptability and growth stability simultaneously.  

Overall, this framework establishes a generalizable approach for predictive and interpretable growth modelling in *Y. lipolytica*, which can be further enhanced by integrating dynamic information and environmental complexity.

{% include button.html link="https://gitlab.igem.org/2025/software-tools/hust-china" text="Click to learn more about our software-tools" %}

## References
1. Gould SJ, Keller GA, Hosken N, Wilkinson J, Subramani S. *A conserved tripeptide sorts proteins to peroxisomes.* **J Cell Biol.** 1989;108(5):1657–1664.  
2. Brocard C, Hartig A. *Peroxisome targeting signal 1: Is it really a simple tripeptide?* **Biochim Biophys Acta.** 2006;1763(12):1565–1573.  
3. Lametschwandtner G, Brocard C, Fransen M, Van Veldhoven PP, Berger J, Hartig A. *The difference in recognition of PTS1 and PTS2 signals is conserved between yeast and mammals.* **EMBO J.** 1998;17(21):5948–5958.  
4. Neuberger G, Maurer-Stroh S, Eisenhaber B, Hartig A, Eisenhaber F. *Prediction of peroxisomal targeting signal 1–containing proteins from amino acid sequence.* **J Mol Biol.** 2003;328(3):581–592.  
5. Dominguez C, Boelens R, Bonvin AMJJ. *HADDOCK: A protein–protein docking approach based on biochemical or biophysical information.* **J Am Chem Soc.** 2003;125(7):1731–1737.  
6. van Zundert GCP, Rodrigues JPG, Trellet M, Schmitz C, Kastritis PL, Karaca E, *et al.* *The HADDOCK2.4 web server: user-friendly integrative modeling of biomolecular complexes.* **J Mol Biol.** 2016;428(4):720–725.  
7. Rodrigues JPG, Trellet M, Schmitz C, Kastritis PL, Karaca E, Melquiond ASJ, Bonvin AMJJ. *Clustering biomolecular complexes by residue contacts similarity.* **Proteins.** 2012;80(7):1810–1817.  
8. van Zundert GCP, Bonvin AMJJ. *Modeling protein–protein complexes using the HADDOCK webserver.* **Methods Mol Biol.** 2014;1137:163–179.  
9. Dauparas J, Anishchenko I, Bennett N, *et al.* **Robust deep learning based protein sequence design using ProteinMPNN.** *Science.* 2022;378(6615):49–56.  
10. Ferreiro DU, Hegler JA, Komives EA, Wolynes PG. **Localizing frustration in native proteins and protein assemblies.** *Proc Natl Acad Sci USA.* 2007;104(50):19819–19824.  
11. Parra RG, Schafer NP, Radusky LG, Tsai MY, Guzovsky AB, Wolynes PG, Ferreiro DU. **Protein Frustratometer 2: a tool to localize energetic frustration in protein molecules, now with electrostatics.** *Nucleic Acids Res.* 2016;44(W1):W356–W360.  
12. Tyka MD, Keedy DA, André I, Dimaio F, Song Y, Richardson DC, Richardson JS, Baker D. **Alternate states of proteins revealed by detailed energy landscape mapping.** *J Mol Biol.* 2011;405(2):607–618.  
13. Leaver-Fay A, Tyka M, Lewis SM, Lange OF, Thompson J, Jacak R, Kaufman K, Renfrew PD, Smith CA, Sheffler W, *et al.* **ROSETTA3: An object-oriented software suite for the simulation and design of macromolecules.** *Methods Enzymol.* 2011;487:545–574.  
14. Istvan ES, Deisenhofer J. **Structural mechanism for statin inhibition of HMG-CoA reductase.** *Science.* 2001;292(5519):1160–1164.  
15. Miziorko HM. **Enzymes of the mevalonate pathway of isoprenoid biosynthesis.** *Arch Biochem Biophys.* 2011;505(2):131–143.  
16. Liu Z, Gao Y, Chen J, Imanaka T, Bao J, Hua Q. **Metabolic engineering of *Yarrowia lipolytica* for the production of terpenoids.** *Metab Eng.* 2019;57:151–161.  
17. Rodriguez GM, Hussain MS, Gambill L, Gao D, Yaguchi A, Blenner M. **Engineering *Yarrowia lipolytica* to produce fuels and chemicals from xylose.** *Biotechnol Bioeng.* 2016;113(11):2528–2538.  
18. Zwietering MH, Jongenburger I, Rombouts FM, van ’t Riet K. Modeling of the bacterial growth curve. *Appl Environ Microbiol.* 1990;56(6):1875–81.  
19. Gibson AM, Bratchell N, Roberts TA. The effect of sodium chloride and temperature on the rate and extent of growth of *Clostridium botulinum* type A. *J Appl Bacteriol.* 1988;65(2):95–108.  
20. Ratkowsky DA, Olley J, McMeekin TA, Ball A. Relationship between temperature and growth rate of bacterial cultures. *J Bacteriol.* 1982;149(1):1–5.  
21. Gupta S, Mozaffar H, Syed A, et al. Machine learning models for microbial growth prediction under environmental stress. *Biotechnol Bioeng.* 2020;117(12):3727–38.  
22. Buchanan RL, Whiting RC, Damert WC. When is simple good enough: a comparison of the Gompertz, logistic, and other empirical models for fitting bacterial growth curves. *Food Microbiol.* 1997;14(4):313–26.  
23. Desai M, Udupa S, Chatterjee S, Sarma SJ. A hybrid machine learning framework for predictive bioprocess modeling using ensemble tree algorithms. *Comput Chem Eng.* 2022;157:107675.  
24. Rajamanickam S, Misra BB. Machine learning-based prediction of microbial growth under multiple environmental conditions. *Front Microbiol.* 2021;12:713517.  
25. Yang H, He F, Liu J, et al. Integration of mechanistic models and machine learning improves prediction accuracy in microbial fermentation. *Biotechnol J.* 2023;18(4):2200604.  
26. Larroude M, Rossignol T, Nicaud JM, Ledesma-Amaro R. Synthetic biology tools for engineering *Yarrowia lipolytica*. *Biotechnol Adv.* 2018;36(8):2150–64.  
27. Qiao K, Abidi SHI, Liu H, Zhang H, Chakraborty S, Zhang L, Tang Y. Engineering lipid overproduction in the oleaginous yeast *Yarrowia lipolytica*. *Metab Eng.* 2015;29:56–65.
