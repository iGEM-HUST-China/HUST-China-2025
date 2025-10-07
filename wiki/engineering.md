---
title: Engineering
permalink: /engineering/
feature_text: |
feature_image: "https://static.igem.wiki/teams/5569/description/egnr.webp"
excerpt: ""
---

## Cycle 1 Construction of effective oil-degradation yeast

### Cycle 1.1.1 engineer suitable stain for oil degradation

#### Design

(1) To construct a yeast strain more suitable for growing in waste oil environments and utilizing oils to synthesize target products, we introduced the tll protein (which efficiently degrades fats) and optimized its sequence with yeast-preferred codons.

(2) Additionally, we aimed to explore the most suitable growth environment for this strain and its ability to grow in different types of oils.

(3) Considering that oils are difficult to dissolve in water, we added emulsifiers (PVA or Tween) to integrate the aqueous and organic phases.

#### Build

(1) The synthesized and optimized tll sequence was ligated into a plasmid and transformed into yeast to construct the strain Po1f-fatase, which can extensively secrete lipase.

(2) Liquid media containing various oils were prepared.

#### Test

(1) SDS-PAGE was used to determine whether lipase was successfully secreted.

(2) Hydrolysis zone assay and Scherer's titration were used to verify the degradation effect of lipase.

(3) The absorbance of the medium at OD600 was measured every 2 hours using a spectrophotometer to plot the growth curves of Po1f-fatase in media with different oils.

#### Learn

(1) The tll protein was successfully transformed into yeast, exhibiting good lipase secretion and fat degradation effects.

(2) In the hydrolysis zone assay, both Po1f-fatase and wild-type strains could grow on tributyrin glycerol solid medium; however, colonies covered most of the plate, making observation difficult. Meanwhile, the hydrolysis zones were not obvious, preventing the judgment of lipase degradation efficacy.

(3) The growth curves did not conform to the standard S-shaped curve of microbial growth; although there was an upward trend, adjacent data fluctuated significantly.

{% include figure.html image="https://static.igem.wiki/teams/5569/en/fatase-sdspage.webp" caption="1" %}

### Cycle 1.1.2 Optimization of Hydrolysis Zone Verification

#### Design

(1) To avoid massive coverage of yeast colonies which makes observation impossible, the spot inoculation method was used instead of spreading, with yeast inoculated only at the center of the plate.

(2) Through paper review, it was learned that phenol red---whose color changes from red to yellow under low pH---could be used to visualize the hydrolysis zone formed by fatty acids (degradation products of fats).

#### Build

Tributyrin glycerol solid medium and YPD liquid medium with a small amount of phenol red added were prepared.

#### Test

Overnight-cultured Po1f-fatase and wild-type strains were inoculated into phenol red-tributyrin glycerol solid medium, and the morphology of hydrolysis zones was observed at 4h, 8h, and 12h of culture.

#### Learn

The hydrolysis zone of Po1f-fatase was significantly larger and yellower than that of the wild-type strain. Both yeasts showed a trend of increasing hydrolysis zones and colonies over time, indicating that Po1f-fatase could degrade fats well and absorb them.

### Cycle 1.2.1 Growth Condition Exploration

#### Design

(1) After consulting teachers and reviewing methods for measuring absorbance of oil-containing media, it was found that oil itself has a significant impact on absorbance measurement.

(2) We added a bacterial cell resuspension step: during each sampling, the strains were centrifuged and resuspended twice with RO water to eliminate the influence of the medium.

#### Build

Oil-containing media were reconfigured using different types of oils.

#### Test

(1) A spectrophotometer was used to measure the yeast cells resuspended twice with RO water at OD600.

(2) The obtained data were plotted into growth curves and their trends were analyzed.

#### Learn

Growth curves obtained from most media conformed to the standard S-shaped curve of microorganisms, indicating that the constructed Po1f-fatase strain could grow well in various oils. However, the fitting effect of a small number of growth curves was still poor.

### Cycle 1.2.2 improvement of growth curve measurement

#### Design

(1) We considered that repeated sampling operations would bring many other impacts on yeast growth, such as contamination by miscellaneous bacteria due to the absence of antibiotics in the yeast medium, and the need for the medium to stay outside the shaker for a long time when the sample size is large.

(2) We attempted to reasonably predict the growth curve through the work of the Model group.

#### Build

We constructed a machine learning-driven growth prediction framework. Dynamic parameters of OD600 (μmax, λ, K) were extracted via Gompertz and spline fitting, and combined with medium composition characteristics to train random forest and XGBoost models, realizing the prediction of growth performance under new carbon source combinations.

#### Test

After measuring a certain amount of data, the algorithm was used to predict the growth curves of Po1f-lipase yeast cultured in canteen waste oil medium under different pH values (including 4.0, 5.0, 6.0, 7.0) and three temperatures (including 28℃, 30℃, 37℃) in shakers.

