---
title: Results
permalink: /results/
feature_text: |
feature_image: "https://static.igem.wiki/teams/5569/description/rst.webp"
excerpt: ""
---

## **Part 1 Multi-dimensional verification of scheme feasibility and exploration on the growth conditions**

### **1.1 Different Types of pure Oil**

The liquid fatty acids in waste cooking oil form a mixed system, dominated by oleic acid and also containing other components such as linoleic acid and linolenic acid.

To confirm that our Yarrowia lipolytica can utilize lipids in waste cooking oil for normal growth, we prepared culture media using glycerol and fatty acids as carbon source combinations---with the total carbon content precisely calculated and kept consistent. For experimental simplification, we directly used the hydrolyzed products of triglycerides to simulate the lipid composition in waste cooking oil. The cultivation was conducted under the standard culture conditions for the wild-type Yarrowia lipolytica strain PO1f, i.e., pH 6.5 and 28°C.

{% include figure.html image="https://static.igem.wiki/teams/5569/result/1.webp" caption="1" %}

Through the comparison and comprehensive analysis of data across all groups, it was found that Yarrowia lipolytica can grow well in fatty acid-rich environments. Furthermore, our experimental results revealed that Yarrowia lipolytica exhibits the optimal growth vigor when using oleic acid as the carbon source. Coincidentally, oleate accounts for the highest proportion (approximately 50%) of total lipids in various types of waste cooking oil. This finding further underscores the growth advantage of our strain in waste cooking oil.

### **1.2 Glycerol and fatty acids in different proportions**


{% include figure.html image="https://static.igem.wiki/teams/5569/result/2.webp" caption="1" %}
In practical production, yeast decomposes lipids into one molecule of glycerol and three molecules of fatty acids: glycerol tends to support cell growth, while fatty acids tend to drive the high-flux operation of squalene synthesis. We aim to investigate whether artificial supplementation of glycerol can alter the ratio of glycerol to fatty acids, thereby enhancing the bacterial growth rate or increasing squalene production. Therefore, under the premise of maintaining a constant total carbon content in the medium, we adjusted the ratio of added glycerol to fatty acids and set up three control groups with glycerol-to-fatty acid ratios of 1:1, 1:3, and 1:5.

**Growth status under different proportions**

For the three types of fatty acids, the order of superiority among the three ratios varies. However, from the perspective of oleic acid--- the main component of hydrolyzed waste cooking oil--- the yeast exhibits the optimal growth when the ratio of glycerol to oleic acid is 1:1. Therefore, it can be concluded that when the cost of supplementary glycerol is lower than the economic value brought by the increased squalene yield, an appropriate amount of glycerol can be added to enhance squalene production.

***To further refine our experimental setup, we compared squalene yield produced by *Y. lipolytica* cultivated in either standard YPD or YPD supplemented with olive oil (see protocol). The results are as follows.***


{% include figure.html image="https://static.igem.wiki/teams/5569/result/3.webp" caption="1" %}

**Squalene yield (mg L⁻¹) of *Yarrowia lipolytica* Po1f wild-type (WT) grown in YPD and YPD supplemented with olive oil.** Error bars represent standard deviations from two to three independent cultures.

The bar graph compares the squalene yields of wild-type *Yarrowia lipolytica* under two conditions. In YPD medium alone (left bar), the strain produces ~10 mg L⁻¹ squalene. When olive oil is added to YPD (right bar), the yield roughly doubles to ~20 mg L⁻¹, indicating that lipid supplementation markedly boosts squalene accumulation. Similar YPD with olive oil was used in our further experiments.

---

## **Part 2 Lipase（TLL）Verification**

**------From waste oil to fatty acids**

*To verify whether our Po1f yeast can discrete lipase which transforms lipid into fatty acid, we conducted several experiments on the secreted Thermomyces lanuginosus lipase (TLL) in engineered Po1f yeast. Through a combination of qualitative plate assays, SDS-PAGE profiling, and quantitative alkalimetric titration, we demonstrate that Po1f -TLL exhibits robust, time-dependent lipid-hydrolytic activity, yielding fatty acids that both acidify the medium and form conspicuous hydrolysis halos. The recombinant strain secretes the ~20 kDa TLL at high levels without appreciable background proteins, and it catalyzes the release of significantly more protonated fatty acids than the wild-type control. Collectively, the data establish Po1f -TLL as an efficient, cleanly secreted biocatalyst for lipid degradation.*

