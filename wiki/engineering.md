---
title: Engineering
permalink: /engineering/
feature_text: |
  ## Engineering
  This page contains information about the engineering of our project.
feature_image: "https://static.igem.wiki/teams/5175/resources/background/bg-engineering.webp"
excerpt: "This page contains information about the engineering of HUST-China 2024."
---

## Introduction

We want to alleviate the problem of microplastic pollution by degrading PET hidden in the irrigation water. We also want to produce rhamnolipid which is beneficial to the soil fertility to improve the soil environment. To this end, we designed three system paths and chose two kinds of chassis bacterias, *E. coli* BL21 and *P. putida* KT2440. In the construction stage, we used homologous recombination and double enzyme digestion to construct the pathway. Although we encountered some problems, we finally achieved certain results by doing continuous attempts and summaries.

## Cycle 1

**Constructing by the homologous recombination and double enzyme digestion.**

### Design

To construct a well-functioning systemic pathway, we hope to use one plasmid to enable *E. coli* BL21 to degrade PET and enhance its own metabolic capacity. We also wish to use two plasmids to provide *P. putida* KT2440 the ability to degrade the PET-breakdown-product "terephthalic acid" and secrete rhamnolipid. Based on the existing parts with independent functions, we achieved our goals by connecting multiple components to form a fully functional system pathway.

#### *E. coli*

In order to realize the ideal function of *E. coli* BL21 which is to degrade PET and enhance its own metabolic capacity, we wanted to use homologous recombination to build our fully functional plasmids. We first obtained fragments and vectors with homologous arms by PCR, and then used homologous recombination to connect the corresponding homologous vector and fragments together.

In the first step, we inserted homologous arms at both ends of the target gene fragment as well as the linearized vector fragment. In the pPeteg pathway, we begin by incorporating the first homologous arm downstream of the PETase-MHETase vector fragment and upstream of aldA-fucO. Following that, a second homologous arm is introduced downstream of aldA-fucO and upstream of the PETase-MHETase vector fragment.

In the second step, we used the homologous recombinase to directly link the linearized vector PETase-MHETase with the aldA-fucO fragment to construct a complete plasmid.

#### *P. putida*

To achieve the ideal function of *P. putida* KT2440 in degrading the PET-breakdown-product "terephthalic acid" and produce rhamnolipid, we decided to use double enzyme digestion to construct our plasmids. We first perform double enzyme digestion to obtain multiple fragments and vectors with the same sticky ends, and then ligate the vectors and fragments containing the same sticky ends together by performing ligation.

In the first step, we use the double enzyme digestion to obtain the target gene fragments and the vector fragment with the same sticky ends. We first culture *E. coli* DH5$\alpha$ containing the basic component and extract the plasmid. Then we obtain the target gene fragment and the vector fragment with the same sticky ends by double enzyme digestion.

In the second step, we used ligation to link the target gene fragment and its corresponding vector fragment with the same sticky ends together, then a complete plasmid would be constructed.

### Build

#### *E. coli* BL21

Based on the principle of seamless cloning, we tried to use homologous recombinase to attach the target gene fragment directly into the vector to form a complete plasmid.

In the pathway pPeteg: First, the linearized vector fragment PETase-MHETase and the gene fragment aldA-fucO were obtained respectively by reverse PCR and PCR. They were then etracted and purified by agarose gel extraction. Finally, homologous recombinase was used to connect PETase-MHETase with aldA-fucO to construct a complete system pathway. Next, we transferred the constructed plasmid into *E. coli* DH5$\alpha$ and inoculated it onto an LB plate containing kanamycin. Then, the solid medium was placed in a 37 °C incubator for overnight incubation at a constant temperature. Subsequently, we picked bacterial plaque for PCR verification. After observing the correct bands, we mixed 800 $\mathrm{\mu L}$ of bacterial solution with 800 $\mathrm{\mu L}$ of 1:1 mixture of glycerol and double distilled water, and we stored the seeds at -20 °C.

{% include figure.html image="https://static.igem.wiki/teams/5175/resources/engineering/engineering-01-new.png" alt=" " caption="Fig 1. The diagram of constructing the plasmid inserted with pPeteg by homologous recombination" %}

{% include figure.html image="https://static.igem.wiki/teams/5175/resources/engineering/engineering-02-new.png" alt=" " caption="Fig 2. The diagram of constructing the plasmid inserted with phaZ-pVLT33 by double enzyme digestion and enzyme ligation" %}

