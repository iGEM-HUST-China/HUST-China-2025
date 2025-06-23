---
title: Results
permalink: /results/
feature_text: |
  ## Results
  This page contains the results of our project.
feature_image: https://static.igem.wiki/teams/5175/resources/background/bg-results.jpg
excerpt: "This page contains the results of our project."
---

## Introduction 

Our project aims to enable *Escherichia coli* BL21 to efficiently degrade polyethylene terephthalate (PET) into terephthalic acid (TPA) and ethylene glycol (EG) while utilizing the EG for energy. Additionally, we seek to confer the ability to utilize TPA and produce rhamnolipid on *Pseudomonas putida* KT2440. To achieve these objectives, we primarily constructed four plasmids: pPeteg-P and pPeteg-M for *E. coli* BL21, and pTerephthalate and pRhamnolipid for *P. putida* KT2440. In addition to these four main plasmids, we also developed five additional plasmids to facilitate more convenient testing of gene functions.

We transferred these plasmids into *E. coli* BL21 and *P. putida* KT2440 to express the desired proteins. Concurrently, we conducted comprehensive investigations to validate the efficiency of PET degradation and the production efficiency of rhamnolipid.

We proved the expression of the target protein by ultrasonic cell fragmentation, nickel column affinity chromatography and SDS-PAGE, meanwhile, we incubated PET by cell fragmentation solution, and detected the content of the degradation product, TPA, after three days of incubation by HPLC-MS, and finally 50 mL of the bacterial solution degraded 0.3 g/L of PET, meanwhile, we also detected the engineered odour pseudo by sulphuric acid-anthracene ketone method. The total sugar content of the engineered *P.putida* was significantly increased, indicating the production of rhamnolipids. With the two engineered bacteria, we achieved the in situ degradation of PET and the secretion of rhamnolipids in order to improve the yield of the crops and to promote agricultural production 

## Plasmid Amplification and Reconstruction

Initially, we transformed the company-synthesized plasmids containing designed sequences into *E. coli* DH5α for amplification, allowing us to obtain a sufficient quantity of plasmid DNA for subsequent experiments. Following this, colony PCR was performed to confirm successful transformation, and the required plasmids were subsequently extracted for further experimentation.

Subsequently, we employed PCR to obtain the target fragments, which were then integrated into the requisite plasmids for our study.

###  Plasmids of *E. coli* BL21

We constructed two plasmids, pPeteg-P and pPeteg-M, for *E. coli* BL21 to assess the activity of different dual enzyme systems in engineered *E. coli*. We verified the size of the plasmids as well as all the fragments involved in constructing the plasmids . In addition to pPeteg-P and pPeteg-M, we also developed FAST-PETase-MHETase (pPM), MHETase-FAST-PETase (pMP), and T7-fucO-aldA (pEG) to independently validate their function.

The pPeteg-P/pPeteg-M plasmids contain the constructs pelB-PETase-G4S-MHETase and pelB-MHETase-G4S-FAST-PETase (using pelB-PETase-G4S-MHETase as an example), along with aldA and fucO. The pelB-PETase-G4S-MHETase enables *E. coli* BL21 to secrete FAST-PETase-G4S-MHETase, degrading PET into TPA and EG, while the aldA-fucO converts EG into GA to enhance the absorption and utilization of EG.

<figcaption class="caption table_caption">Table 1. Plasmids of <em>E. coli</em> BL21</figcaption>

  <table>
    <tr>
      <th>Plasmids</th>
      <th>Expected size(bp)</th>
      <th>Fragments</th>
      <th>Expected size(bp)</th>
    </tr>
    <tr>
      <td rowspan="2">pPeteg-P</td>
      <td rowspan="2">10712</td>
      <td>T7 promoter-lac operator-pelB-FAST-PETase-G4S-MHETase-T7 terminator</td>
      <td>2682</td>
    </tr>
    <tr>
      <td>T7 promoter-fucO-aldA-T7 terminator</td>
      <td>2862</td>
    </tr>
    <tr>
      <td rowspan="2">pPeteg-M</td>
      <td rowspan="2">10736</td>
      <td>T7 promoter-lac operator-pelB -G4S-MHETase-FAST-PETase -T7 terminator</td>
      <td>2682</td>
    </tr>
    <tr>
      <td>T7 promoter-fucO-aldA-T7 terminator</td>
      <td>2862</td>
    </tr>
    <tr>
      <td>pPM</td>
      <td>7892</td>
      <td>T7 promoter-lac operator-pelB-FAST-PETase-G4S-MHETase-T7 terminator</td>
      <td>2682</td>
    </tr>
    <tr>
      <td>pMP</td>
      <td>7915</td>
      <td>T7 promoter-lac operator-pelB -G4S-MHETase-FAST-PETase -T7 terminator</td>
      <td>2682</td>
    </tr>
    <tr>
      <td>pEG</td>
      <td>5360</td>
      <td>T7 promoter-fucO-aldA-T7 terminator</td>
      <td>2862</td>
    </tr>
  </table>