### **2.1 SDS-PAGE**


{% include figure.html image="https://static.igem.wiki/teams/5569/result/4.webp" caption="1" %}

**SDS-Page Result**

The Po1f-TLL band(about 20KDa) is located between 25KDa band and 35KDa band, supporting the band is the TLL protein. Also, it can be conclude that Po1f don't secrete other protein much, and the TLL proteins are successfully secreted in large quantity.

### **2.2 Hydrolysis Circles**

#### **2.2.1 Hydrolysis Circle-1**


{% include figure.html image="https://static.igem.wiki/teams/5569/result/5.webp" caption="1" %}

**Different inoculation approaches of different cultivation times**

(A)Spread plate+1d (B)Blank+1d
(C)Central spot+1d (D)Central spot+8h

One day after inoculation, the entire A plate appeared yellow, while the hydrolysis zone of the C plate emerged in the center and showed a tendency of expansion with increasing time. Phenol red turns red under high pH conditions and yellow otherwise. The analysis revealed that there was a large amount of secreted lipase in the fermentation broth; the lipase degraded tributyrin, leading to a decrease in the pH of the plate.

#### **2.2.2 Hydrolysis Circle-2**


{% include figure.html image="https://static.igem.wiki/teams/5569/result/6.webp" caption="1" %}

**Different group of different cultivation times**

> (A)Po1f-TLL+24h     (B)Po1f-TLL+8h     (C)Po1f-TLL+4h
> (D)Po1f-WT+24h      (E)Po1f-WT+8h      (F)Po1f-WT+4h

According to the medium color, it is obvious that the hydrolysis circle expand as the cultivation time increase. Compared to the wild type ,the Po1f that secrete TLL has larger hydrolysis circle. We conclude that TLL can efficiently degrade the lipid,which produce the fatty acid and contribute to the color change of phenol red, which shows red in high pH condition while yellow in low pH condition. It is also noticeable that when the cultivation time comes to 24h, the hydrolysis circle faded or even disappear, we explain this by the growth of yeast that absorb the fatty acids. However, there is still a hydrolysis in Po1f-tll plate, indicating that the TLL expand and degrade the lipid around the yeast.

### **2.3 Alkalimetric titration**

| sample       | Po1f-TLL | Po1f-WT | blank |
|--------------|-----------|----------|-------|
| NaOH(5mM)    | 24ml      | 10ml     | 9ml   |

*sample: adding 1 ml corresponding supernatant into 4 ml TE(blank for 5 ml) and 10 ml olive oil emulsion, react under 60 degree in 10 min. After that, add 95% ethanol to cease the reaction immediately. Add 0.5mM phenol to indicate the pH.*

### **2.4 Exploration of the Optimal Activity Conditions of Lipase**

| initial PH | enzyme activity |
|------------|-----------------|
| 5.5        | 390             |
| 6          | 405             |
| 6.5        | 375             |
| 7          | 360             |
| 7.5        | 330             |


{% include figure.html image="https://static.igem.wiki/teams/5569/result/7.webp" caption="1" %}

**Lipase activity under different pHs**

*The decrease weight of reactant*
*enzyme activity=___________________________*
*time*

To discover the effect of pH condition for tll, we formulate oil cultivation media with several different initial pH.The data shows that tll has the highest activity under pH6.0 condition.

### **2.5 Nitrogen**

Through literature surveys, we have noted the micro- and macro-level effects of nitrogen limitation on *Yarrowia lipolytica*. To feed data into hardware-based feeding algorithms and other control strategies, we designed a tightly linked series of experiments whose key variable was the C:N ratio.

To guarantee experimental accuracy, we first determined the optimum C:N ratio for *Y. lipolytica* growth: media with C:N ratios from 10 to 80 were prepared, inoculated with pre-cultured cells, and incubated. The results showed that a C:N ratio of 10 gave the highest yield, with the OD600/OD800 ratio remaining maximal throughout the entire cultivation period.