#### Learn

(1) The predicted curves conformed to the desired S-shaped curve, proving that the algorithm's prediction was relatively consistent with reality.

(2) The platform phase at the front end of some curves was very short, and the yeast quickly entered the logarithmic growth phase, indicating that the yeast utilized oil well.

## Cycle2 enhancement of mva pathway

### Cycle 2.1 beta oxidization enhancement

#### Design

(1) Literature review revealed that after fatty acids enter yeast cells, they enter the beta-oxidation pathway, and then proceed to the mevalonate (MVA) pathway for squalene synthesis.

(2) Overexpressing key genes of the beta-oxidation pathway to promote the initial conversion of fatty acids and generate more energy---both of which can facilitate squalene synthesis.

#### Build

(1) PCR primers were designed to obtain three key genes (MFE2, POX2, POT1) from the yeast genome.

(2) An overexpression vector carrying the three genes was constructed and transformed into Po1f-fatase1 yeast (which had been introduced with lipase).

#### Test

(1) Engineering strains containing the three genes, Po1f-WT, and Po1f-fatase were cultured in YPD liquid medium, followed by centrifugation to collect bacterial cells.

(2) Bacterial cells of the three strains were collected; different bacterial cells with the same weight were separately added to olive oil liquid medium and cultured overnight.

(3) Petroleum ether and alkaline titration were used to measure the contents of oil and fatty acids in the medium.

#### Learn

(1) The engineering strain with peroxisome modification could degrade oil and absorb fatty acids better than Po1f-fatase, showing a significant improvement compared to the wild type.

(2) The improvement effect was limited, far below our expectations. We inferred that although beta-oxidation can promote fatty acid conversion, most of the generated energy is carried by NADH, which cannot be well utilized by the MVA pathway.

### Cycle 2.2.1 Overexpression of the enzymes in mva pathway

#### Design

(1) To redirect acetyl-CoA to squalene synthesis, we designed a scheme to overexpress all genes of the mevalonate (MVA) pathway in the cytoplasm.

(2) Considering the existence of rate-limiting steps, we prioritized overexpressing the corresponding genes to relieve inhibition.

#### Build

(1) All genes of the MVA pathway (ERG8, ERG9, ERG10, ERG12, ERG13, ERG19, ERG20, IDI) and the catalytic enzyme for the key rate-limiting step (hmgr) were obtained from the yeast genome using primers.

(2) The obtained genes were ligated into vectors with hp4d promoters and then transformed into yeast.

#### Test

(1) Wild-type, overexpressed, and knockout strains were cultured for 3 days in oil-supplemented medium.

(2) The collected bacterial cells were freeze-dried using a vacuum freeze dryer to prepare bacterial freeze-dried powder.

(3) A nitrogen evaporator was used to determine the squalene content in the freeze-dried powder.

#### Learn

(1) The engineering strains with enhanced MVA pathway showed significantly delayed growth rate, with even lower concentration compared to the wild type.

(2) Contrary to expectations, the squalene yield of the engineering strains decreased instead. We inferred that overexpressing a large number of genes caused the engineering strains to consume too much energy for growth, thereby slowing down the rate of substance synthesis.

Insert data showing that the squalene content of wild-type strains was 4 times higher than that of engineering strains in the first measurement

### Cycle 2.2.2 remove of the restriction of rate-limiting reaction and enhancement of squalene preservation

#### Design

(1) To solve the problem of slow cell growth, we reviewed papers again and proposed corresponding solutions: using two isozymes of hmgr---one feedback inhibition-resistant type (tHMGR) and one NADH-preferring type (NADH-HMGR)---to utilize multiple cofactors simultaneously, better harness energy, and relieve the impact of rate-limiting steps.

(2) To maximize carbon flux toward squalene, we also designed the knockout of ERG1, a key gene that consumes squalene.

#### Build

(1) Plasmids carrying tHMGR and NADH-HMGR separately and together were constructed.

(2) sgRNA for ERG1 gene knockout was designed and a knockout vector was constructed.

(3) The 4 types of plasmids were transformed into Po1f-fatase respectively to construct engineering strains.

#### Test

(1) Wild-type, overexpressed, and knockout strains were cultured for 3 days in oil-supplemented medium.

(2) The collected bacterial cells were freeze-dried using a vacuum freeze dryer to prepare bacterial freeze-dried powder.

(3) A nitrogen evaporator was used to determine the squalene content in the freeze-dried powder.

#### Learn

(1) The squalene yields of strains expressing the two isozymes separately increased by 25% (~25 mg L⁻¹) and 300% (~70 mg L⁻¹) respectively, while the strain co-expressing both achieved a six-fold increase (~120 mg L⁻¹), showing a significant synergistic effect.