#### *P. putida* KT2440

Our basic process of constructing a complete plasmid is: extract the plasmid, obtain the fragment of the target gene with sticky ends through double enzyme digestion, and perform ligation to link the target gene to the vector.

Take the pTerephthalate system pathway(Here tells the way we construct pTerephthalate by using plasmid tphA2A3BA1-pUC57 and plasmid tpak-pUC57. Tt's the same principle as constructing by using plasmid tphA2A3A1-pUC57 and plasmid tphB-tpaK-pUC57.) as an example. Initially, we separately cultured *E. coli* DH5$\alpha$(tphA2A3BA1-pUC57), *E. coli* DH5$\alpha$ (tpaK-pUC57) and *E. coli* DH5$\alpha$ (pBBR1-CS2), then we extracted the plasmids. After that, We used double enzyme digestion on the plasmids tphA2A3BA1-pUC57 and pBBR1-CS2 with restriction endonucleases *Xho* I and *EcoR* I for 30 minutes. Then we used double enzyme digestion on plasmids tpaK-pUC57 and pBBR1-CS2 with restriction endonucleases *Spe* I and *EcoR* I for 30 minutes. Next we verified and purified them through agarose gel extraction to obtain the target gene fragment and vector fragment with the same sticky ends. We have constructed the plasmids tphA2A3BA1-pBBR1-CS2 and tpaK-pBBR1-CS2 through ligation. Next, we transferred the constructed plasmid into *E. coli* DH5$\alpha$ and inoculated it onto an LB plate containing kanamycin. Then, the solid medium was placed in a 37 °C incubator for overnight incubation at a constant temperature. Subsequently, we picked bacterial plaque for PCR verification. After observing the correct bands, we mixed 800 $\mathrm{\mu L}$ of bacterial solution with 800 $\mathrm{\mu L}$ of 1:1 mixture of glycerol and double distilled water, and we stored the seeds at -20°C.

After that, We used double enzyme digestion on the plasmids tphA2A3BA1-pUC57 and tpaK-pBBR1CS-2 with restriction endonucleases *Xho* I and *EcoR* I for 30 minutes. And we use double enzyme digestion on the plasmids tpaK-pUC57 and the tphA2A3BA1-pBBR1-CS2 with restriction endonucleases *Spe* I and *EcoR* I for 30 minutes. We then verified and purified them through agarose gel extraction. Unfortunately, we did not find the target band.

### Results

We successfully constructed plasmids pPeteg, phaZ-pVLT33, tphA2A3BA1-pBBR1-CS2 and tpak- pBBR1-CS2.

{% include figure.html image="https://static.igem.wiki/teams/5175/resources/engineering/engineering-01.png" alt="The results of PCR identification for pPeteg and phaZ-pVLT33" caption="Fig 3. The results of PCR identification for pPeteg (left) and phaZ-pVLT33 (right)" %}

In Fig.3, the left sub-figure is the result of PCR identification of plasmid pPeteg, it shows that there is a bright band at about 2900 bp, and the length of the fragment we obtained by PCR using the primers we designed should be 2862 bp, which proves that we have successfully constructed the plasmid PETase-MHETase -aldA-fucO.

The right sub-figure of Fig.3 is the result of PCR identification of phaZ-pVLT33 plasmid. It shows that there is a bright band at about 800 bp, and the length of the fragment we obtained by PCR using the primers we designed should be 867 bp, which proves that we have successfully constructed the plasmid of phaZ-pVLT33 system pathway.

{% include figure.html image="https://static.igem.wiki/teams/5175/resources/engineering/engineering-02.png" alt="The results of PCR identification for tphA2A3BA1-pBBR1CS-2 and tpaK-pBBR1CS-2" caption="Fig 4. The results of PCR identification for tphA2A3BA1-pBBR1CS-2 (left) and tpaK-pBBR1CS-2 (right)" %}

In Fig.4, the left sub-figure is the result of PCR identification of tphA2A3BA1-pBBR1CS-2 plasmid. It shows that there is a bright band at about 4000 bp, and the length of the fragment we obtained by PCR using the primers we designed should be 4213 bp, which proves that we have successfully constructed the plasmid of tphA2A3BA1-pBBR1CS-2 system pathway.

The right sub-figure of Fig.4 is the result of PCR identification of tpak- pBBR1-CS2 plasmid. It shows that there is a bright band at about 1500 bp, and the length of the fragment we obtained by PCR using the primers we designed should be 1634 bp, which proves that we have successfully constructed the plasmid of tpak- pBBR1-CS2 system pathway.

### Experience

After many attempts, in the process of double enzyme digestion, we found that directly conducting double enzyme digestion on the original plasmid was not suitable for all pathways, and we could not successfully construct pathways rhlA-rhlB-pVLT33 and pTerephthalate. We have carefully analyzed and summarized the reasons for the failure.

First, when constructing the pathway rhlA-rhlB-pVLT33, the length of rhlA-rhlB gene fragment was too close to the length of the pUC57 vector fragment, and it was difficult to obtain pure rhlA-rhlB fragments in the process of agarose gel extraction. Therefore, we tried to obtain the rhlA-rhlB fragment by PCR and then use double enzyme digestion to obtain the rhlA-rhlB fragment with sticky ends.

Furthermore, the tpak-pBBR 1-CS2 fragment obtained by our double enzyme digestion was always too small and had multiple wrong bands. We suspect that it is due to an error while designing the plasmid tpak-pUC57. We might designed excess restriction sites on the tpak gene fragment. Therefore, we attempted to replace the restriction endonuclease we used to solve this problem.

## Cycle 2

**Obtaining the target fragment through PCR technology and changing restriction endonucleases.**

### Design

After encountered many failures and did several attempts, we analysed the problems in the first cycle and have come up with ideas to solue them.

When constructing the plasmid rhlA-rhlB-pVLT33,we tried to obtain the linearized rhlA-rhlB fragment by PCR first, and then perform double enzyme digestion on the rhlA-rhlB fragment , so as to solve the problem that it is difficult to obtain the pure rhlA-rhlB fragment due to the similar length of the rhlA-rhlB gene fragment and the original pUC57 vector in plasmid rhlA-rhlB-pUC57.

When constructing the plasmid pTerephthalate, in the first phase of the process, we perfrmed double enzyme digested on plasmid tpak-pBBR1-CS2 to obtain the linearized target vector. However, after multiple attempts, we consistently observed that the size of the obtained tpak-pBBR1-CS2 fragment was smaller than expected. We suspect that this was due to an error while we were designing our the plasmid, specifically, an inclusion of redundant restriction enzyme sites within the tpak gene fragment. To address this issue, we attempted to select new restriction endonucleases for double enzyme digestion. By designing primers, we used PCR technology to add restriction enzyme sites for *Sal* I and *EcoR* I on both ends of the tphA2A3BA1 gene fragment. Following this, we performed double enzyme digestion reaction on both the tphA2A3BA1 fragment and plasmid tpak-pBBR1-CS2, and then ligated the two fragments together to obtain the pTerephthalate system.

{% include figure.html image="https://static.igem.wiki/teams/5175/resources/engineering/engineering-05-new.png" alt=" " caption="Fig 5. The diagram of constructing the plasmid inserted with pTerephthalate by double enzyme digestion and enzyme ligation" %}

{% include figure.html image="https://static.igem.wiki/teams/5175/resources/engineering/engineering-06-new.png" alt=" " caption="Fig 6. The diagram of constructing the plasmid inserted with rhlA-rhlB-pVLT33 by double enzyme digestion and enzyme ligation" %}

### Build

#### rhlA-rhlB-pVLT33 pathway

Initially, we separately cultured two strains of *E. coli* DH5$\alpha$ (rhlA-rhlB-pUC57) and *E. coli* DH5$\alpha$ (pVLT33) and extracted the plasmids. Then, we obtained the linearized rhlA-rhlB gene fragment from the plasmid rhlA-rhlB-pUC57 by PCR. After that, We used double enzyme digestion on the rhlA-rhlB fragment and the vector pVLT33 with restriction endonucleases *Sac* I and *EcoR* I for 30 minutes, then verified and purified them through agarose gel extraction to obtain the target gene fragment and vector fragment with the same sticky ends.  We have constructed the rhlA-rhlB-pVLT33 plasmid through enzyme ligation reaction. Next, we transferred the constructed plasmid into *E. coli* DH5$\alpha$ and inoculated it onto an LB plate containing kanamycin. Then, the solid medium was placed in a 37 °C incubator for overnight incubation at a constant temperature. Subsequently, we selected individual colonies for PCR verification. After observing the correct bands, we mixed 800 $\mathrm{\mu L}$ of the bacterial solution with 800 $\mathrm{\mu L}$ of 1:1 mixture of glycerol and double distilled water, then we stored the seeds at -20 °C.

#### pTerephthalate pathway

To solve this problem, we attempted to select new restriction endonucleases for double enzyme digestion. First, we designed primers and used PCR to add restriction enzyme sites for *Sal* I and *EcoR* I at both ends of the tphA2A3BA1 gene fragment. Subsequently, we performed double enzyme digestion on both the tphA2A3BA1 fragment and the tpak-pBBR1-CS2 using the restriction endonucleases *Sal* I and *EcoR* I for 30 minutes. Following the digestion, we performed agarose gel recovery to purify and isolate the target gene fragment and vector fragment, ensuring they possessed identical cohesive ends. Then we constructed the pTerephthalate plasmid through ligation. Next, we transferred the constructed plasmid into *E. coli* DH5$\alpha$ and inoculated it onto an LB plate containing kanamycin. Then, the solid medium was placed in a 37 °C incubator for overnight incubation at a constant temperature. Subsequently, we selected individual colonies for PCR verification. After observing the correct bands, we mixed 800 $\mathrm{\mu L}$ of bacterial solution with 800 $\mathrm{\mu L}$ of 1:1 mixture of glycerol and double distilled water, and we stored the seeds at -20 °C.

### Results

After several attempts, we successfully constructed plasmids rhlA-rhlB-pVLT33 and pTerephthalate.

{% include figure.html image="https://static.igem.wiki/teams/5175/resources/engineering/engineering-03.png" alt="The results of PCR identification for tphA2A3BA1-pBBR1CS-2 and tpaK-pBBR1CS-2" caption="Fig.7 The results of PCR identification for pTerephthalate (left) and rhlA-rhlB-pVLT33 (right)" %}

In Fig.3, the left figure is the result of PCR identification of plasmid pTerephthalate. It shows that there is a bright band at about 3000 bp, and the length of the fragment we obtained by PCR using the primers we designed should be 2971 bp, which proves that we have successfully constructed the plasmid of pTerephthalate system pathway.

The right figure of fig.7 is the result of PCR identification of rhlA-rhlB-pVLT33 plasmid. It shows that there is a bright band at about 2500 bp, and the length of the fragment we obtained by PCR using the primers we designed should be 2452 bp, which proves that we have successfully constructed the plasmid of rhlA-rhlB-pVLT33 system pathway.

### Experience

Initially, during the process of directly performing double enzyme digestion on the original plasmid to obtain at the linearized target vector, we encountered the problem that the size of the target vector we obtained was consistently too small. Upon examining the base sequence of the gene, we discovered that this was due to an error in our plasmid designing, specifically, the inclusion of redundant restriction enzyme sites within the tpak gene fragment. Consequently, we attempted to resolve this issue by selecting new restriction endonucleases for double enzyme digestion. Ultimately, our revised experimental protocol proved effective, and we successfully constructed the complete pathway pTerephthalate.

In addition, due to the low activity and low amplification efficiency of the vector pVLT33, the ligation efficiency between pVLT33 and phaZ and rhlA-rhlB is low. We spent too much time on constructing plasmids phaZ-pVLT33 and rhlA-rhlB-pVLT33, and we were unable to construct the plasmid phaZ-rhlA-rhlB within the limited time. We would working on finding a way to increase the activity of pVLT33 in the future.

## Cycle 3

**Expression Validation**

### *E. coli* BL21

#### Design

We aimed to validate the efficiency of *E. coli* BL21 engineered bacteria in degrading PET, and we'd test the promotion on the growth and metabolic capacity of *E. coli* BL21 engineered bacteria provided by ethylene glycol. Therefore, we measured the enzymatic activity of FAST-PETase-MHETase expressed by engineered bacteria *E. coli* BL21. We also monitored the growth of *E. coli* BL21 engineered bacteria in M9 medium with ethylene glycol and glycerol as the carbon sources, then we drew the growth curve.

#### Build

First, we cultured *E. coli* DH5$\alpha$ (PETase-MHETase-aldA-fucO) and extracted plasmids. Then, we transferred the extracted plasmids into *E. coli* BL21 and inoculated them onto LB plates containing kanamycin. We incubated the solid culture medium at 37 °C overnight, and then picked bacterial plaque for PCR verification. After observing the correct bands, we mixed 800 $\mathrm{\mu L}$ of bacterial solution with 800 $\mathrm{\mu L}$ of 1:1 mixture of glycerol and double distilled water, and we stored the seeds at -20 °C.

#### Test

Our plasmids were successfully transferred to *E. coli* BL21.

After observing the correct and bright bands in the PCR verification of colonies, we cultured and expanded the bacteria plaque and stored the bacterial solution for future expansion and induction of expression.

We cultured *E. coli* BL21 (PETase-MHETase), *E. coli* BL21 (MHETase-PETase), *E. coli* BL21 (pPeteg), and *E. coli* BL21 (pUC19) in M9 culture medium containing ethylene glycol and glycerol as carbon sources.

We first verified the efficiency of *E. coli* BL21 engineered bacteria in degrading PET, specifically by inoculating *E. coli* BL21 (PETase-MHETase), *E. coli* BL21 (MHETase-PETase) and *E. coli* BL21 (pUC19) into LB liquid culture medium containing kanamycin and added IPTG during the logarithmic growth phase ($\mathrm{OD_{600}}$=0.6-0.8).  We cultured the strains for 2 days at 16 °C and 200 rpm. Then, we performed nickel affinity chromatography and SDS-PAGE gel electrophoresis on the supernatant of the culture medium. We did not observe the correct bands. We repeated the nickel affinity chromatography and SDS-PAGE gel electrophoresis on the cell lysate and the precipitate, and finally observed the correct bands.

{% include figure.html image="https://static.igem.wiki/teams/5175/resources/engineering/engineering-08.png" alt="SDS-PAGE gel electrophoresis of <em>E. coli</em> BL21 (PETase-MHETase) and <em>E. coli</em> BL21 (MHETase-PETase)" caption="Fig 8. The results of SDS-PAGE gel electrophoresis for the cell pellet, supernatant and cultural media of <em>E. coli</em> BL21 (PETase-MHETase) and <em>E. coli</em> BL21 (MHETase-PETase)" %}

We believe that the FAST-PETase-MHETase is not excreted, so we wanted to determine the efficiency of the enzyme in degrading PET by directly detecting the activity of the crude enzyme solution. We induced the growth of the engineered bacteria at low temperature, then lysed the cell suspension and concentrated the supernatant to prepare the crude enzyme solution. We incubated the crude enzyme solution with PET powder for several days and detected the degration of PET by using HPLC. We found that the FAST-PETase-MHETase expressed by our engineered bacteria has achieved the expected efficiency in degrading PET.

{% include figure.html image="https://static.igem.wiki/teams/5175/resources/engineering/engineering-09.png" alt="The HPLC-MS results for FAST-PETase-MHETase, MHETase-FAST-PETase, and the control group" caption="Fig 9. The HPLC-MS results for FAST-PETase-MHETase, MHETase-FAST-PETase, and the control group" %}

We also investigated the promotion of growth and metabolic capacity of *E. coli* BL21 by ethylene glycol. We measured the growth and metabolic capacity of *E. coli* BL21 (pPeteg) and *E. coli* BL21 (pUC19) and drew the growth curves. Compared to *E. coli* BL21 (pUC19), the concentration of *E. coli* BL21 (PETase-MHETase-aldA-fucO) was higher at all stages, and the growth rate was not significantly reduced. This indicates that fucO-aldA can promote *E. coli* BL21's utilization of ethylene glycol and improve its metabolic efficiency, thereby promoting cell growth better. This proves that the gene aldA-fucO has successfully transferred into *E. coli* BL21 and can be effectively expressed.

{% include figure.html image="https://static.igem.wiki/teams/5175/resources/engineering/engineering-10.png" alt="Growth Curves of <em>E. coli</em> BL21" caption="Fig 10. Growth curves for wild-type (WT) <em>E. coli</em> and engineered <em>E. coli</em> (aldA-fucO) utilizing ethylene glycol (EG) as the sole carbon source" %}

### *P. putida* KT2440

#### Design

We wanted to verify the ability of the engineered *P. putida* KT2440 to degrade terephthalic acid, and to test if the engineered *P. putida* KT2440 was consistent with our expectations to produce rhamnolipid by using TCL and anthrone-sulfuric acid method to detect the expression of rhamnolipid.

#### Build

First, we cultured *E. coli* DH5$\alpha$ (pTerephthalate) and *E. coli* DH5$\alpha$ (rhlA-rhlB-pVLT33) and extracted plasmids. Then, we transferred the 2 plasmids separately to *P. putida* KT2440 via electroporation and plated each of the strain on 1 LB plate containing kanamycin for selection. We then incubated the solid culture medium at 30 °C for overnight cultivation, and then picked bacterial plaque for PCR verification. After observing the correct bands, we mixed 800 $\mathrm{\mu L}$ of bacterial solution with 800 $\mathrm{\mu L}$ of 1:1 mixture of glycerol and double distilled water, and we stored the seeds at -20 °C.

#### Test

Our plasmids were successfully transferred into *P. putida* KT2440.

After the correct and bright bands showed on the results of PCR identification, we cultured and expanded the bacterial plaque and stored the bacterial solution for future expansion and induction of expression.

We inoculated 1% of *P. putida* KT2440 (pTerephthalate) and 1% of *P. putida* KT2440 (pBBR1-CS2) in M9 medium with terephthalic acid as the carbon source.

We detected the growth of *P. putida* KT2440 (pTerephthalate) and *P. putida* KT2440 (pBBR1-CS2) and drew the growth curves. The cell concentrations of both strains were almost constant at all stages and were close to zero. We suspected that pTerephthalate conferred limited ability to degrade terephthalic acid to *P. putida* KT2440, and it was difficult to observe significant differences in growth between *P. putida* KT2440 (pTerephthalate) and *P. putida* KT2440 (pBBR1-CS2) when inoculated at 1% concentration of *P. putida* KT2440.

Therefore, we increased the inoculation concentration of *P. putida* KT2440 to 10% and cultured *P. putida* KT2440 (pTerephthalate) and *P. putida* KT2440 (pBBR1-CS2) in M9 medium with terephthalic acid as the carbon source. Then we measured the growth of *P. putida* KT2440 (pTerephthalate) and *P. putida* KT2440 (pBBR1-CS2) and drew the growth curves. Compared to *P. putida* KT2440 (pBBR1-CS2), the cell concentration of *P. putida* KT2440 (pTerephthalate) remained relatively constant at all stages, while the cell concentration of *P. putida* KT2440 (pBBR1-CS2) decreased gradually. This indicates that pTerephthalate can endow *P. putida* KT2440 with the ability to degrade terephthalic acid to enhance its metabolism, proving that the gene pTerephthalate transferred to *P. putida* KT2440 can be effectively expressed.

{% include figure.html image="https://static.igem.wiki/teams/5175/resources/engineering/engineering-11.png" alt="Growth Curves of <em>P. putida</em> KT2440" caption="Fig 11. Growth Curves of <em>P. putida</em> KT2440 (pTerephthalate-A), (pTerephthalate-B), and Empty Vector (pBBR1-CS2) Utilizing Terephthalic Acid (TPA) as Carbon Source" %}

Additionally, we collected the suspensions of *P. putida* KT2440 (pTerephthalate) and *P. putida* KT2440 (pBBR1-CS2) that we cultured and detected the remaining terephthalic acid content in the samples by HPLC.

Based on the data, we believe that the efficiency of our engineered strain in degrading terephthalic acid is consistent with our expectation.

---

We also validated the efficiency of our engineered *P. putida* KT2440 (rhlA-rhlB-pVLT33) to produce rhamnolipid. We cultured *P. putida* KT2440 (rhlA-rhlB-pVLT33) and *P. putida* KT2440 (pVLT33) in M9 medium supplemented with soybean reconciled oil as the carbon source. 

We used anthrone-sulfuric acid method to test the ability of our engineered cells to produce rhamnolipid. We sampled a certain amount of the cultured *P. putida* KT2440 (rhlA-rhlB-pVLT33) and *P. putida* KT2440 (pVLT33) for several days and added anthrone-sulfuric acid. We applied TCL to test the ability of our engineered cells to produce rhamnolipid. Based on the data, we believe that the amount of rhamnolipid produced by our engineered strain is consistent with the expected value.

{% include figure.html image="https://static.igem.wiki/teams/5175/resources/engineering/engineering-12.png" alt="Determination of Rhamnolipid Content in <em>P. putida</em> KT2440" caption="Fig 12. Determination of Rhamnolipid Content in <em>P. putida</em> KT2440 (rhlA-rhlB) and Empty Vector (WT) Using the Sulfuric Acid-Anthrone Method" %}