{% include figure.html image="https://static.igem.wiki/teams/5569/result/8.webp" caption="1" %}

**Biomass Density under Initial Carbon-to-Nitrogen Ratios**

To establish a baseline for dynamic changes in nitrogen content, the nitrogen-consumption rate was also determined: using C/N = 10 medium, the ammonia-depletion rate was measured to support the design of a dynamic nitrogen-feeding regime. Semi-quantitative analysis with a water-quality test kit and repeated sampling showed that 250 mL of culture consumed ≈ 0.2 g NH₄⁺-N every 24 h.

Building on these key parameters, we next investigated how dynamic shifts in nitrogen availability regulate squalene yield in *Yarrowia lipolytica*, aiming to clarify the relationship between nitrogen-supply mode and target-product accumulation.

To balance analytical accuracy, cost and throughput, a UV-spectrophotometric protocol for squalene was developed in-house based on published principles. The workflow covers sample preparation, measurement and data processing. A calibration curve constructed with authentic squalene standards at 219.5 nm provided the quantitative basis for determining squalene yield.

{% include figure.html image="https://static.igem.wiki/teams/5569/result/9.webp" caption="1" %}
**Standard Curve of Squalene (Absorbance at 219.5 nm)**

At the experimental-design stage, the nitrogen-feeding strategy was benchmarked against the previously acquired data; three feeding regimes were formulated and compared. The final results demonstrate that prolonging the feeding interval to create sustained oscillations of nitrogen within a defined concentration window exerts a positive effect on squalene synthesis in *Yarrowia lipolytica*, raising yield markedly and furnishing a pivotal reference for subsequent optimization of nitrogen-based control schemes in microbial squalene production.

{% include figure.html image="https://static.igem.wiki/teams/5569/result/10.webp" caption="1" %}

**Squalene Yield under Dynamic Nitrogen Contents**

Finally, we determined that 0.2 g of nitrogen should be fed every 24 h, equivalent to 0.943 g of ammonium sulfate.

### **2.6 Grow in waste of oil from school canteen**

After constructing the strain capable of efficiently expressing lipase, we intended to test and compare its growth performance under different environmental conditions. Specifically, we selected three types of media for investigating the growth status of the engineered yeast: the general complete medium for yeast (YPD medium), the medium with a 1:1 mixture of oleic acid and glycerol as the carbon source, and the medium using waste cooking oil obtained from the university canteen as the carbon source.

{% include figure.html image="https://static.igem.wiki/teams/5569/result/11.webp" caption="1" %}

**Growth status in different oil conditions**

As indicated by the experimental results, the engineered yeast can grow well in the waste cooking oil from the canteen, and its abundance during the plateau phase is higher than that when cultured in YPD medium (with glucose as the carbon source).

### **2.7 Different PHs & Temperatures**

In the industrial production process, the pH value can be adjusted during the pretreatment of waste cooking oil, and the temperature of the fermenter can be controlled. Therefore, using waste cooking oil from the canteen as the carbon source, we investigated the optimal growth pH and temperature of yeast with the modified strain PO1f-fatase. The pH gradient was set as follows: 4.0, 5.0, 6.0, and 7.0; the temperature gradient included the commonly used values: 28°C, 30°C, and 37°C.

{% include figure.html image="https://static.igem.wiki/teams/5569/result/12.webp" caption="1" %}

**Growth status with different pHs and Temperatures**

Finally, it was concluded that the engineered yeast exhibits optimal growth under the conditions of 28°C and an initial pH of 6.0.

### **2.8 Conclusion**

**The data illustrates Po1f-TLL has the strongest degradation ability that produce the most fatty acids which requires the largest amount of NaOH solution to neutralize the protons.**

---

## **Part 3 β-oxidization pathway**

**------from FFA to Acetyl-CoA**

### **3.1 Plasmid construction**

Our standard cloning workflow begins with genomic DNA isolated from *Yarrowia lipolytica*. Target genes are amplified by PCR, digested with NotI and ClaI, and ligated into the likewise-cut 7166 backbone using T4 DNA ligase. The ligation mixture is transformed into *E. coli*, selected on ampicillin plates, verified by colony PCR, and the positive clone is propagated for plasmid recover


