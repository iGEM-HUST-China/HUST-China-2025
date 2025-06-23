---
title: Contribution
permalink: /contribution/
feature_text: |
  ## Contribution
  This page contains the contribution of the project.
feature_image: "https://static.igem.wiki/teams/5175/resources/background/bg-contribution.jpg"
excerpt: "This page contains the contribution of the project."
---

## Introduction

This year, our team focused on designing a metabolic coupling system to co-culture *E. coli* BL21 and *P. putida* KT2440 to reduce the content of microplastics in the soil, thus realizing the aim of improving the ability for crops to effectively absorb nutrients and water and increasing the crop yields. We successfully constructed a two-bacterium co-culture system that enabled *E. coli* BL21 to degrade PET in high efficiency while enhancing the ability of *P. putida* KT2440 to produce rhamnolipid. Additionally, we developed a microplastic enrichment device and a two-bacterium co-culture fermenter system in terms of hardware. Furthermore, we would like to share some of our wet lab experiences for future iGEM teams to reference.

## Parts

These parts are crucial for gene expression. Our project has registered several components, all of which meet the RFC standardization requirements. By combining the following parts, we try to promote the degradation efficiency of PET and increase the expression of the final products.

###  *E. coli* BL21

**pT7-lac operator-PETase-MHETase-T7-pT7 -aldA-fucO -T7**

Consisting of PETase-MHETase and aldA-fucO, it is used to introduce the PET degradation pathway into *E.coli* BL21. Hence, *E. coli* BL21 can degrade PET polymers into monomers TPA (terephthalic acid) and EG (ethylene glycol), which can be absorbed and utilized by our engineered bacteria. In addition, we overexpressed the EG-utilizing pathway (aldA-fucO) to enhance the viability of *E. coli*. Meanwhile, the G4S flexible peptide was selected as the linker of FAST-PETase and MHETase to form a double enzyme system. This configuration significantly reduces the diffusion barrier between the active sites of the enzyme, thereby promoting their synergistic effect and improving the catalytic efficiency.

###  *P. putida* KT2440 

 **pT7-tphA2-tphA3-tphB-tphA1-T7-pT7-tpaK-T7** 

We designed this plasmid to enable *P. putida* KT2440 to autonomously transport TPA into the cell and participate in metabolic pathways. TPA 1,2-dioxygenase (TPADO) can effectively catalyze the oxidation of TPA through the synergistic action of TphA1, TphA2 and TphA3, transforming TPA into the intermediate product 1,2-dihydroxy-3,5-cyclohexadiene-1,4-dicarboxylic acid (DCD). TphB can further oxidize DCD to produce PCA. Given the slow passive diffusion of aromatic carboxylates across the phospholipid bilayer of bacterial endomembrane, we introduced TpaK as a TPA transporter for application in engineered *P. putida* KT2440.

**pT7-lac operator- Rrhla-Rlb-T7-PT7-lac operator-phaZ-T7** 

The synergistic effect of rhlA and rhlB enables *P. putida* KT2440 to accumulate rhamnolipids during metabolism. In order to increase the proportion of carbon sources used by *P. putida* KT2440 for rhamnolipid synthesis, we overexpressed the gene phaZ, which encodes poly(3-hydroxyalkanoate) depolymerase. Consequently, the anabolic pathway of PHA was inhibited, leading an increased production of rhamnolipids.

## Wet lab experience

### Genetic Engineering

Initially,to enable *E. coli* BL21 to degrade PET and enhance its own metabolic capacity, we hope to construct the plasmid we need through homologous recombination. We first obtained multiple pairs of homologous arms via PCR, and then connected the corresponding vectors and fragments through homologous recombination. To harness the capabilities of *P. putida* KT2440 in degrading the PET-breakdown product "terephthalic acid" and producing rhamnolipid, we planned to construct our plasmids using double enzyme digestion. We began by performing double enzyme digestion to obtain multiple pairs of fragments and vectors with compatible sticky ends, followed by ligating the vectors and fragments with the same sticky ends together.

However, after numerous attempts during the process of double enzyme digestion, we discovered that directly performing double enzyme digestion on the original plasmid was not suitable for all pathways, and we were unable to successfully construct rhlA-rhlB-pVLT33 and pTerephthalate pathways. Considering that there were redundant restriction sites on the target gene fragment while we were constructing pTerephthalate and the lengths of the two fragments obtained from the double enzyme digestion of the original plasmid during the construction of rhlA-rhlB-pVLT33 were too close, we could not successfully construct the plasmids pTerephthalate and pRhamnolipid. Soon, for the first case, we changed the restriction endonuclease we used. For the second case, we obtained the linearized target fragment from the original plasmid by PCR, and then performed double enzyme digestion and digestion to solve the above two problems, and finally, we successfully obtained plasmid pPeteg, pTerephthalate, phaZ-pVLT33 and rhl-pVLT33.

### Engineered Bacteria

This year, we selected two chassis organisms, *E. coli* BL21 and *P. putida* KT2440. *E. coli* BL21 is a commonly used chassis for the secretion of heterologous proteins, while *P. putida* KT2440 is widely utilized in scientific research and environmental management. Although both strains have been studied to some extent, we continue to explore their biological modification methods and the construction of co-culture systems.

For *E. coli* BL21, we hope it will be able to exfiltrate the FAST-PETase-MHETase double enzyme system to degrade PET microplastics in the soil. To achieve this, we utilized the pelB signal peptide to improve BL21's ability to secrete FAST-PETase-MHETase. Furthermore, to improve expression levels, we selected the strong T7 promoter to initiate the expression of protein FATS-PETase and MHETase, thereby increasing the expression efficiency of the FAST-PETase-MHETase double enzyme system.

*P. putida* KT2440 is less commonly used as an engineered strain compared to *E. coli*. Due to the lack of competent cell for *P. putida* KT2440, we thoroughly consulted the relevant information in the initial stages of our research. Ultimately, we opted to employ electroporation to introduce our plasmids into *P. putida* KT2440. Throughout our exploration, we systematically identified the optimal electroporation conditions for this strain, which enabled us to successfully transfer the plasmid into *P. putida* KT2440. Finally, we assessed the degradation of terephthalic acid and the production of intracellular rhamnolipids in *P. putida* KT2440, thus verifying the function of the imported plasmids.

## Hardware

In the process of designing and researching our project, we realized that co-culture of multiple bacterias is becoming more and more common in synthetic biology, and how to achieve culture of different strains at different optimal growth temperatures remains a major challenge to be solved in current hardware designing. For our double-bacteria co-culture system, we first tried to design two tank fermenters connected by the middle pipeline. Later, we investigated the fermentation equipment of some biological companies, rationally reformed the three-dimensional form of the fermenter, and proposed a set of two-way flow temperature control system, so as to build a set of double-bacteria co-culture fermentation system. We hope that this bidirectional flow temperature control system will offer innovative solutions for hardware designing in synthetic biology, bridge the gap between synthetic biology and industrial production, and promote the application and development of synthetic biology.
