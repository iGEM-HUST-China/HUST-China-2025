---
title: Protocol
permalink: /protocol/
feature_text: |
  ## Protocol
  This page contains the protocols of our project.
feature_image: "https://static.igem.wiki/teams/5175/resources/background/bg-protocol.jpg"
excerpt: "This page contains the protocols of our project."
---

## Culture medium

<figcaption class="caption table_caption">Table 1. Ingredients of LB (Luria-Bertani) medium</figcaption>

| **Component** | **Amount** |
| ------------- | ---------- |
| $\mathrm{NaCl}$          | 10 g/L     |
| Tryptone      | 10 g/L     |
| Yeast Extract | 5 g/L      |
| Agar(solid)   | 20 g/L     |

<figcaption class="caption table_caption">Table 2. Ingredients of M9 medium</figcaption>

| **Component** | **Amount** |
| ------------- | ---------- |
| $\mathrm{NaCl}$          | 0.5 g/L    |
| $\mathrm{Na_2HPO_4}$       | 6.78 g/L   |
| $\mathrm{KH_2PO_4}$        | 3 g/L      |
| $\mathrm{NH_4Cl}$         | 1 g/L      |
| $\mathrm{MgSO_4}$         | 0.241 g/L  |
| $\mathrm{CaCl_2}$         | 0.011 g/L  |
| Glucose       | 4 g/L      |

The correspondent carbon source should be added before the culture medium being used.

## Molecular experiments

### Agarose gel electrophoresis

1. Measure 0.25 g of agarose and place it in a conical flask, then add 25 mL of TAE buffer.
2. Microwave on high for approximately 45 seconds until it boils, shake to disperse the agarose, repeat boiling once more until the solution becomes clear.
3. Add 2.5 $\mathrm{\mu L}$ Gelred dye, mix well, and pour it into a mold fitted with appropriately spaced combs.
4. Allow it to sit until the gel completely solidifies, approximately 30 minutes.
5. Gently and vertically remove the combs, take out the gel, and place it in an electrophoresis chamber.
6. Add TAE buffer until the gel is just covered (with the end containing the sample wells near the negative electrode).
7. Dilute 1 $\mathrm{\mu L}$ 10x loading buffer with 4 $\mathrm{\mu L}$ ultrapure water, mix with 5 $\mathrm{\mu L}$ PCR product, and load it into the sample wells of the gel. Finally, add 5 $\mathrm{\mu L}$ marker into the sample wells.
8. Set the voltage to 120V and run the electrophoresis for 25 minutes.
9. After electrophoresis is complete, remove the gel and capture images using a gel imaging system under ultraviolet conditions.

### Gel extraction (purification)

1. Cut the gel as thin as possible, add 300-350 $\mathrm{\mu L}$ of Buffer GDP, and place the gel in a 55 °C water bath to dissolve.
2. Transfer the liquid to the purification column and let it stand for 5 min.
3. Centrifugate at 12000 rpm for 1 min, pipette the liquid back to the suction column, and centrifugate at 12000 rpm for 1 min.
4. Discard the solution, add 300 $\mathrm{\mu L}$ Buffer BD, and centrifugate at 12000 rpm for 1 min. (purification doesn’t include this step)
5. Add 700 $\mathrm{\mu L}$ Buffer GW, centrifugate at 12000 rpm for 1 min. (only add 400 $\mathrm{\mu L}$ for purification)
6. Repeat step 5).
7. Discard liquid, centrifugate the empty column at 12000 rpm for 2 min.
8. Discard the collection tube and dry the column for 15~20 min.
9. Place the purification column on a 1.5 mL EP tube, add 50 $\mathrm{\mu L}$ ddH2O to the center of the membrane, and stand it for 2 min.
10. Centrifugate at 12000 rpm for 2 min.
11. Pipette the liquid back to the suction column, centrifugate at 12000 rpm for 2 min.
12. Discard the column, measure the concentration and purity.

### Construction of the plasmid

#### Amplified fragment

<figcaption class="caption table_caption">Table 3. Ingredients of Amplified fragment</figcaption>

| **Component**             | **Amount** |
| ------------------------- | ---------- |
| 2 × Phanta Max Master Mix | 25$\mathrm{\mu L}$       |
| Upstream primer           | 2$\mathrm{\mu L}$        |
| Downstream primer         | 2$\mathrm{\mu L}$        |
| Template DNA              | 2$\mathrm{\mu L}$        |
| $\mathrm{ddH_2O}$                     | 19$\mathrm{\mu L}$       |