{% include figure.html image="https://static.igem.wiki/teams/5569/result/35.webp" caption="1" %}

**PCR of POX2, the band is similar to the anticipated length 2139bp**

**PCR of POT1, the band is similar to the anticipated length 1281bp**

**PCR of MFE2, the band is similar to the anticipated length 2807bp**



### **3.2 β-oxidization pathway verification**

To illustrate the function of three genes (MFE2, Pox2, Pot1) which have significant function in the beta-oxidization progress of *Yarrowia lipolytica*, we assay the quantity of fatty acid with a series of experiment which reflect on the ability of converting the fatty acid into energy

First, we use three types of the engineering *Y.lipolytica*: po1f wild-type(WT), po1f lipase(FA), po1f beta oxidization (BO). TLLbe was introduced into FA and has been proved previously to enhance the lipid degradation, while BO has been introduced with MFE2, Pox2 and Pot1.

We cultivate these three kinds of yeast after 24h, then centrifuge for separating the yeast and re-suspense with the olive oil emulsion for overnight cultivation

{% include figure.html image="https://static.igem.wiki/teams/5569/result/16.webp" caption="1" %}



**Fig. RT sedimentation (from left to right WT, FA, BO)**

### **3.3 Alkalimetric titration**

Adding 75 ul phenolphthalein solution into 5 ml sample, use 50mM NaOH solution to titrate.


{% include figure.html image="https://static.igem.wiki/teams/5569/result/17.webp" caption="1" %}

**Table. Titration result (from left to right WT, FA, BO)**

|             | WT   | FA   | BO   |
|-------------|------|------|------|
| 0.5nM NaOH/ml | 3.64 | 0.85 | 0.72 |

### **3.4 Lipid extract**

Adding 15 ml petroleum ether into 5mL sample, after 20min ultrasonic oscillation, centrifuge at 9000 rpm for 10 min. Collect the oil phase which is at the top of the solution and put the falcon tube into oven, then wait until the weight is constant.


{% include figure.html image="https://static.igem.wiki/teams/5569/result/18.webp" caption="1" %}
**yeast sediment**

**water phase**

**oil phase**

**centrifuge result(from left to right WT,FA,BO)**

{% include figure.html image="https://static.igem.wiki/teams/5569/result/19.webp" caption="1" %}

**oil**

**extraction result(from left to right WT, FA, BO)**

|                | WT   | FA   | BO   |
|----------------|------|------|------|
| oil pure weight/g | 0.72 | 0.56 | 0.47 |

Both the titration and extraction illustrate a decline of the fatty acid. Obviously, WT has the weakest ability to break down the lipid and absorb it. The efficiency of fatty acid absorbed by BO has approximate 15% increase comparing to FA, which reflect the beta oxidization has been enhanced.

We hypothesize that the increase is limited due to its transport. When all of these beta oxidization gene is overexpressed, they demand large amount of energy.

### **3.5 Conclusion**

In conclusion, our combined cloning and phenotypic analyses confirm that the three-step β-oxidation module (MFE2, POX2, POT1) from Yarrowia lipolytica was successfully assembled and is functionally active in PO1f. After 24 h of growth on olive-oil emulsion, the engineered "BO" strain consumed 15 % more fatty acid than the lipase-only "FA" control, as independently quantified by alkalimetric titration (0.72 vs. 0.85 mM NaOH mL⁻¹) and gravimetric lipid extraction (0.47 vs. 0.56 g residual oil). The wild-type strain retained the most lipid (0.72 g), underscoring the necessity of both enhanced lipolysis and downstream β-oxidation for maximal fat utilization.

---

## **Part 4 MVA pathway**

**------from Acetyl-CoA to Squalene**


### **4.1 Plasmid construction**

{% include figure.html image="https://static.igem.wiki/teams/5569/result/36.webp" caption="1" %}


**PCR of ERG9, the band is similar to the anticipated length 1365bp**

**PCR of ERG8, the band is similar to the anticipated length 1284bp**

**PCR of ERG12, the band is similar to the anticipated length 1377bp**

**PCR of ERG13, the band is similar to the anticipated length 1369bp**

**PCR of ERG10, the band is similar to the anticipated length 1628bp**

{% include figure.html image="https://static.igem.wiki/teams/5569/result/37.webp" caption="1" %}

