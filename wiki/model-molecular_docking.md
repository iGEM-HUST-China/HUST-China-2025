---
title: Molecular Docking
permalink: /model/molecular-docking/
feature_text: |
  ## Model
  All models are wrong, but some are useful.——George E. P. Box
feature_image: "https://static.igem.wiki/teams/5175/resources/background/bg-model.jpg"
excerpt: "The model is a means of assisting the overall completion and implementation of a project through computational methods."
---

## Molecular Docking

{% include figure.html 
  image="https://static.igem.wiki/teams/5175/resources/model/molecular-docking-intro.gif" 
  alt="Molecular Docking" 
  caption="Fig 1. Introduction to Molecular Docking"
%}

Molecular docking refers to the computational simulation of interactions between small molecules and target molecules to predict their binding modes and sites. In our project design, we aimed to identify the most efficient PETase-MHETase dual-enzyme system for PET degradation. We estimated the types and lengths of linkers, along with the order of PETase and MHETase in the peptide sequence may influence degradation efficiency. Therefore, we employed molecular docking to explore how these factors affect the binding affinity of PETase within the dual-enzyme system. Ultimately, we identified the most effective combination, PETase-ggggs(15)-MHETase, for subsequent project design and wetlab studies.

### Materials

We obtained the sequence information for FAST-PETase and MHETase from the PDB. For linkers, they are generally classified into 2 types, flexible linkers and rigid linkers. Flexible linkers provide better adaptability, allowing the connected enzymes to rotate and move freely, which is essential for dynamic interactions. In contrast, rigid linkers prevent excessive proximity or rotation between the two enzymes, maintaining appropriate spatial separation and reducing interference. We selected 5 widely used linkers, including flexible linkers (GGGGS, GSGSG, and GGGGG) and rigid linkers (EAAAK and PAPAP), incorporating 6 varying linker lengths (10, 15, 20, 25, 30, and 35 amino acids) to construct the PETase-Linker-MHETase dual-enzyme system.

We obtained the three-dimensional structure of the dual-enzyme system from the AlphaFold Server[^1]and used AutoDockTools to add polar hydrogen atoms,which serves as the receptor for docking. The ligands were constructed using Avogadro, an advanced semantic chemical editor, visualization, and analysis platform[^2]. We utilized Avogadro to build and minimize 4PET as the ligand for molecular docking.

### Methods

We used AutoDock Vina[^3] [^4]to perform docking between the ligand and receptor. The box parameters were configured based on the positions of the catalytic triad (Ser133, Asp179, His210) and the oxyanion hole (Tyr60, Met134) on PETase.[^5]A semi-flexible docking approach was employed, with the ligand 4PET set as a flexible molecule and the receptor treated as a rigid molecule. After docking, the conformation with the lowest binding energy was selected as the basis for assessing the affinity between the ligand and receptor.

The conformation-related scoring function used in AutoDock Vina is based on the following equations:

<center>
$$
  c = \sum f _ { t _ { i } t _ { j } } ( r _ { i j } )
$$
</center>

The summation range includes all pairs of atoms that can move relative to each other. Each atom $i$ is assigned a type $t_i$, and an interaction function $f$ is defined based on the distances between atoms.

$c$can be viewed as the sum of contributions from intermolecular and intramolecular interactions, namely:

<center>
$$
  c = c _ { \mathrm{inter} } + c _ { \mathrm{intra} }
$$
</center>

### Results

By varying the types of linkers, linker lengths, and the orders of PETase and MHETase, we investigated how these factors influence the affinity between PET and PETase. A total of 60 combinations were compared using 5 types of linkers, 6 different linker lengths, and 2 orders, resulting in affinity data (<a href="https://static.igem.wiki/teams/5175/resources/model/molecular-docking-result.csv" target="_blank">Click here</a> to download the attachment, find part of the result in Fig. 2).