#### PCR system

<figcaption class="caption table_caption">Table 4. PCR system configuration</figcaption>

<table>
  <thead>
    <tr>
      <th>Temperature</th>
      <th>Time</th>
      <th>Cycles</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>95 °C</td>
      <td>30 sec</td>
      <td rowspan="6">30</td>
    </tr>
    <tr>
      <td>95 °C</td>
      <td>15 sec</td>
    </tr>
    <tr>
      <td>58 °C</td>
      <td>15 sec</td>
    </tr>
    <tr>
      <td>72 °C</td>
      <td>1.5 min</td>
    </tr>
    <tr>
      <td>72 °C</td>
      <td>2 min</td>
    </tr>
    <tr>
      <td>12 °C</td>
      <td>$\infty$</td>
    </tr>
  </tbody>
</table>


1. Purify the correct linear fragment by running electrophoresis.
2. Extract the gel.
3. Recombine the fragments with homologous recombinase.
4. Transform *E. coli*.

#### Homologous Recombination

<figcaption class="caption table_caption">Table 5. Ingredients of Homologous Recombination</figcaption>

| **Component** | **Amount**                     |
| ------------- | ------------------------------ |
| Exnase II     | 2$\mathrm{\mu L}$                            |
| 5× CE buffer  | 4$\mathrm{\mu L}$                            |
| Fragment      | 200 ng(approximately 4$\mathrm{\mu L}$)    |
| Vector        | 50-200 ng(approximately 1$\mathrm{\mu L}$) |
| $\mathrm{ddH_2O}$         | To 20$\mathrm{\mu L}$                        |

<center>
  $$
    \left\{
      \begin{aligned}
        X & = \left[0.02 \times \frac{\text{the number of base pairs of the vector}}{\text{the concentration of the vector}}\right] \mathrm{\mu L} \\
        Y & = \left[0.04 \times \frac{\text{the number of base pairs of the fragment}}{\text{the concentration of the fragment}}\right] \mathrm{\mu L}
      \end{aligned}
    \right.
  $$
</center>

​	(When the fragment length is longer than the plasmid, regard the fragment as the plasmid and regard the plasmid as the fragment to calculation)

1. Formulate the above system on the ice.

2. Gently suck and mix(do not shake fiercely), briefly centrifuge to collect the reaction liquid to the bottom of the tube.

3. Put the tube in 50 °C water bath for 20 min, and transfer the system into *E. coli* DH5α.

#### Double enzyme digestion

  <figcaption class="caption table_caption">Table 6. Ingredients of double enzyme digestion</figcaption>

  | **Component** | **Amount** |
  | ------------- | ---------- |
  | Fragment      | 60$\mathrm{\mu L}$       |
  | 10× Buffer    | 8 $\mathrm{\mu L}$       |
  | Enzyme 1      | 5 $\mathrm{\mu L}$       |
  | Enzyme 2      | 5 $\mathrm{\mu L}$       |
  | $\mathrm{ddH_2O}$         | 2 $\mathrm{\mu L}$       |
  | Total         | 80 $\mathrm{\mu L}$      |

1. Formulate the above system on the ice.

2. Gently suck and mix(do not shake fiercely), briefly centrifuge to collect the reaction liquid to the bottom of the tube.

3. Put the tube in PCR instrument, control the temperature at 37 °C for 20 min, then put the tube on ice immediately.

#### Enzyme ligation

<figcaption class="caption table_caption">Table 7. Ingredients of enzyme ligation</figcaption>

| **Component**   | **Amount** |
| --------------- | ---------- |
| Fragment        | 1 $\mathrm{\mu L}$       |
| Vector          | 4 $\mathrm{\mu L}$       |
| T4 ligation mix | 5 $\mathrm{\mu L}$       |

1. Formulate the above system on the ice.

2. Gently suck and mix(do not shake fiercely), briefly centrifuge to collect the reaction liquid to the bottom of the tube.

3. Put the tube in 16 °C react for 20 min(while the 25 °C react for 10 min), transfer the system into *E. coli* DH5$\alpha$.

### Plasmid extraction

1. Take 3 mL bacteria solution to centrifugate at 12000 rpm for 1 min, and pour out the supernatant. (If the bacterial plaque is small, repeat until getting a large one.)
2. Add 250 $\mathrm{\mu L}$ solution I. Blow and stir repeatedly to ensure that there is no bacterial block to cleave the inside of the bacterial block adequately.(Components of solution I: EDTA, glucose. EDTA is the chelating agent of divalent metal. It can chelate divalent metal ions to inhibit the activity of DNase, protecting the extracted DNA from degradation. Glucose plays the role of avoiding the suspended Escherichia coli settling too quickly.)
3. Add 250 $\mathrm{\mu L}$ solution II, slowly invert, and turn the tube several times to mix gently. Stand for two minutes to get a transparent cleavage solution. In order not to break the DNA chain, the operation must be very gentle. The standing time can not be too long since DNA will also break under alkaline conditions, otherwise, the genomic DNA will be broken. It is difficult to separate broken DNA from the plasmid.(Components of solution Ⅱ: NaOH and SDS. NaOH dissolves cells and combines with protein to form the sediment. Remember to close the lid in time after using solution II because NaOH will react with carbon dioxide in the air.)
4. Add 350 $\mathrm{\mu L}$ solution III, immediately invert and mix.(Components of solution Ⅲ: potassium acetate, acetic acid. SDS encounters potassium ions to generate water-insoluble PDS, resulting in a large amount of flocculent precipitation. Since the genomic DNA is a long chain, it is easy to be precipitated by these precipitations. It is difficult to precipitate if the genomic DNA breaks into short chains. )Acetic acid is to neutralize the sodium hydroxide in the previous step.)
5. Centrifugate at 12000 rpm for 10 min.
6. Carefully pipette the supernatant into the column. Centrifugate at 12000 rpm for 1 min. Repeat once without standing.
7. Add 500 $\mathrm{\mu L}$ HBC washing Buffer, centrifugate at 12000 rpm for 1 min and discard the filtrate.
8. Add 700 $\mathrm{\mu L}$ DNA washing Buffer (80% ethanol) to clean the purification column. Centrifugate at 12000 rpm for 1 min and discard the filtrate. Repeat the wash operation twice.(Wash away impurities such as small molecular proteins and inorganic ions.)
9. Centrifugate empty column at 12000 rpm for 2 min.
10. Dry in 37 °C until the purification column is no ethanol (15 min). (Remove ethanol in these two steps, otherwise, the subsequent elution efficiency will be affected.)
11. Put the purification column into a clean 1.5 mL EP tube and add 30 $\mathrm{\mu L}$ of the ddH2O preheated at 60 °C to the center of the silicone gel membrane, and stand it for 2 min. Centrifugate at 12000 rpm for 1 min. (Preheat can improve the elution efficiency, and add it to the center of the silicone gel membrane to ensure that the eluent will completely cover the surface of the silicone membrane to achieve maximum elution efficiency.)
12. Repeat the elution with the above eluent without standing. The first standing is to let the eluent cover the silicone membrane and let the DNA fall off the column.