**PCR of ERG19, the band is similar to the anticipated length 1191bp**

**PCR of tHMGr, the band is similar to the anticipated length 1533bp**

**PCR of NADH-HMGr, the band is similar to the anticipated length 1071bp**

**PCR of IDI, the band is similar to the anticipated length 840bp**

**PCR of ERG20, the band is similar to the anticipated length 1062bp**





### **4.2 Optimization of the rate-limiting step**

**Squalene yields (mg L⁻¹) of *Yarrowia lipolytica* expressing feedback-resistant or cofactor-switched HMGR isoenzymes.**

{% include figure.html image="https://static.igem.wiki/teams/5569/result/30.webp" caption="1" %}


**Squalene yields with different HMG-CoA reductase**

(Strains were cultured in YPD + olive oil.)

The bar graph compares intracellular squalene yields (mg L⁻¹) among four *Yarrowia lipolytica* variants grown in YPD plus olive oil.

The PO1f-fatase control reaches ~20 mg L⁻¹. Expression of NADH-HMGR, which utilizes NADH as cofactor, lifts the yield to ~60 mg L⁻¹, while the feedback-insensitive t-HMGR alone achieves ~100 mg L⁻¹. Co-expressing both t-HMGR and NADH-HMGR further elevates squalene to ~120 mg L⁻¹, demonstrating that simultaneously bypassing negative feedback and increasing NADH supply synergistically boosts
{% include figure.html image="https://static.igem.wiki/teams/5569/result/31.webp" caption="1" %}


**Tag recovery**

When co-expressing tHMGr and NADH-HMGr, we conducted tag recovery.

{% include figure.html image="https://static.igem.wiki/teams/5569/result/32.webp" caption="1" %}

### **4.3 Impact of exogenous genes**

**Squalene yield of Po1f-fatase and Po1f-fatase^Exogenous^**

Although it has been demonstrated that the introduction of exogenous genes such as tHMGr and NADH-HMGr can significantly promote the reactions of rate-limiting steps, the results of our yeast experiments are not as theoretically expected. This may be attributed to the increased metabolic burden imposed on yeast by the introduced exogenous genes, which disrupts its metabolic equilibrium and consequently leads to a reduction in squalene synthesis.

### **4.4 Squalene downstream knockout**

To channel carbon flux toward squalene, we knocked out the downstream genes responsible for converting squalene to cholesterol in the cytosolic MVA pathway. The resulting knockout strain and the wild-type control were cultivated in parallel, and both growth and intracellular squalene yields were monitored over time.

{% include figure.html image="https://static.igem.wiki/teams/5569/result/33.webp" caption="1" %}

![Growth curve of WT and erg^-^ Po1f]

{% include figure.html image="https://static.igem.wiki/teams/5569/result/34.webp" caption="1" %}

**Survival status of WT and erg^-^Po1f**

(A) erg^+^Po1f(WT) (B)erg^-^Po1f

Surprisingly, after knocking out the downstream gene of squalene metabolism, the yeast growth was impaired and the squalene yield will be decreased. Upon consulting the literature, we found that squalene exerts negative feedback regulation and possesses cytotoxicity. Addressing these issues has become our top priority.

### **4.5 Conclusion**

**Conclusion**

Disrupting ERG1, the first committed step that consumes squalene in the cytosolic MVA pathway, successfully blocked downstream sterol synthesis but failed to raise the intracellular squalene pool. Instead, the Δerg1 mutant exhibited slower growth and a 25 % lower squalene yield than the wild-type, indicating that accumulated squalene is both cytotoxic and subject to stringent negative-feedback control. These data reposition the challenge from "increasing squalene" to "balancing squalene flux".

