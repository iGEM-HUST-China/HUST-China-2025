---
title: Genome-scale Metabolic Modeling
permalink: /model/genome-scale/
feature_text: |
  ## Model
  All models are wrong, but some are useful.——George E. P. Box
feature_image: "https://static.igem.wiki/teams/5175/resources/background/bg-model.jpg"
excerpt: "The model is a means of assisting the overall completion and implementation of a project through computational methods."
images01:
  - src: https://static.igem.wiki/teams/5175/resources/model/model-gssm-02.png
    alt: A Figure of dFBA Simulation Results
    caption: Figure 2.dFBA simulation of Biomass, TPA, and lrhh<br> Biomass concentration in grams of dry weight (gDW) and substrate concentration in mmol<br> At the beginning of the simulation, the initial biomass of the strain was 0.1 gDW. Due to the low production of rhamnolipids, it was difficult to distinguish them. Please refer to Figure 3 for additional information
  - src: https://static.igem.wiki/teams/5175/resources/model/model-gssm-03.png
    alt: A Figure of dFBA Simulation Results
    caption: Figure 3. Supplementary image of rhamnolipids generation under simulated conditions in Figure 2

---

## Genome-scale Metabolic Modeling

To aid wetlab metabolic pathway modification and to assess the performance of the project in real-world applications, we constructed a genome-scale metabolic model of engineered *Pseudomonas putida* KT2440 (*P.putida* KT2440) that is capable of dynamically simulating cellular metabolic activities. Compared with other published GSSMs, our model scores is 76%, which exceeds the average of published models. We can predict the growth behavior, TPA uptake rate and rhamnolipid product yield of engineered bacteria. We estimated that engineered *P.putida* could efficiently absorb and degrade TPA while producing rhamnolipids in the process. With our GSSM, we have established a foundation that will help future teams to build metabolic model for *P.putida* and improve the idea of using *P.putida* to degrade microplastics.

### Methods

GSMM is a method for representing, quantifying, and comparing the metabolism of a given organism as a set of equations that include key gene expression, enzyme-catalyzed reactions, transport mechanisms, and spontaneous non-catalyzed reactions, primarily using Flux Balance Analysis (FBA) or Dynamic Flux Balance Analysis (dFBA)[^1]. The MATLAB COBRA toolbox implementation was accessed using the COBRA package [^2]for python.

#### Construction of metabolic reaction list

The initial metabolic reaction list of *P.putida* KT2440 was obtained from the latest high-quality genome-scale metabolic model of *P.putida* “iJN1463”[^3]. Based on this, the TPA metabolic pathway and the rhamnolipid synthesis metabolic pathway were added to obtain the modified iJN1463. Specifically, TPA is metabolized into acetyl-CoA and succinyl-CoA then go into the TCA cycle and linked to the wild-type β-ketoadipic acid pathway, while the synthesis of rhamnolipids starts from the substrate β-hydroxyacyl-ACP in the fatty acid synthesis pathway and condenses with dTDP-L-Rhamnose. A total of seven metabolites and eight reactions were added, and 24 of the phaZ-regulated reactions were ceiling-adjusted to obtain the growth behavior of the engineered *P.putida* KT2440. Due to the lack of data, it was assumed that the upper and lower limits of RHLA and RHLB fluxes set in the *P.putida* KT2440 model PAO1 were the same as those of the engineered *P.putida* during the simulation. The list of added reactions is given below (see Tables 1 and 2).

 <figcaption class="caption table_caption">Table 1.Definition of newly added metabolites with ID suffixes representing the compartments in which they are located<br>Note: c:cytosol, e:extracellular space</figcaption>

 | Metabolite ID | Formula  | Name                                                       | Charge | Compartment |