### *E. coli* heat shock transformation

1. Take 100 $\mathrm{\mu L}$ of the competent *E. coli* that melted on ice to the precooled 1.5 mL EP tube.
2. Add 2 $\mathrm{\mu L}$ plasmid to the tube and avoid touching the bottom of the EP tube. Then gently blow and stir and place the tube on ice for 5 min.
3. Place the tube at 42 °C for 90s and transfer it to the ice immediately to bathe for 2 min.
4. Add 700 $\mathrm{\mu L}$ non-antibiotics liquid LB to the tube and incubate it in a shaker at 37 °C for 20 min.
5. Take solid LB medium, add antibiotics and pour the plate.
6. Centrifugate at 5000 rpm for 2 min, pour out part of the supernatant, re-suspend it, spread it on a plate, and incubate it at 37 °C.

### *E. coli* conservation

Add 800 $\mathrm{\mu L}$ 50% glycerol aqueous solution to the seed preservation tube for high-pressure steam sterilization, mix with 800 $\mathrm{\mu L}$ bacteria solution, and store at -20 °C.

# Expression Validation

### Preparation of *Pseudomonas putida* KT2440 competent cells

1. Put *P. putida* KT2440 into 3 mL LB liquid culture medium with chloramphenicol resistance and inoculate at 30 °C for overnight cultivation shaking at 220 rpm.
2. Take 1 mL of overnight cultured bacterial solution and inoculate it into 50 mL of LB liquid culture medium with chloramphenicol resistance at 30 °C, shaking at 220 rpm, and cultivate until the $\mathrm{OD_{600}}$ reaches approximately 0.6.
3. Centrifuge at 5000 rpm for 10 min. Discard the supernatant and resuspend the bacteria in 5 mL of buffer on ice.
4. Repeat step 3) for 2-3 times and suspend the plaque with 100 $\mathrm{\mu L}$ of buffer solution. Transfer the resuspended cells into 1.5 mL sterile centrifuge tubes and store them in the -20 °C for future use.