{% include figure.html image="https://static.igem.wiki/teams/5175/resources/result/result-01.png" caption="Fig 1. The bands of pPeteg-P (upper band) and pPeteg-M (lower band)(~3000 bp) from PCR" %}

The bands of pPeteg-P (upper band) and pPeteg-M (lower band)(~3000 bp) from PCR are identical to the theoretical lengths of 2862 bp estimated by the designed primer locations (homologous recombination fragments), which could demonstrate that these plasmids had successfully been obtained.

{% include figure.html image="https://static.igem.wiki/teams/5175/resources/result/result-02.png" caption="Fig 2. The bands of pPM(2500+ bp) from PCR" %}

The bands of pPM(2500+ bp) from PCR are identical to the theoretical lengths of 2682bp estimated by the designed primer locations (promoter to terminator), which could demonstrate that these plasmids had successfully been obtained.

{% include figure.html image="https://static.igem.wiki/teams/5175/resources/result/result-03.png" caption="Fig 3. The bands of pEG(~3000 bp) from PCR" %}

The bands of pEG(~3000 bp) from PCR are identical to the theoretical lengths of 2862bp estimated by the designed primer locations (promoter to terminator), which could demonstrate that these plasmids had successfully been obtained.

All the results above showed us a success of the construction of pPeteg-P, pPeteg-M, pPM, pMP, pEG.

###  Plasmids of *P. putida* KT2440

We constructed three plasmids for *P. putida* KT2440: pTerephthalate-A, pTerephthalate-B, and pRhamnolipid. We verified the size of each plasmid as well as all the fragments involved in constructing the plasmids . In addition to pTerephthalate and pRhamnolipid, we also constructed plasmids to ensure the function of rhlA-rhlB and phaZ.

The pRhamnolipid plasmid is composed of rhlA-rhlB and phaZ, which collaboratively function to ensure the efficient secretion of rhamnolipid. To reduce the transcriptional burden imposed by the T7 promoter, we designed pTerephthalate-B to assess its impact on TPA utilization and growth.

<figcaption class="caption table_caption">Table 2. Plasmids of <em>P. putida</em> KT2440</figcaption>

  <table>
    <thead>
      <tr>
        <th>Plasmids</th>
        <th>Expected size(bp)</th>
        <th>Fragments</th>
        <th>Expected size(bp)</th>
      </tr>
    </thead>
    <tbody>
      <tr>
        <td rowspan="3">pTerephthalate-A</td>
        <td rowspan="3">10622</td>
        <td>T7 promoter- tphA2-tphA3 -tphA1-T7 terminator- T7 promoter - tphB-tpaK-T7 terminator</td>
        <td>10622</td>
      </tr>
      <tr>
        <td>T7 promoter- tphA2-tphA3 -tphA1-T7 terminator</td>
        <td>2959</td>
      </tr>
      <tr>
        <td>T7 promoter - tphB-tpaK-T7 terminator</td>
        <td>2449</td>
      </tr>
      <tr>
        <td rowspan="3">pTerephthalate-B</td>
        <td rowspan="3">10832</td>
        <td>T7 promoter - tphA2-tphA3-tphB -tphA1-T7 terminator- T7 promoter - tpaK-T7 terminator</td>
        <td>10832</td>
      </tr>
      <tr>
        <td>T7 promoter - tphA2-tphA3-tphB -tphA1-T7 terminator</td>
        <td>4111</td>
      </tr>
      <tr>
        <td>T7 promoter - tpaK-T7 terminator</td>
        <td>1634</td>
      </tr>
      <tr>
        <td rowspan="3">pRhlmnolipid</td>
        <td rowspan="3">13277</td>
        <td>T7 promoter-lac operator-rhlA-rhlB-T7 terminator- T7 promoter -phaZ-T7 terminator</td>
        <td>13277</td>
      </tr>
      <tr>
        <td>T7 promoter -lac operator -rhlA-rhlB-T7 terminator</td>
        <td>2452</td>
      </tr>
      <tr>
        <td>T7 promoter -phaZ-T7 terminator</td>
        <td>1075</td>
      </tr>
      <tr>
        <td>rhlA-rhlB</td>
        <td>12202</td>
        <td>T7 promoter -lac operator-rhlA-rhlB-T7 terminator</td>
        <td>2452</td>
      </tr>
      <tr>
        <td>phaZ</td>
        <td>10837</td>
        <td>T7 promoter -lac operator-phaZ-T7 terminator</td>
        <td>1075</td>
      </tr>
    </tbody>
  </table>