| ------------- | -------- | ---------------------------------------------------------- | ------ | ----------- |
| tpa_c         | $\mathrm{C_8H_4O_4}$   | Terephthalate                                              | -2     | c           |
| tpa_e         | $\mathrm{C_8H_4O_4}$   | Terephthalate                                              | -2     | e           |
| dhchdc_c      | $\mathrm{C_8H_6O_6}$   | (3S,4R)-3,4-Dihydroxycyclohexa-1,5-diene-1,4-dicarboxylate | -2     | c           |
| 3h3h_c        | $\mathrm{C_{20}H_{37}O_5}$ | 3-hydroxydecanoyl-3-hydroxydecanoate                       | -1     | c           |
| 3h3h_e        | $\mathrm{C_{20}H_{37}O_5}$ | 3-hydroxydecanoyl-3-hydroxydecanoate                       | -1     | e           |
| lrhh_c        | $\mathrm{C_{26}H_{47}O_9}$ | L-rhamnosyl-3-hydroxydecanoyl-3-hydroxydecanoate           | -1     | c           |
| lrhh_e        | $\mathrm{C_{26}H_{47}O_9}$ | L-rhamnosyl-3-hydroxydecanoyl-3-hydroxydecanoate           | -1     | e           |

<figcaption class="caption table_caption"> Table 2. Definition of newly added reactions, EX_ prefix for exchange reactions </figcaption>

| Reaction ID    | Name                         | Metabolites                                                  |
| -------------- | ---------------------------- | ------------------------------------------------------------ |
| EX_tpa_e       | Terephthalic acid exchange   | tpa_e: -1                                                    |
| TPA_transport  | TPA_transport                | tpa_e: -1, tpa_c: 1                                          |
| TPHA123        | TPA Dioxygenase Reaction     | tpa_c: -1, o2_c: -1, nadph_c: -1, h_c:  -1, dhchdc_c: 1, nadp_c: 1 |
| TPHB           | Diol Dehydrogenase Reaction  | dhchdc_c: -1, nadp_c: -1, dhbz_c: 1,  co2_c: 1, nadph_c: 1   |
| RHLA           | Rhamnosyltransferase chain A | hydroxydecanoyl_acp: -2, h2o_c: -1,  hydroxydecanoyl_hydroxydecanoate: 1, h_c: 1, ACP_c: 2 |
| RHLB           | Rhamnosyltransferase chain B | hydroxydecanoyl_hydroxydecanoate: -1,  dtdprmn_c: -1, dtdp_c: 1, h_c: 1, lrhh_c: 1 |
| EX_lrhh_e      | lrhh exchange                | lrhh_e: 1                                                    |
| lrhh_transport | lrhh_transport               | lrhh_c: -1, lrhh_e: 1                                        |

#### Model Performance Evaluation

We assessed the level of performance of our GSMM using the metrics given in the Memote v0.14.0 [^4]software, which provides quality control and assurance metrics consistent with the consensus on the ideal construction of the GSMM, organized into four categories: annotations, basic tests, biomass reactions, and chemometrics. Annotation tests ensure that cross-references in SBML-formatted models are complete and MIRIAM-compliant, which is critical for the extension and use of GSMM . The basic test ensures that the model is formally correct, the biomass test evaluates consistent growth in different media, and the stoichiometry test ensures that mass and energy inconsistencies are removed from the model.

#### Implementation of dFBA (time-resolved simulation)

For dFBA simulations, the initial medium composition was set to 200 mmol TPA as the carbon source, leaving the glucose content at 0 to assess growth in a TPA-rich environment. Other essential non-carbon metabolites (e.g., oxygen, carbon dioxide, water, etc.) were set to 1000 mmol to ensure that growth simulations were not limited by them. The fluxes are calculated and multiplied by a small, constant time interval to give the approximate change in media composition over the time frame. A time step of 0.1 h was found to give good resolution with moderate calculation time. Subtracting this change from the initial medium composition gives a new initial medium composition. [^5] The process is repeated until the dFBA solution function reaches the computational limit. At each time step, store the media concentration vector for plotting and analysis.

You can <a href="https://static.igem.wiki/teams/5175/resources/model/model-gssm-attachment-01.csv" target="_blank">click here</a> to download the original ingredient of the culture medium.

### Results

#### Model performance evaluation

Norsigian et al. (2020) evaluated the Memote scores of models published in Bigg and found that models in JSON format had an average score of 58% and models in SBML format had an average score of 73%.[^5] Our model is in SBML format with a score of 76% (Figure 1), exceeding the average level of published models. There is reason to believe that our model can reflect the actual situation to a certain extent.

{% include figure.html image="https://static.igem.wiki/teams/5175/resources/model/model-gssm-01.png" alt="Our Memote Score" caption="Fig 1. Our Memote Score" %}

#### Dynamic Flux Balance Analysis (dFBA) Modeling