### Electroporation for *Pseudomonas putida* KT2440

1. Set the electric field strength of the electroporator to 12 kV/cm and the pulse length to 2.5 ms.
2. Add 2-5 $\mathrm{\mu L}$ (50 ng) of plasmid to 100 $\mathrm{\mu L}$ of bacterial suspension on ice. Gently blow and stir and place the tube on the ice. 
3. Transfer the mixed bacterial suspension to an electroporation cup and electroporate (be sure to dry the outer wall of the electroporation cup before placing it in the electroporator) 
4. After electroporation, add 800 $\mathrm{\mu L}$ of LB broth without antibiotics to the electroporation cup and mix with the bacterial suspension. 
5. Suck out the mixture and transfer it to a 1.5 mL EP tube. Incubate at 30 °C for 20 minutes.
6. Take solid LB medium, add antibiotics and pour the plate.
7. Centrifugate at 5000 rpm for 2 min, pour out part of the supernatant, re-suspend it, spread it on a plate, and incubate it at 30 °C overnight.

### Protein purification

#### Sample preparation

1. Inoculate activated bacterial strains into the corresponding resistant medium for expanded culture. Cultivate at 37 °C and shaking at 160 rpm until the $\mathrm{OD_{600}}$ reaches 0.6-0.8, then induce the culture by adding IPTG (1 mol/L) at a ratio of 1/1000. Induce expression at 30 °C for 6 hours or at 16 °C for overnight.
2. Centrifugate at 5000 rpm and 4 °C for 5 min. Collect the induced expression bacteria, discard the culture medium (collect the culture medium if it contains secreted proteins), add 30 mL of binding buffer to resuspend the cells, and sonicate the solution by using an ultrasonic cell disruptor at 800W for 10 minutes in an ice-water bath.
3. Centrifugate at 9000 rpm for 5 min at 4 °C, and take the supernatant (be sure the balance is completely calibrated), collect the supernatant, resuspend the precipitate in 1 mL of binding buffer, and take samples of both the supernatant and the precipitate for SDS-PAGE gel electrophoresis detection.
4. Protein purification is performed on ice. Add 2 mL of His purification gel to the purification column, equilibrate the column with 10 mL of binding buffer, slowly load the sample onto the column and collect the flow-through in a tube.
5. Wash the column sequentially with 30 mL of binding buffer and 30 mL of 50 mM imidazole.
6. Wash the column with 1 mL of 100 mM imidazole, then add 3 mL of 100 mM imidazole and collect the flow through for two 2 mL EP tubes, followed by elution of the target protein washed by 10 mL of 250 mM imidazole, collecting the elution in labeled tubes in order.
7. Perform SDS-PAGE and protein dialysis.
8. Procession of the samples: Take 40 $\mathrm{\mu L}$ of the eluted protein sample, add 10 $\mathrm{\mu L}$ of 5x SDS sample loading solution, heat at 100 °C by using metal bath for 10 minutes, and centrifuge at 12000 rpm for 2 minutes.
9. Mix the samples with Loading buffer in a 1.5 mL EP tube in the proportion of 4:1. Seal and heat in a metal bath at 95 °C for 5 min to fully stretch the protein space structure.
10. Perfuse the diluted electrophoresis buffer and fill it up to about 0.5 cm above the glass plate in the groove, and take out the comb.
11. Pipette 30 $\mathrm{\mu L}$ of the treated sample to pass through the buffer, and add the sample vertically.
12. Add electrode buffer to the electrophoresis tank to make the liquid levels equal on both sides. Connect the positive and negative electrophoresis tanks of the electrophoresis apparatus at 140 V for 30 min.
13. Peel the board, and dye with 0.1% Coomassie brilliant blue R250 dyeing solution for about 20 min (baking dyeing: heating and boiling in microwave oven 6-7 times).
14. Soak and rinse with rinsing solution twice for 10 min each time, change ddH2O and continue rinsing until the band is clear.
15. Observe the bands and analyze the results

#### Detection of PET enzyme activity in crude enzyme solution

1. Centrifuge 1.5 mL of cell lysate, dry it to obtain 400 $\mathrm{\mu L}$ of crude enzyme solution. Prepare multiple tubes of crude enzyme solution, and store them at -20 °C.
2. Weigh 6 mg of PET powder, mix it with 3 mL of the crude enzyme solution, and incubate the solution at 37 °C and 200 rpm for 3 days.
3. After incubation, add an equal volume of methanol to the solution, centrifuge at 12000 rpm for 3 minutes, and collect the supernatant.
4. Test the degration of PET in the supernatant by using HPLC-MS (mobile phase: 1/1000 phosphoric acid, 10% methanol).

