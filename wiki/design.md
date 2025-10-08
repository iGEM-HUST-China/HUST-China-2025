---
title: Design
permalink: /design/
feature_text: |
feature_image: "https://static.igem.wiki/teams/5569/description/desn.webp"
excerpt: ""
---

# Design Description: From Waste Oil to Sustainable Squalene


## 1. Introduction

**Squalene** is a high-value terpene known for its **excellent biocompatibility** and diverse applications in cosmetics, food, and nutraceuticals. However, current production methods—primarily shark-derived extraction and food crop-based synthesis—pose serious sustainability and ethical concerns.

Globally, over 150 million tons of **waste oil (WO)** are generated annually. Improper disposal can cause severe environmental pollution—contaminating water volumes up to a million times that of the waste—and its illegal reuse poses significant public health risks. In our country, addressing the WO problem has become increasingly urgent.

**Squoilene** aims to transform WO into squalene efficiently, offering a low-cost and sustainable alternative for industrial applications. By optimizing exoenzyme activity, enhancing metabolic flux, and implementing a compartmentalized bioprocess in ***Yarrowia lipolytica***, we achieve integrated conversion of WO into high-purity squalene—realizing the combined goals of environmental protection, biomanufacturing, and advanced skincare.

## 2. Our Selection of Chassis

***Yarrowia lipolytica*** is an oleaginous yeast named for its lipolytic (fat-breaking) properties; notably, it boasts **high tolerance to salt, low & high temperatures and low pH**, granting **strong adaptability to complex, unstable environments**. This yeast also utilizes diverse substrates for growth—including WO, ethanol, glucose and glycerol—while its cytoplasm contains **abundant lipid droplets and subcellular structures**, and it further benefits from well-developed gene editing tools and a clear genetic background.


## 3. Lipase Secretion for Highly Degrade Lipids
***Thermomyces lanuginosus* lipase (TLL)** is a well-defined commercial lipase with high efficiency for lipid degradation. In this study, a recombinant plasmid containing the TLL gene sequence was kindly provided by our tutor.The core research objective was to construct a high-performance *Y. lipolytica* strain capable of strong adaptation in oily environments and efficient utilization of lipids as the sole carbon source, ultimately directing metabolic flux towards the biosynthesis of the target product.

## 4. β-oxidation Enhancement to Get Abundant Acetyl-CoA

The degradation of waste oil produces large amounts of free fatty acids, which need to undergo β-oxidation to synthesize acetyl-CoA, the precursor for squalene. To enhance the supply of precursor substances, we overexpressed the key β-oxidation enzymes **POT1, MFE2, and POX2.**
.

## 5. Mevalonate (MVA) Pathway Improvement
### 5.1 Modification of Rate-Limiting Enzymes
Through analysis of the entire MVA pathway, **HMG-CoA reductase (HMGR)** was identified as a key rate-limiting enzyme. Factors affecting its efficiency include ubiquitination degradation triggered by negative feedback from downstream products and limitation by its cofactor NADPH.  We introduced a codon-optimized **NADH-dependent HMGr** from *Silicibacter pomeroyi* and a **truncated HMGr (tHMGr)** lacking the feedback regulatory domain, thereby increasing MVA pathway flux. Using dry lab methods, we also de novo designed these enzymes to have lower free energy and increased stability.
### 5.2 Overexpression of Other Enzymes in MVA Pathway

We constructed plasmids carrying the remaining enzymes of the MVA pathway under hp4d promoters and XPR2 terminators to enhance squalene synthesis through direct overexpression.

### 5.3 Limiting Downstream Flux

We knocked out ERG1 (the first enzyme downstream of squalene cyclase) with the expectation of increasing squalene production. However, unexpectedly, the **ERG1^-^ strain** exhibited severely impaired growth and almost no proliferation in the culture medium, resulting in a reduced squalene yield.

**At this stage, the molecular engineering of squalene synthesis seems to have reached a deadlock. Those modifications are only modest improvements. Three main limiting factors were identified:**
>**1. Squalene is an intermediate, so metabolic flux is naturally directed downstream.**
>**2. Endogenous HMG-CoA reductase in *Yarrowia lipolytica* is subject to negative feedback regulation.**
>**3. High squalene accumulation may exert cytotoxic effects, reducing cellular metabolic rates.**

**Upon analyzing these constraints, we realized that they primarily occur in the cytosol. This insight naturally led to a new strategy: Relocating the squalene biosynthetic pathway via compartmentalization.**

## 6. Peroxisomal Compartmentalization

We targeted the non-HMGR enzymes of the MVA pathway, along with NADH-HMGR and tHMGR to the peroxisome to fully exploit the abundant acetyl-CoA and cofactors NADH within the peroxisome to synthesize the squalene efficiently.

Enzyme targeting was achieved using the PTS1 signal peptide. In Model, we optimized the PTS1-SKL/G4SSKL/TYWIRFSKL sequences for precise protein localization.
{% include figure.html image="https://static.igem.wiki/teams/5569/model/m02.webp" caption="Figure 1. Model design of our project" %}

## 7.Dynamic Regulation of Peroxisomes

We knocked out PEX23 (a negative regulator of peroxisomes) and overexpressed PEX10 (a protein responsible for matrix protein import) to increase peroxisome abundance and volume, thereby enhancing squalene biosynthetic capacity.


**After those design, combining efficient lipases for WO degradation with peroxisomal compartmentalization strategies markedly enhanced the capacity of *Yarrowia lipolytica* for squalene biosynthesis.**

## 8. Suicide Switch Design

We designed an innovative suicide system in which yeast survive under room light but die under sunlight or isolated blue light. Comparing room light and sunlight, we found a subtle yet critical difference: modern lamps, such as LEDs, do not emit far-red light. Blue light activates BL222, triggering CRISPR translation, whereas LexA can preemptively inhibit this process. Hsp82 and Hsc82 are essential proteins for maintaining yeast cell membrane integrity. When the kill switch is activated, CRISPR, guided by sgRNAs, targets and disrupts Hsp82 and Hsc82, leading to yeast cell death.
{% include figure.html image="https://static.igem.wiki/teams/5569/hw2/d11.webp" caption="Figure3. Suicide Switch Principle" %}

## 9. Hardware Design

During our research and experimental work, we found that laboratory-scale fermentation equipment is prohibitively expensive and unable to monitor fermentation conditions and relevant parameters in real time. Our team once conducted continuous sampling and measurements for 36 hours, a process that was labor-intensive, time-consuming, and carried a high risk of contamination, significantly reducing experimental efficiency and accuracy. To address these challenges in miniature fermentation, we developed an **Integrated Fermentation & Processing System (iFPS)**, which automates the entire workflow from inoculation to cell lysate preparation for under $100.

## 10. Beyond Squalene

The Squalene project presents a complete and feasible peroxisomal compartmentalization strategy for the MVA pathway. Using squalene as a precursor, this approach enables the construction of subcellular factories for diverse terpenoids. Compounds traditionally sourced from plants, animals, or chemical synthesis can now be produced more sustainably and reliably for the cosmetics and related industries.

Through its strategies and iterative designs for squalene biosynthesis, the project aims to inspire iGEM teams to explore the cosmetic industry and pursue innovative solutions. While practical implementation still faces challenges, we believe this initiative demonstrates the untapped potential of synthetic biology in the fashion sector and promotes greater sustainability and environmental responsibility.