(2) The knockout strains could not grow normally on the plate. We inferred that the blockage of subsequent metabolic pathways prevented yeast from synthesizing substances required for normal metabolic growth, leading to death. Additionally, paper reviews indicated that massive accumulation of squalene in the cytoplasm would cause cytotoxicity.

### Cycle 2.2.3 relocation of mva pathway

#### Design

(1) To solve the problem of inhibited cell growth, we proposed a fundamental solution: peroxisomal compartmentalization. This would sequester squalene into peroxisomes, better utilize energy produced by beta-oxidation, prevent its consumption in downstream pathways, and protect the cytoplasm from toxicity.

(2) We attached the peroxisomal localization signal peptide SKL to all genes of the MVA pathway.

(3) The optimized tHMGR and NADH-HMGR were fused with SKL.

#### Build

(1) Genes of all enzymes in the MVA pathway with SKL were obtained from the yeast genome using primers, and SKL was ligated to the other two genes.

(2) Corresponding plasmids were constructed, transformed into yeast, and cultured for 3 days.

(3) The collected bacterial cells were freeze-dried using a vacuum freeze dryer to prepare bacterial freeze-dried powder.

(4) A nitrogen evaporator was used to determine the squalene content in the freeze-dried powder.

#### Test

Regrettably, due to the large number of genes and limited time, the project of constructing the complete MVA pathway in peroxisomes is still in progress. However, based on previous experimental results, we believe that the squalene yield of strains with the complete pathway will be significantly increased.

### Cycle 2.2.4 reconstruction of the structure of rate-limiting enzymes

#### Design

(1) Although existing isozymes can relieve the impact of rate-limiting steps to a certain extent, when we transfer the MVA pathway into peroxisomes, the only available cofactor will be NADH.

(2) We aim to localize tHMGR into peroxisomes as well to achieve the same experimental effect as in the cytoplasm, while optimizing the enzyme structure to enhance its catalytic ability.

#### Build

De novo sequence redesign was performed using ProteinMPNN, and Rosetta FastRelax was combined to conduct energy refinement of the conformation, thereby obtaining candidate variants with higher stability and better binding performance.

#### Test

Due to time constraints, we regretfully failed to complete the introduction and verification of the redesigned rate-limiting enzyme. However, we believe that through hardware technology and prediction, we can obtain the optimized protein and contribute to the goal of squalene accumulation.

## Cycle3 peroxisomes positioning and enhancement

### Cycle 3.1.1 signal peptide filtering

#### Design

(1) Before initiating any subsequent experimental steps, we aimed to select the most efficient and suitable peroxisomal targeting peptide for our project from all currently studied ones (e.g., PTS1, PTS2).

(2) Members of the Model group selected ERG8 from the MVA pathway; by ligating different targeting peptides to ERG8 and calculating the binding energy with PEX5 (peroxisomal protein sorting auxiliary protein), SKL with the lowest required binding energy was finally selected.

#### Build

(1) We designed ERG8 primers containing SKL, and obtained gene fragments with SKL targeting peptide from the yeast genome and GFP-containing vector via PCR.

(2) Corresponding plasmids were constructed, vectors were transformed into yeast, and cultured in YPD for 24 hours.

#### Test

Nile red staining was used to label lipid-containing parts of yeast cells, and confocal fluorescence microscopy was employed to observe the distribution of green fluorescence in yeast, so as to confirm whether GFP entered peroxisomes.

#### Learn

GFP did partially enter peroxisomes, confirming the effectiveness of the targeting peptide; however, we expected higher efficiency of the targeting peptide to increase the amount of target protein entering peroxisomes.

### Cycle 3.1.2 signal peptide improvement

#### Design

(1) The Model group re-conducted studies and attempted to add flexible peptides to increase the swing amplitude of SKL, thereby improving its binding probability with PEX5.

(2) The structure of PEX5 was studied in detail to more accurately identify the binding site of the targeting peptide in the hydrophobic pocket of PEX5, thus better predicting the binding effect.

(3) By comparing the newly obtained targeting peptides (G4S, TWY) with SKL and calculating binding energies, it was found that TWY had the best binding effect.

#### Build

(1) Using HADDOCK-based peptide-enzyme docking simulation, the binding mechanisms of classic and extended PTS1 motifs (SKL, GGGSSKL, TYWIRFSKL) were analyzed, revealing the energetic and structural basis for efficient recognition by PEX5, thus providing principles for the rational design of import signals.

(2) Using new primers, the modified TWY targeting peptide sequence was ligated to the gene sequences of GFP and ERG8 via PCR; corresponding plasmids were constructed and transformed into yeast, followed by culturing in YPD liquid medium for 24 hours.

#### Test

Unfortunately, due to time constraints, we failed to verify whether the modified targeting peptide TWY could better import the target protein into peroxisomes compared to SKL. However, based on previous experiments, we believe that TWY will have better localization ability.