#### Measurement of *E. coli* BL21 growth curve

1. Inoculate *E. coli* BL21 in 100 mL of M9 medium with ethylene glycol as the carbon source and add 0.5 g/L of glycerol. Cultivate under the corresponding temperature.
2. Transfer 3 mL of *E. coli* BL21 from the culture medium to an EP tube every 24 hours.
3. Measure the absorbance at $\mathrm{OD_{600}}$.
4. Plot a standard curve with growth time on the x-axis and absorbance on the y-axis.

#### Measurement of *P. putida* KT2440 growth curve

1. Inoculate *P. putida* in 100 mL of M9 medium with terephthalic acid as the carbon source, Cultivate at 30 °C.
2. Transfer 3 mL of *E. coli* BL21 from the culture medium to an EP tube every 24 hours.
3. Measure the absorbance at $\mathrm{OD_{600}}$.
4. Measure the absorbance at $\mathrm{OD_{600}}$.

#### Crude extraction of rhamnolipids

1. Pour 15 mL of the fermentation broth into a 50 mL centrifuge tube, centrifuge at 10,000 rpm for 10 minutes, and take 10 mL of the supernatant.
2. Adjust the pH to around 2.0 using 6 M HCl.
3. Add an equal volume of ethyl acetate, vortex for 15-20 minutes, then centrifuge at 8000 rpm for 10 minutes.
4. Remove the organic phase and add 8 mL of ethyl acetate. Combine the organic phases from both extractions.
5. Evaporate the organic phase to obtain the rhamnolipid sample for thin-layer chromatography identification and quantification by the anthrone-sulfuric acid method.

#### Thin-layer chromatography (TLC) of rhamnolipid

1. Prepare the plate: Dissolve 0.5 g of carboxymethyl cellulose sodium (CMC-Na) in 100 mL of water, heat to boiling to dissolve, mix with the adsorbent silica gel at a ratio of 1:3 and grind evenly, then spread the gel on a glass plate, then shake it evenly. Dry the gel in the dark, and then place it in an oven at 105 °C for about 30 minutes, then cool the plate and set aside.
2. Spotting samples: Take the sample to be tested, and use a micro-syringe to draw a certain amount of sample, gently touch it to the TLC plate to allow the sample to be absorbed automatically (ensuring the spot diameter does not exceed 3 mm). You can spot multiple times, and blow away any residual solvent with a wash ball before each new spot. There must be a spacing of 15 mm between two spots to avoid interference.
3. expansion: Choose an appropriate glass specimen tank based on the size of the TLC plate, and prepare the developing solvent (make sure the ratio of the developing solvent is: methanol : water : acetic acid = 65:15:12:1). Seal the glass specimen tank for 10-15 minutes to saturate the developing solvent, then place the TLC plate at an angle to immerse it for development, allowing the solvent to move up the TLC plate.
4. Visualization: After expansion, remove the TLC plate and let it dry. Spray the TLC plate with a visualizing reagent and heat for 2 min to develop the color that could indicate the presence of carbohydrate compounds. The visualizing reagent is 2 g of anthrone dissolved in 1 L of 80% sulfuric acid. Place a small amount of iodine crystals in a sealed container to saturate the air with iodine vapor, then place the TLC plate inside for a few minutes. We can see the color development which indicates the presence of lipid compounds.
5. Take a small amount of bacterial liquid, centrifuge, and use the supernatant as the sample to be tested. Compare it with a standard rhamnolipid sample in the chromatography experiment to observe color development and determine the presence of rhamnolipid compounds.

#### Quantitative detection of rhamnolipids

1. Take 400 $\mathrm{\mu L}$ of *P. putida* KT2440 (rhlA-rhlB-pVLT33) in an 1.5 mL EP tube.
2. Weigh 0.04 g of anthrone, dissolve it in 20 mL of concentrated sulfuric acid to prepare the sulfuric acid-anthrone solution. The solution must be used as soon as it has been prepared.
3. Slowly add 800 $\mathrm{\mu L}$ of sulfuric acid-anthrone solution into the 400 $\mathrm{\mu L}$ *P. putida* KT2440 solution, and incubate at 100 °C for 10 min. Then cool the solution to room temperature.
4. Measure the absorbance of the solution at 625 nm by using a microplate reader.