{% include figure.html 
  image="https://static.igem.wiki/teams/5175/resources/model/molecular-docking-01.png" 
  alt="Molecular Docking" 
  caption="Fig 2. Part of the results of molecular docking<br>Note:The conformation of PET after docking and the hydrogen bonds formed are shown, with the red portion representing 4PET and the blue portion indicating the amino acid residues that form hydrogen bonds with PET. In the protein names, \"f\" denotes FAST-PETase, while \"eaaak\" and others represent different types of linkers, with the length of the linker (number of amino acids) indicated in parentheses, and \"m\" representing MHETase." 
%}

From the docking results, it can be observed that some dual-enzyme systems using rigid linkers exhibited good affinity of PETase for PET. However, considering that flexible linkers provide better flexibility, allowing the connected enzymes to rotate and move freely to adapt to dynamic interactions, we prefered to choose flexible linkers. Although the PETase-gsgsg(35)-MHETase combination exhibited the highest affinity among flexible linkers, the docking results indicate that PET interacts with both enzymes simultaneously. Therefore, after comprehensive consideration, we selected the PETase-ggggs(15)-MHETase combination, which showed good affinity and reasonable hydrogen bonds in the docking results (see Figure 3).

{% include figure.html 
  image="https://static.igem.wiki/teams/5175/resources/model/molecular-docking-02.png" 
  alt="Molecular Docking" 
  caption="Fig 3. Docking results of PETase-ggggs(15)-MHETase<br>Note: The red portion represents 4PET, the green portion represents PETase, the pink portion is the 15 amino acid linker of type ggggs, and the yellow portion represents MHETase."
%}

### Limitation

Molecular docking investigated the differences of PET-PETase affinity in different dual-enzyme systems, providing a basis for selecting the optimal combination. However, the binding energy of 4PET with monomer FAST-PETase is -9.8 kcal/mol, suggesting that the increased efficiency of PET degradation in dual enzyme systems cannot solely be explained by affinity. Future work should consider the impact of PETase reaction product diffusion.

The docking used a semi-flexible approach, treating the receptor as a rigid body, which may differ from actual conditions. Future studies could set the catalytic site of PETase as flexible to obtain more accurate binding energies. 

The computational method also has limitations: AutoDock Vina employs iterative local search for global optimization, which may miss the optimal conformation. Increasing the number of repetitions could reduce this likelihood.




{% include button.html link="../" text="Go back to Model Introduction" %}

---

## References

[^1]: Abramson, J., Adler, J., Dunger, J. et al. Accurate structure prediction of biomolecular interactions with AlphaFold 3. Nature 630, 493–500 (2024). doi: 10.1038/s41586-024-07487-w
[^2]: Hanwell, M.D., Curtis, D.E., Lonie, D.C. et al. Avogadro: an advanced semantic chemical editor, visualization, and analysis platform. J Cheminform 4, 17 (2012). doi: 10.1186/1758-2946-4-17
[^3]: Trott O, Olson AJ. AutoDock Vina: improving the speed and accuracy of docking with a new scoring function, efficient optimization, and multithreading. J Comput Chem. 2010 Jan 30;31(2):455-61. doi: 10.1002/jcc.21334. PMID: 19499576; PMCID: PMC3041641.
[^4]: Eberhardt J, Santos-Martins D, Tillack AF, Forli S. AutoDock Vina 1.2.0: New Docking Methods, Expanded Force Field, and Python Bindings. J Chem Inf Model. 2021 Aug 23;61(8):3891-3898. doi: 10.1021/acs.jcim.1c00203. Epub 2021 Jul 19. PMID: 34278794; PMCID: PMC10683950.
[^5]: García-Meseguer R, Ortí E, Tuñón I, Ruiz-Pernía JJ, Aragó J. Insights into the Enhancement of the Poly(ethylene terephthalate) Degradation by FAST-PETase from Computational Modeling. J Am Chem Soc. 2023 Sep 6;145(35):19243-19255. doi: 10.1021/jacs.3c04427. Epub 2023 Aug 16. PMID: 37585687; PMCID: PMC10851425.