The metabolic activities of the engineered *P.putida* in a TPA-rich culture environment were modeled by using dFBA to qualitatively evaluate the TPA-processing and rhamnolipid-producing capabilities of the engineered bacteria, respectively.

The simulations predicted the evolution of the engineered bacteria as expected, with *P.putida* successfully growing in an environment where TPA was the main carbon source, suggesting that the strain possesses an efficient TPA metabolism. The TPA content continued to decrease and a small amount of rhamnolipid production began after a certain amount of biomass accumulation. In the early stage, the cells may concentrate their resources on growth, and once a certain biomass is reached, the metabolic pathway gradually shifts to the synthesis of secondary metabolites, such as rhamnolipids. Predicting the timing of the onset of rhamnolipid production and yield changes by dFBA will provide ideas for optimizing production conditions.

{% include figure2.html images=page.images01 %}

## Discussion

We completed a time-resolved engineered *P.putida* genome-scale metabolic model modified iJN1463. Memote demonstrates the completeness and reliability of our model. We hope that future teams can improve its accuracy and validation with further growth and metabolomics data.

Growth curves generated using time-dependent dFBA showed the expected general trend. However, it was not possible to experimentally determine a potential estimated microplastic degradation rate. Modeling the rate of microplastic depolymerization itself was challenging because the model was unable to predict the intensity of enzyme expression, which is directly correlated with the rate of degradation.

Without further validation of our model, it is not possible to derive growth behavior in large bioreactors from the model because scaling up is likely not as simple as multiplying the flux by a specific factor. It would be necessary to perform additional growth experiments in the laboratory using different sized bioreactors to fine-tune the model and potentially predict each parameter as a function of the other. Additional data can then be integrated into the dFBA model to optimize the parameters.

The dFBA simulation can be further improved by allowing metabolic fluxes to become substrate concentration-dependent. Michaelis-Menten kinetics can be used to address this issue, however, the vmax and Km values required for genome-scale metabolic modeling do not exist. Mass action kinetics may be a valuable alternative to approximate growth rates. Including substrate concentration-dependent fluxes would allow more accurate prediction of the transition from exponential to stable phase.

Despite of these limitations, we remain confident that metabolic modeling will continue to contribute to the future progress of the project, and through continued collaboration with the wetlab team we can improve the models while optimizing the wetlab experiments.




{% include button.html link="../" text="Go back to Model Introduction" %}

---

## References

[^1]: Heirendt L, Arreckx S, Pfau T, et. al. Creation and analysis of biochemical constraint-based models using the COBRA Toolbox v.3.0. Nat Protoc. 2019 Mar;14(3):639-702. doi: 10.1038/s41596-018-0098-2. PMID: 30787451; PMCID: PMC6635304. 
[^2]: Ebrahim A, Lerman JA, Palsson BO, Hyduke DR. COBRApy: COnstraints-Based Reconstruction and Analysis for Python. BMC Syst Biol. 2013 Aug 8;7:74. doi: 10.1186/1752-0509-7-74. PMID: 23927696; PMCID: PMC3751080. 
[^3]: Nogales J, Mueller J, Gudmundsson S, et, al. High-quality genome-scale metabolic modelling of <i>Pseudomonas putida</i> highlights its broad metabolic capabilities. Environ Microbiol. 2020 Jan;22(1):255-269. doi: 10.1111/1462-2920.14843. Epub 2019 Nov 11. PMID: 31657101; PMCID: PMC7078882. 
[^4]: Lieven C, Beber ME, Olivier BG, et. al. MEMOTE for standardized genome-scale metabolic model testing. Nat Biotechnol. 2020 Mar;38(3):272-276. doi: 10.1038/s41587-020-0446-y. Erratum in: Nat Biotechnol. 2020 Apr;38(4):504. doi: 10.1038/s41587-020-0477-4. PMID: 32123384; PMCID: PMC7082222. 
[^5]: Norsigian CJ, Pusarla N, McConn JL, Yurkovich JT, Dräger A, Palsson BO, King Z. BiGG Models 2020: multi-strain genome-scale models and expansion across the phylogenetic tree. Nucleic Acids Res. 2020 Jan 8;48(D1):D402-D406. doi: 10.1093/nar/gkz1054. PMID: 31696234; PMCID: PMC7145653. 
