---
title: Model
permalink: /model/
feature_text: |
feature_image: "https://static.igem.wiki/teams/5569/description/modl.webp"
excerpt: ""
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




