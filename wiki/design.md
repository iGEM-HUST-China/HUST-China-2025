---
title: Design
permalink: /design/
feature_text: |
feature_image: "https://static.igem.wiki/teams/5569/description/desn.webp"
excerpt: ""
---

## Welcome to iGEM HUST-China 2025 wiki!

# Design Description: Squalene Production from Waste Cooking Oil

## 1. Introduction

Squalene is a terpene compound with significant development potential. With its excellent bioactivity and safety profile, squalene is highly suitable for applications in cosmetics, food, and nutritional supplements. However, due to high production costs and complex purification processes, the widespread adoption of squalene-related products remains limited, making it difficult for the general public to access them conveniently.

Meanwhile, approximately 150 million tons of Waste Cooking Oil (WCO) are generated globally each year. Improper disposal can lead to a dual crisis: environmentally, WCO can cause water pollution, potentially affecting water volumes up to 1 million times its own weight; regarding safety, the re-entry of "gutter oil" into the food service industry poses significant public health risks. Particularly in China, the issue of WCO urgently needs addressing, both in terms of generation volume and disposal methods.

**Squoilene** is dedicated to efficiently degrading hazardous WCO and converting it into squalene, providing cosmetic manufacturers and other related industries with cost-effective squalene products that offer both strong moisturizing properties and excellent antioxidant functions. Through optimization of extracellular enzymes, enhancement of metabolic flux, and continuous advancement of compartmentalization strategies, we genetically engineer *Yarrowia lipolytica* and cultivate it using an integrated crude extraction device, ultimately achieving the triple objectives of environmental protection, biomanufacturing, and high-end skincare.

## 2. The "Squalene Alchemist" from Waste Cooking Oil: Chassis Strain Selection

*Yarrowia lipolytica* is an oleaginous yeast, named for its lipolytic (fat-decomposing) characteristics. Notably, this yeast exhibits high tolerance to salt, low temperatures, and low pH, enabling it to demonstrate strong adaptability in complex and unstable environments like WCO. Furthermore, this yeast can grow utilizing various substrates (including WCO, ethanol, glucose, and glycerol). Its cytoplasm is rich in lipid droplets and unique subcellular structures, and it also comes with a well-established set of genetic editing tools and a clear genetic background—all these features enhance its scientific research and industrial application value.

## 3. Lipase Secretion

*Thermomyces lanuginosus* lipase (Tll) is a well-characterized, mature commercial lipase known for its outstanding catalytic efficiency in lipid degradation. In this study, we first obtained a recombinant plasmid carrying the *tll* gene sequence. The core research objective was to construct a high-performance yeast strain capable of strong adaptation in oily environments and efficient utilization of lipids as the sole carbon source, ultimately directing metabolic flux towards the biosynthesis of the target product.

## 4. Enhanced Beta-Oxidation

The degradation of waste oil produces large amounts of free fatty acids, which need to undergo β-oxidation to synthesize acetyl-CoA, the precursor for squalene. To enhance the supply of precursor substances, we overexpressed the key β-oxidation enzymes POT1, MFE2, and POX2.

## 5. MVA Pathway Optimization

Through analysis of the entire MVA pathway, **HMG-CoA reductase (HMGR)** was identified as a key rate-limiting enzyme. Factors affecting its efficiency include ubiquitination degradation triggered by negative feedback from downstream products and limitation by its cofactor NADPH. HMGR is widely present in nature, providing a rich resource of variants for selection. By introducing a codon-optimized NADH-dependent HMGR from *Silicibacter pomeroyi* and a tHMGR lacking the negative feedback regulatory domain, we increased the flux through the MVA pathway and raised the squalene content. Using dry lab methods, we also de novo designed these enzymes to have lower free energy and increased stability.