{% include figure.html image="https://static.igem.wiki/teams/5175/resources/result/result-04.png" caption="Fig 4. The bands of pTerephthalate-A (upper band) and pTerephthalate-B (lower band)(~3000 bp) from PCR" %}

The bands of pTerephthalate-A(~3000bp) from PCR are identical to the theoretical lengths of 2959 bp, 2449 bp estimated by the designed primer locations (promoter to terminator), which could demonstrate that these plasmids had successfully been obtained.

The bands of pTerephthalate-B(~4000 bp、~2000 bp) from PCR are identical to the theoretical lengths of 4111 bp，2000 bp estimated by the designed primer locations (promoter to terminator), which could demonstrate that these plasmids had successfully been obtained.

{% include figure.html image="https://static.igem.wiki/teams/5175/resources/result/result-05.png" caption="Fig 5. The bands of T7-tphA2-tphA3 -tphA1-T7(~3000 bp) from PCR" %}

The bands of T7-tphA2-tphA3 -tphA1-T7(~3000 bp) from PCR are identical to the theoretical lengths of 2959 bp estimated by the designed primer locations (promoter to terminator), which could demonstrate that these plasmids had successfully been obtained.

{% include figure.html image="https://static.igem.wiki/teams/5175/resources/result/result-06.png" caption="Fig 6.The bands of T7-tphB-tpaK(~2000+ bp) from PCR" %}

The bands of T7-tphB-tpaK(~2000+ bp) from PCR are identical to the theoretical lengths of 2576 bp estimated by the designed primer locations (promoter to terminator), which could demonstrate that these plasmids had successfully been obtained.

{% include figure.html image="https://static.igem.wiki/teams/5175/resources/result/result-07.png" caption="Fig 7.The bands of tphA2-tphA3-tphB-tphA1(~3000 bp) from PCR" %}

The bands of tphA2-tphA3-tphB -tphA1(~3000 bp) from PCR are identical to the theoretical lengths of 2971 bp estimated by the designed primer locations (promoter to terminator), which could demonstrate that these plasmids had successfully been obtained.

{% include figure.html image="https://static.igem.wiki/teams/5175/resources/result/result-08.png" caption="Fig 8.The bands of tpaK(~1500 bp) from PCR" %}

The bands of tpaK(~1500 bp) from PCR are identical to the theoretical lengths of 2971 bp estimated by the designed primer locations (promoter to terminator), which could demonstrate that these plasmids had successfully been obtained.

All the results above showed us a success of the construction of pTerephthalate-A, pTerephthalate-B.

{% include figure.html image="https://static.igem.wiki/teams/5175/resources/result/result-09.png" caption="Fig 9.The schematic diagram of pRhlmnolipid" %}

Unfortunately, due to time constraints, we were unable to successfully construct the complete plasmids. Consequently, we opted to construct T7-rhlA-rhlB-T7 and T7-phaZ-T7 as alternative plasmids for individual validation of their functionalities.

{% include figure.html image="https://static.igem.wiki/teams/5175/resources/result/result-10.png" caption="Fig 10.The bands of rhlA-rhlB(2000+ bp) from PCR" %}

The bands of rhlA-rhlB(2000+ bp) from PCR are identical to the theoretical lengths of 2452bp estimated by the designed primer locations (promoter to terminator), which could demonstrate that these plasmids had successfully been obtained.

{% include figure.html image="https://static.igem.wiki/teams/5175/resources/result/result-11.png" caption="Fig 11.The bands of phaZ(~2000 bp) from PCR" %}

The bands of phaZ(~2000 bp) from PCR are identical to the theoretical lengths of 2452bp estimated by the designed primer locations (colony PCR flanking primers), which could demonstrate that these plasmids had successfully been obtained.

All the results above showed us a success of the construction of pVLT33-rhlA-rhlB-phaZ.