By separately and combinatorially expressing two HMGR isoenzymes that are (i) refractory to squalene-mediated feedback (t-HMGR) and (ii) able to exploit the NADH-rich peroxisomal redox poise (NADH-HMGR), we obtained an early, gene-dose preview of the metabolic advantage expected from full MVA-pathway sequestration. Each single substitution already tripled (NADH-HMGR) or quintupled (t-HMGR) the wild-type squalene yield, while dual expression delivered a six-fold increase (~120 mg L⁻¹) without compromising growth. The clear additivity of feedback relief and cofactor switching validates both engineering strategies and argues that peroxisomal compartmentalization---by simultaneously supplying high NADH and physically isolating the enzymes from cytosolic sterol sensors---will further amplify flux. Consequently, we are now concatenating t-HMGR and NADH-HMGR with the remaining MVA genes into peroxisome-targeted operons; the quantitative benchmarks established here provide a short-cut to assess the incremental value of each import event and should accelerate construction of a fully compartmentalized, high-yield squalene cell factory.

---

## **Part 5 Peroxisomal Compartmentalization**

**------highly efficiency to synthese Squalene**

To solve these problems, we decided to use compartmentalization to move the entire MVA pathway and the synthesis of squalene into peroxisome, therefore extracting squalene out of cytoplasm, reducing its cytotoxicity, relieving negative feedback and preventing it from transforming into cholesterol.

### **5.1 Linking genes with SKL**

Thanks to the work being done by dry lab, we acquired the sequence of PTS, which guides proteins into peroxisome.

***E.coli* colony PCR of MVA pathway genes linked with SKL**
{% include figure.html image="https://static.igem.wiki/teams/5569/result/38.webp" caption="1" %}

**Distribution of gfp with and without PTS1**
{% include figure.html image="https://static.igem.wiki/teams/5569/en/pts1-gfp.webp" caption="1" %}

(A)The engineered strains, transfected with GFP lacking peptide(SKL) ,cultured PA for 24 hours, were stained with Nile red and photographed with a laser confocal microscope.

(B) The engineered strains, transfected with GFP containing peptide(SKL) ,cultured PA for 24 hours, were stained with Nile red and photographed with a laser confocal microscope

We investigated the localization of proteins to peroxisomes mediated by the peroxisomal targeting signal (PTS). Firstly, the PTS amino acid sequence SKL is fused with green fluorescent protein (GFP) via amplification to generate the GFP-PTS gene fragment. Subsequently, the gene fragments (GFP and GFP-PTS) were recombined with plasmid 7166, resulting in the construction of recombinant plasmids, namely 7166-GFP-PTS and 7166-GFP . These recombinant plasmids were then linearized and cloned into the genome of Yarrowia lipolytica strain Po1f, leading to the generation of GFP-engineered strains: Po1f-GFP-PTS and Po1f-GFP.

Finally, the engineered strains Po1f-GFP-PTS and Po1f-GFP were stained with Nile Red. Observations under a laser scanning confocal microscope (LSCM) revealed that the green fluorescent foci derived from GFP-PTS expression completely overlapped with the large red fluorescent regions (which correspond to lipids accumulated in peroxisomes), producing bright yellow fluorescence. In contrast, the green fluorescent foci from GFP expression showed minimal overlap with the red Nile Red-stained regions; in some cases, an almost opposite distribution pattern is observed. For instance, in the leftmost cell of Figure B, the The distribution of bright green fluorescent (formed by the concentrated distribution of GFP) is highly diffuse and are largely separated from the regions where red Nile Red-stained lipids are concentrated.

These results demonstrate that the enhanced peroxisomal targeting signal PTS can efficiently mediate the targeted localization of proteins to peroxisomes. This finding is consistent with the results reported by DeLoache et al., who successfully achieved the targeting of proteins to peroxisomes in Saccharomyces cerevisiae.

### **4.3 Conclusion**

To date, we have successfully accomplished the design, introduction, and functional verification of the peroxisomal targeting signal 1 (PTS1) peptide. Moreover, we have obtained all small plasmids with each target gene fused to PTS1. Currently, we are proceeding with tag recovery to facilitate the construction of large plasmids.

Moving forward, we will continue to advance the project: we plan to generate squalene-synthesizing strains with compartmentalized metabolic pathways either by sequential introduction of individual small genes or via the transfer of the large plasmid. This strategy is expected to achieve a further leap in squalene production.

Additionally, we anticipate contributing valuable insights into peroxisomal compartmentalization and related synthetic biology tools to the iGEM community, aiming to support and inspire future research in this field.

{% include figure.html image="https://static.igem.wiki/teams/5569/en/20251007222710-2089-153.webp" caption="1" %}