Since squalene is a precursor for many terpenoids, we recognized the difficulty of accumulating large amounts of squalene in engineered bacteria. To increase squalene accumulation, we knocked out *ERG1*, the first enzyme (squalene monooxygenase) involved in the subsequent downstream reactions of squalene, expecting a significant increase in squalene yield. However, unexpectedly, the *erg1* knockout strain grew very poorly, showing almost no proliferation in the medium, and the final squalene yield even decreased.

**At this point, molecular modifications targeting squalene seemed to have reached an impasse. The improvements achieved solely by replacing the rate-limiting enzyme and modifying the lipase were not entirely satisfactory. Three factors hindered our engineering efforts:**

1.  Squalene is merely an intermediate product, so metabolic flux tends to flow downstream.
2.  The endogenous HMG-CoA reductase in yeast is subject to negative feedback regulation.
3.  Significant accumulation of squalene might produce cytotoxicity, affecting the cellular metabolic rate.

**After identifying these problems, we realized these influencing factors exist primarily in the cytosolic matrix. Thus, a new idea emerged naturally: change the location of the pathway required for squalene synthesis – compartmentalization.**

## 6. Compartmentalization

To direct enzymes into the peroxisome, we selected the PTS1 signal as the targeting peptide. Through dry lab simulations, we attempted to screen for the targeting signal sequence PTS1-SKL that achieves precise protein localization. Preliminary experiments verified that Green Fluorescent Protein (GFP) could be successfully expressed in the peroxisomes of *Yarrowia lipolytica*, laying the foundation for achieving compartmentalized synthesis. Subsequently, we added our designed SKL sequence to the target genes, aiming to successfully achieve squalene synthesis within the peroxisomes.

## 7. Peroxisome Regulation

While considering synthesizing squalene in peroxisomes, we also proposed the idea of dynamically regulating the number and size of peroxisomes. Therefore, we attempted to knock out *PEX23*, a negative regulator of peroxisomes, and overexpressed *PEX10*, a gene responsible for matrix protein import, aiming to increase the volume and number of peroxisomes, thereby further expanding the capacity for squalene synthesis.

## 8. Suicide Switch Design

**We designed an intriguing suicide system that allows the yeast to survive under indoor light but causes its death under sunlight or specific blue light. By comparing indoor light and sunlight, we identified a subtle but crucial difference: modern light sources (e.g., LEDs) do not produce far-red light. Blue light can activate BL222 to trigger the translation of the CRISPR system, while LexA can preemptively block this process. Hsp82 and Hsc82 have been confirmed as essential proteins for maintaining yeast cell membrane structure. When the kill switch is triggered, CRISPR identifies the homologous sequences of the *HSC82* and *HSP82* genes via sgRNA and knocks them out, leading to yeast death.**

## 9. Hardware Design

**During our research and experimental process, we found that laboratory-scale micro-fermentation equipment is very expensive and still cannot monitor fermentation conditions and relevant parameters in real-time. Our team members once spent 36 hours continuously sampling and measuring data. This process was not only cumbersome and time-consuming but also posed a significant contamination risk, greatly reducing experimental efficiency and accuracy. To address this issue in the field of micro-fermentation, we integrated and built an Integrated Fermentation & Processing System (iFPS), achieving full automation from "post-inoculation" to "lysis-ready" for less than $100.**

## 10. Beyond Squalene

The Squoilene project provides a complete and feasible compartmentalization strategy for the MVA pathway. Using squalene as a precursor, numerous terpenoids have the potential to be produced through the construction of subcellular factories using compartmentalization strategies. Many terpenes currently sourced from plants, animals, or the chemical industry for cosmetics and other sectors could be obtained in a more environmentally friendly and stable manner. We hope that the strategies and iterative solutions developed by Squoilene for squalene synthesis will inspire more iGEM teams to focus on the cosmetics industry and motivate them to undertake more creative work. Although many factors still affect practical application, we believe this will unlock the often-overlooked potential of synthetic biology in the fashion field and promote the greening and sustainability of the fashion industry.

---
**Design Description: Mature Design**