The results above could demonstrate that these plasmids are correctly constructed, so we can transform pPeteg-P， pPeteg-M into *E. coli* BL21, while pTerephthalate-A, pTerephthalate-B, rhlA-rhlB, phaZ into *P. putida* KT2440 for verification.

## Strain construction

We have successfully constructed all the target plasmids needed in the three loops, and this step really facilitates our subsequent experiments. At the same time, in order to facilitate the measurement of the function of some elements, we separately constructed plasmids (phaZ，rhlA-rhlB，pPM，pMP，pEG) for some essential elements.

{% include figure.html image="https://static.igem.wiki/teams/5175/resources/result/result-12.png" caption="Fig 12.Colony PCR results of target fragments in plasmid PETase-EG24" %}

All the bands are identical to the theoretical sizes, demonstrating that these plasimds had been successfully transformed and verified.The results are as follows: pPM about 2500 bp, pMP about 2500 bp, pEG about 3000 bp.

The theoretical length of 2682bp、2682bp and 2862bp estimated by the design primers location (promoter to terminator) was the same, indicating that we successfully obtained the plasmid we needed.

The successful plasmids transformed into *E.coli* BL21 was verified by colony PCR.

The plasmids were successfully introduced into *P. putida* through electroporation. Given that our wild-type *P. putida* exhibits resistance to chloramphenicol, the plasmids incorporated a kanamycin resistance marker. Consequently, we employed dual antibiotic selection plates to effectively screen for successfully transformed engineered strains.

## Expression Validation

### *E.coli* BL21

#### Characterization of PETase and Degradation Performance in *E. coli* BL21

Initially, we aimed to evaluate the expression capacity and secretion efficiency of the engineered *E. coli* BL21 strains expressing the dual enzyme system (FAST-PETase-MHETase and MHETase-FAST-PETase). The strains were cultivated in LB medium at 37°C, including both engineered strains (PM and MP) and a control strain with an empty vector. When the optical density (OD600) reached 0.6-0.8, IPTG was added to induce protein expression, and the cultures were subsequently incubated at 16°C on a shaker for 1 day. After incubation, we collected both the supernatant and the pellet, followed by protein affinity chromatography and SDS-PAGE gel electrophoresis to assess protein expression.

{% include figure.html image="https://static.igem.wiki/teams/5175/resources/result/result-13.png" caption="Fig 13.FAST-PETase-MHETase，MHETase-FAST-PETase PAGE-SDS cell lysate (post-purification), cell pellet (left), and purified culture medium (right)" %}

As illustrated in Figure 13, our protein was successfully expressed in *E. coli*; however, no secretion was observed. Furthermore, a substantial amount of the target protein appeared to be present in the cell pellet. Consequently, we utilized the crude enzyme solution to analyze its PET degradation activity. A total of 3 mL of the crude enzyme solution was mixed with 5 mg of 100 μm PET powder and incubated at 37°C for 72 hours. After incubation, 1.5 mL of the reaction mixture was withdrawn and combined with 4.5 mL of methanol to terminate the reaction. The degradation products, specifically TPA, were quantitatively analyzed using HPLC-MS to assess the extent of PET degradation by the enzyme.

The mass spectrometry analysis revealed a peak with a retention time of 8.96 minutes, which closely matches that of the TPA standard, thereby confirming that the previously purified enzymes correspond to the introduced constructs PM and MP. By comparing the peak areas with the standard curve, we quantified the production levels, finding that PM yielded 223.12 ng/mL and MP yielded 310.20 ng/mL. These results indicate that the introduced genes can stably degrade PET.

{% include figure.html image="https://static.igem.wiki/teams/5175/resources/result2/result-20.png" caption="Fig 14.1 This figure shows the results of HPLC-MS measurements of FAST-PETase-MHETase, MHETase-FAST-PETase and Control, the growth curves were plotted by the standards, and the TPA content was measured before and after three days of incubation, respectively, with a significant peak detected at 8.96 min, indicating that both of our designed dual enzyme systems can effectively degradation of PET" %}

{% include figure.html image="https://static.igem.wiki/teams/5175/resources/result2/result-19.png" caption="Fig 14.2 Standard curves were plotted using standard samples (right) to quantify the TPA content in FAST-PETase-MHETase, MHETase-FAST-PETase and the control, which showed that the MP activity was significantly higher than that of PM in our designed dual enzyme system" %}

