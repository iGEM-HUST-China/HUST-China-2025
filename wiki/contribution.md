---
title: Contribution
permalink: /contribution/
feature_text: |
feature_image: "https://static.igem.wiki/teams/5569/description/ctbtion.webp"
excerpt: ""
---

## Overview
# Project Contribution: Converting Waste Cooking Oil to High-Value Squalene

**This project aims to efficiently convert waste cooking oil into high-value squalene through synthetic biology technology.**

**Through systematic metabolic engineering, we introduced high-efficiency lipases for waste oil degradation, improved the squalene synthesis pathway in *Yarrowia lipolytica*, and innovatively adopted a peroxisomal compartmentalization strategy using the optimal peroxisomal targeting peptide identified by model-based algorithms to enhance yield. Additionally, we developed a low-cost, automated fermentation processing system, providing a complete solution for the scalable production of squalene.**

## Part 1: Parts

**These parts are crucial for constructing the squalene synthesis pathway. Our project has registered several basic parts, achieving efficient conversion from waste cooking oil to squalene through the combination of the following modules.**

{% include figure.html image="https://static.igem.wiki/teams/5569/en/20251007222710-2089-153.webp" caption="Figure 1 All plasmid maps" %}

### 1.1 Metabolic Pathway Optimization Module

- **Hp4d-Kozak-tHMGr-XPR2_term**
  This part expresses a truncated HMG-CoA reductase (tHMGR), which relieves the feedback inhibition of the native enzyme, significantly increasing the flux through the MVA pathway and providing ample precursor substances for squalene synthesis.

- **Hp4d-Kozak-NADH_HMGr-XPR2_term**
  This part introduces an exogenous NADH-dependent HMGR from *Silicibacter pomeroyi*, which can utilize the abundant NADH in peroxisomes, further strengthening the rate-limiting step of the MVA pathway.

### 1.2 β-Oxidation Enhancement Module

- **Hp4d-Kozak-POX2-XPR2_term**
  This part overexpresses the first enzyme in the fatty acid β-oxidation pathway—fatty acyl-CoA oxidase—initiating the fatty acid degradation process.

- **Hp4d-Kozak-MFE2-XPR2_term**
  This part overexpresses a multifunctional enzyme in the β-oxidation pathway, possessing hydratase, dehydrogenase, and epimerase activities.

- **Hp4d-Kozak-POT1-XPR2_term**
  This part overexpresses 3-ketoacyl-CoA thiolase, responsible for the thiolysis reaction in the final step of β-oxidation, generating acetyl-CoA.

- **Hp4d-Kozak-POX2-XPR2_term-Hp4d-Kozak-MFE1-XPR2_term-Hp4d-Kozak-POT1-XPR2_term**
  This composite part integrates three key enzymes of the β-oxidation pathway into a single plasmid, significantly enhancing the supply efficiency of acetyl-CoA and the NADH cofactor content within peroxisomes through modular design.

### 1.3 Peroxisomal Compartmentalization Module

- **Hp4d-Kozak-ERG10-PTS1-XPR2_term**
  This part expresses acetyl-CoA acetyltransferase carrying the PTS1 signal peptide, targeting it to the peroxisome, where it catalyzes the condensation of two acetyl-CoA molecules into acetoacetyl-CoA.

- **Hp4d-Kozak-ERG13-PTS1-XPR2_term**
  This part expresses HMG-CoA synthase carrying the PTS1 signal peptide, catalyzing the condensation of acetoacetyl-CoA and acetyl-CoA into HMG-CoA within the peroxisome.

- **Hp4d-Kozak-tHMGr-PTS1-XPR2_term & Hp4d-Kozak-NADH_HMGr-PTS1-XPR2_term**
  These two parts express the peroxisome-targeted truncated HMGR and NADH-dependent HMGR, respectively, efficiently catalyzing the reduction of HMG-CoA to mevalonate within the peroxisome.

- **Hp4d-Kozak-ERG12-PTS1-XPR2_term, Hp4d-Kozak-ERG8-PTS1-XPR2_term, Hp4d-Kozak-ERG19-PTS1-XPR2_term**
  These parts are responsible for phosphorylating mevalonate and decarboxylating it to generate IPP, with all enzymes targeted to the peroxisome.

- **Hp4d-Kozak-IDI-PTS1-XPR2_term, Hp4d-Kozak-ERG20-PTS1-XPR2_term, Hp4d-Kozak-ERG9-PTS1-XPR2_term**
  These parts catalyze the final steps from IPP to squalene, including IPP isomerization, the stepwise synthesis of FPP, and the condensation of two FPP molecules into squalene, with the complete pathway localized to the peroxisome.

- **Composite Parts for Modular MVA Pathway Assembly:**
  - *Hp4d-Kozak-POX2-XPR2_term-Hp4d-Kozak-MFE1-XPR2_term-Hp4d-Kozak-POT1-XPR2_term*
  - *Hp4d-Kozak-ERG10-PTS1-XPR2_term-Hp4d-Kozak-ERG13-PTS1-XPR2_term-Hp4d-Kozak-tHMGR-PTS1-XPR2_term-Hp4d-Kozak-NADH_HMGR-PTS1-XPR2_term*
  - *Hp4d-Kozak-ERG12-PTS1-XPR2_term-Hp4d-Kozak-ERG8-PTS1-XPR2_term-Hp4d-Kozak-ERG19-PTS1-XPR2_term*
  - *Hp4d-Kozak-E9-PTS1-XPR2_term-Hp4d-Kozak-IDI-PTS1-XPR2_term-Hp4d-Kozak-E20-PTS1-XPR2_term*

  **Modular MVA Pathway Assembly:**
  We divided the complete compartmentalized MVA pathway into four functional plasmids for modular assembly, greatly simplifying genetic operations and providing convenience for subsequent industrial applications and pathway optimization.