### Cycle 3.2 Peroxisome Proliferation and Expansion

#### Design

(1) Considering the issue of targeting peptide localization, we reviewed papers and found a dual-benefit method: the increase and expansion of peroxisomes can store more squalene, while increasing the probability of collision with targeting peptides to facilitate localization.

(2) We discovered that PEX23 and PEX10 play important regulatory roles in the formation process of peroxisomes.

(3) It was clarified that PEX23 and PEX10 exert negative and positive regulation on peroxisomes respectively. Therefore, we chose to construct PEX23 knockout vector and PEX10 overexpression vector separately.

#### Build

(1) Primers were designed to obtain the PEX10 sequence from the yeast genome, and the CDS sequence of PEX23 was searched from the NCBI library, with corresponding knockout sgRNA designed.

(2) The two sequences were ligated into overexpression and knockout vectors respectively, and the two plasmids were transformed into yeast.

#### Test

Regrettably, we failed to complete the construction of the two engineering strains. Moreover, limited by the existing experimental equipment, we cannot directly extract peroxisomes to verify whether they have proliferated or expanded. However, we believe that the introduction of these two gene vectors can achieve our goal and have a positive impact on squalene accumulation.

## Cycle4 hardware construction and iteration

### Cycle 4.1: From Manual Operation to Semi-Automated Proof of Concept (V1.0 → V2.0)

#### Design

Our initial design goal was to integrate three independent functions---fermentation, centrifugation, and disruption---into a single device. The V1.0 design included an upper tank for fermentation and a lower tank for enrichment and lysis, but liquid transfer and mode switching still required extensive manual intervention.

#### Build

We built the V1.0 prototype, where the upper tank was equipped with manually controlled sliders and cocks, and the lower tank required manual shaft replacement to switch between centrifugation and oscillation modes.

#### Test

Tests on V1.0 verified the feasibility of the integrated design, but the entire process still required researchers' step-by-step involvement, failing to achieve the "one-click start" automation goal.

#### Learn

We recognized that insufficient automation was the core issue. To achieve true full automation, two key points must be addressed: first, realizing automated fluid control, and second, achieving seamless automatic switching between centrifugation and oscillation modes.

### Cycle 4.2: Implementation of Core Automation Functions and Identification of Bottlenecks (V2.0 → V3.0)

#### Design

Based on the learnings from the first cycle, we conducted a disruptive redesign. We introduced a mortise-tenon structure to couple stirring and flow switching, controlled separately by the forward and reverse rotation of a motor; meanwhile, we innovatively designed an automatic mode-switching bearing, which automatically switches between centrifugation and oscillation modes by changing the rotation direction of the bottom motor.

#### Build

We built the V2.0 prototype, integrating the above-mentioned automated designs.

#### Test

V2.0 successfully realized the core function of "single-motor-driven multi-mode switching," proving the feasibility of our design concept. However, new bottlenecks were identified during testing: 1. Inability to automatically balance before centrifugation; 2. Tedious repeated addition/extraction of liquids in centrifuge tubes; 3. Suboptimal actual effect of the oscillation mode.

#### Learn

The automated mechanical structure is feasible, but liquid handling processes and user experience have become new optimization priorities. We learned that an innovative liquid handling solution is needed to address balancing and transfer issues, and the mode-switching mechanism needs to be optimized to achieve true oscillation effects.

### Cycle 4.3: Intelligent Control and User-Friendliness Upgrade (V3.0 → V4.0)

#### Design

Targeting the findings from the second cycle, we made three key design improvements: 1. Introducing an STM32 intelligent control system, integrated with temperature and pH sensors to enable process monitoring; 2. Inventing a connected centrifuge tube kit, realizing automatic balancing and simplified liquid handling based on the communicating vessel principle; 3. Adding a one-way bearing to the drive shaft to prevent centrifuge tubes from rotating during oscillation, achieving true oscillatory disruption.

#### Build

We built the V3.0 prototype with integrated circuits and sensors, and manufactured the connected centrifuge tubes and improved mode-switching mechanism.

#### Test

V3.0 achieved a high level of automation and intelligence, but tests and user feedback revealed deeper issues: the DC motor used for flow control had insufficient precision, leading to inaccurate switch positioning; the 3D-printed gears lacked sufficient strength and were prone to damage.

#### Learn

Reliability and control precision are key to productization. We recognized that while pursuing functional innovation, we must select components with matching performance and consider the mechanical strength of materials.

### Final Outcome (V4.0)

Based on the learnings from the third cycle, we finally replaced the top motor with a stepper motor capable of precise positioning, and planned to replace key components such as gears with metal parts, thus creating the final version of the iFPS device with stable performance and smooth operation. Through these three closely linked engineering cycles, we successfully iterated a conceptual idea into a mature hardware product capable of solving practical pain points.