A growth curve was established using standard samples, and the TPA concentrations were measured before incubation and after three days of incubation. A distinct peak was detected at 8.96 minutes, indicating that our designed dual-enzyme system effectively degrades PET. Furthermore, the activity of MHETase-FAST-PETase (MP) was found to be significantly higher than that of FAST-PETase-MHETase (PM).

#### Growth curve of *E. coli* BL21

We cultivated engineered *E. coli* BL21 (pEG) and wild-type strains by adding varying concentrations of ethylene glycol (EG) along with 0.5 g/L glycerol. The optical density at 600 nm (OD600) was measured every 12 hours to monitor growth. The methodology for obtaining the growth curves is described as follows.

{% include figure.html image="https://static.igem.wiki/teams/5175/resources/result/result-15.png" caption="Fig 15.Growth curves for wild-type (WT) <em>E. coli</em> and engineered <em>E. coli</em> (EG) utilizing ethylene glycol (EG) as the sole carbon source" %}

The results indicate that, compared to the control group, the cell concentration of *E. coli* BL21 (EG) improved under various temperatures and concentrations of ethylene glycol (EG), with an observed increase in growth rate, particularly at higher EG concentrations. This suggests that our engineered T7-fucO-aldA construct significantly enhances the utilization of ethylene glycol through the glycolate shunt, thereby promoting better cellular growth.

### *P. putida* KT2440

#### Growth Curve of *P. putida* KT2440

We cultivated engineered *P. putida* KT2440 strains, including (pTerephthalate-A), (pTerephthalate-B), and the empty vector (pBBR1-CS2), in M9 medium with 2 g/L terephthalic acid (TPA) as the sole carbon source. Given that terephthalic acid is present at a low concentration and is considered a non-conventional carbon source, we initially inoculated *P. putida* into 10 mL of LB medium for 48 hours. Following this incubation, the cells were collected via low-speed centrifugation and then resuspended in M9 medium. The optical density at 600 nm (OD600) was measured every 12 hours to monitor growth, and the methodology for obtaining the growth curves is described as follows.

{% include figure.html image="https://static.igem.wiki/teams/5175/resources/result/result-16.png" caption="Fig 16.Growth Curves of <em>P. putida</em> KT2440 (pTerephthalate-A), (pTerephthalate-B), and Empty Vector (pBBR1-CS2) Utilizing Terephthalic Acid (TPA) as Carbon Source" %}

The results indicate that, compared to the control group (pBBR1-CS2), *P. putida* KT2440 (pTerephthalate-A) and (pTerephthalate-B) were able to survive under the cultivation conditions of 2 g/L TPA. After 100 hours, a decline in cell concentration was observed due to the depletion of the carbon source, whereas the control group was unable to utilize TPA, leading to a significant reduction in cell concentration after 30 hours. This demonstrates that the introduction of pTerephthalate-A and pTerephthalate-B conferred *P. putida* KT2440 with the capability to metabolize TPA.

#### Validation of Rhamnolipid Secretion in *P. putida* KT2440

We aimed to demonstrate the ability of *P. putida* harboring rhlA and rhlB to produce rhamnolipids. To ensure stable production of rhamnolipids, facilitating the confirmation of gene functionality, *P. putida* was initially inoculated into 10 mL of LB medium and incubated for 48 hours. Following low-speed centrifugation to collect the cells, they were resuspended in M9 medium containing 10 g/L of soybean oil as the carbon source for fermentation. IPTG was added to induce gene expression. After incubating at 30 °C for 7 days, the fermentation broth was collected for rhamnolipid extraction, and quantification was performed using the sulfuric acid-anthrone method.

{% include figure.html image="https://static.igem.wiki/teams/5175/resources/result2/result-21.png" caption="Fig 17.Determination of Rhamnolipid Content in <em>P. putida</em> KT2440 (rhlA-rhlB) and Empty Vector (WT) Using the Sulfuric Acid-Anthrone Method" %}

The sulfuric acid-anthrone method is capable of quantifying the total sugar content in the sample solution. Rhamnolipids, functioning as surfactants, consist of both reducing sugar and long-chain fatty acid components. Organic solvent extraction can remove soluble sugars from the fermentation broth. In our experiments, *P. putida* KT2440 (rhlA-rhlB) exhibited significantly higher rhamnolipid production compared to the wild-type strain. However, since the wild-type also produced a measurable amount, we planned to design further experiments, including mass spectrometry, to confirm the production of rhamnolipids. Unfortunately, due to time constraints, we were unable to successfully detect rhamnolipids.