### 1.4 Peroxisome Regulation Module

- **HP4d-Kozak-PEX10-XPR2-term**
  This part overexpresses the peroxisome biogenesis factor PEX10, used to regulate the number and size of peroxisomes, providing greater synthesis capacity for the compartmentalized metabolic pathway.

### 1.5 Lipase Secretion Module

- **Hp4d-Kozak-mTLL-XPR2_term**
  This part expresses a codon-optimized and modified thermostable lipase (mTLL), achieving efficient extracellular secretion of the lipase to decompose triglycerides in waste cooking oil into free fatty acids.

### 1.6 Biosafety Module

- ***Hp4d-EL222-XPR2_term-5C120_8lexA operator_CYC1 minimal box promoter-Cas9-XPR2-Scr1_trna-crRNA (Hsp82, Hsc82)-SpCas9 Scaffold***

  **Blue Light-Activated Suicide Switch:** This composite part contains the blue light sensor protein EL222 and the CRISPR-Cas9 system. Under blue light irradiation, the system activates and expresses Cas9 nuclease and crRNA targeting the essential genes *HSP82* and *HSC82*, inducing cell death to prevent accidental leakage of the engineered strain.

- ***HP4d-PhyB- XPR2_term -hp4d-PIF-XPR2-PIF_BP-Lex2- XPR2_term***

  **Red Light Survival Regulation System:** This part contains the red light sensing system PhyB-PIF, which can express the survival factor Lex2 under red light irradiation, counteracting the blue light-induced death signal and providing a dual-regulation mechanism for cell fate.

## Part 2: Wet Lab

### 2.1 Genetic Engineering

When constructing large metabolic pathways containing multiple genes, we initially attempted traditional restriction enzyme digestion and ligation methods. However, due to the complex plasmid structures and large number of fragments, the efficiency was low. Subsequently, we switched to Gibson Assembly technology. By precisely designing homologous arms, we successfully constructed all complex multi-gene expression plasmids. This experience demonstrates that for complex metabolic engineering projects, selecting the appropriate DNA assembly method is crucial.

### 2.2 Growth Curve Measurement

During the first measurement of strain concentration in oily medium, we were surprised to find that the resulting growth curves were not the standard "S-shaped" curve. All growth curves showed an initial decrease followed by an increase, then entering a plateau phase. Investigation revealed that oil droplets also absorb light at OD600. In the early stage, as the strain degrades oil droplets for growth, the increase in yeast cell count is slower than the rate of oil droplet degradation, so the OD600 shows a downward trend. Subsequently, the yeast strain enters the logarithmic phase, and the cell count increases rapidly, causing OD600 to show an upward trend. Later, we utilized centrifugation operations, measuring the OD600 before and after centrifugation of samples multiple times to objectively determine the current growth status of the strain. This experience indicates that for OD measurements in media containing oil droplets, centrifugation operations are necessary.

## Part 3: Hardware

{% include figure.html image="https://static.igem.wiki/teams/5569/hardware/hh40.webp" caption="Figure 2 iFPS Schematic Diagram" %}

During the project advancement, we identified a significant technological gap between traditional laboratory shake flask cultivation and industrial fermentation. To address this, we independently designed and developed an Integrated Fermentation & Processing System (iFPS). This system innovatively integrates microbial fermentation, cell centrifugation and collection, and mechanical disruption/lysis functions into a compact desktop device. Through automated control, it achieves the entire process operation from inoculation to obtaining crude lysate. Our device is available for all teams to replicate and use, hoping to provide a viable solution for the iGEM community and the field of synthetic biology regarding micro-fermentation issues, thereby promoting the development of synthetic biology.

## Part 4: Modeling

{% include figure.html image="https://static.igem.wiki/teams/5569/model/m1.webp" caption="Figure3. Molecular_docking" %}
**The functions and value our model can provide to other researchers or teams:**
The Model digital twin modeling system we built not only serves the metabolic reprogramming research of this project but also provides a universal framework and reusable tools for other teams engaged in microbial metabolic engineering and systems modeling.

- **Molecular Docking Level:** Can be used for binding energy analysis and conformational screening of any signal peptide or receptor, providing a quantitative basis for research on protein localization anchoring and transmembrane transport mechanisms.

- **Enzyme Design Engineering Level:** Provides an integrated sequence-structure optimization pipeline based on ProteinMPNN and Rosetta, helping users quickly generate and screen stable, highly active enzyme mutants.

- **System Level:** Can input any environmental parameters (e.g., pH, temperature, substrate type) to automatically fit growth curves and predict kinetic parameters, applicable to fermentation process optimization or strain tolerance analysis.

Through this three-tier architecture, users can comprehensively evaluate biological system performance from structure, function, to phenotype, achieving **interpretable, transferable, and reusable** modeling design.
In the future, we hope to expand this model into an open, callable computational platform to support more iGEM teams and researchers.
