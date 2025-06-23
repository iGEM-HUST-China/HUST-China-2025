---
title: Design
permalink: /design/
feature_text: |
  ## Design
  This page contains the design of the wet-lab part of our project.
feature_image: "https://static.igem.wiki/teams/5175/resources/background/bg-design.webp"
excerpt: "This page contains the design of the wet-lab part of our project."
---

## OVERVIEW

From 1950 to 2015, approximately 8.3 billion tons of plastics were produced globally, of which up to 79 % of waste plastics were disposed of in landfills or leaked into the environment. These large amounts of plastic gradually break down into microplastics over time. Microplastics enter oceans, lakes and other bodies of water mainly through rivers and rainwater runoff. Wastewater treatment plants are often unable to fully filter microplastics, so they also enter natural water bodies through wastewater discharges and end up in the soil as soil contaminants. These particles can damage soil structure and quality, leading to reduced crop yields and altering important properties such as weight capacity and water retention. More seriously, crops may absorb these microplastics, compromising their ability to effectively absorb nutrients and water. 

To address these issues, we designed a metabolically coupled system for simultaneous degradation of microplastics and synthesis of fertilizer for the fermentation culture of *Escherichia coli* BL21 and *Pseudomonas putida* KT2440, and introduced the FAST-PETase-MHETase dual enzyme system to enable engineered *E.coli* to degrade polyethylene terephthalate from polymers into monomers. The tph gene cluster (tphA2-tphA3-tphB-tphA1, tpaK) was introduced for the complete uptake and utilization of terephthalic acid (TPA), and rhlA-rhlB conferred *P.putida* the ability to produce mono-rhamnolipids.

In order to enhance the viability of *E.coli* and at the same time increase the rhamnolipid production in *P.putida*, we also modified their metabolic pathways to some extent by overexpressing the ethylene glycol (EG) utilization pathway (fucO-aldA) in *E.coli* and the polyhydroxyalkanoates (PHA) degradation pathway (phaZ) in *P.putida*, thus optimizing the ability of the engineered bacteria to utilize different carbon sources and altering the direction of intracellular carbon flow.

## Chassis strains: *Escherichia coli* BL21 and *Pseudomonas putida* KT2440

*Escherichia coli* BL21 (*E.coli* BL21) is one of the most commonly used strains for prokaryotic expression. As a well-studied chassis organism, *E.coli* is simple to genetically modify, easy to cultivate, and is a common chassis for the secretion of heterologous proteins. *E.coli* BL21 secretes PET-degrading enzymes for the degradation of PET polymers.

*Pseudomonas putida* KT2440 (*P.putida* KT2440) is a bacterium widely used in scientific research and environmental management, with a variety of unique biological properties and metabolic capabilities. KT2440 is capable of degrading a wide range of environmental pollutants, including certain plastics and organic pollutants, which makes it an important application in the field of biodegradation, and its abundant metabolic pathways can be used to biosynthesize a variety of value-added from renewable resources chemical substances [^1]. In addition, the genome of KT2440 was resolved in 2002, making it the first *Pseudomonas putida* strain to be resolved and the first Gram-negative strain to be deemed environmentally safe by the US Department of Health's Recombinant DNA Committee [^2].

### Strategy 1: *E.coli* BL21 degradation of PET and utilization of EG

To degrade PET microplastics, we introduced a PET degradation pathway into *E.coli* BL21. Through this pathway, *E.coli* BL21 can degrade PET polymers into monomers TPA and EG, which can be absorbed and utilized by engineered bacteria.

Polyethylene terephthalate (PET) is a synthetic polyester with a high proportion of aromatic components, which is chemically inert and normally unavailable to most microorganisms. To degrade PET, we introduced FAST-PETase and MHETase to degrade PET polymers into the monomers TPA and EG.

PETase and MHETase are from the strain *Ideonella sakaiensis* 201-F6, and PET can be degraded by the synergistic action of the two enzymes[^3]. FAST-PETase is a machine-learning obtained PETase with properties suitable for in situ PET degradation at mild temperatures and moderate pH conditions[^4].
                                               
However, the main product of PETase degradation of PET is MHET, and the MHET intermediate tends to bind tightly to PET degrading enzyme in a non-catalytic pose, which leads to the inhibition of PET degrading enzyme. Therefore, an efficient MHET hydrolase is needed to degrade the intermediate product in time to further depolymerise MHET into its monomers TPA and EG[^5]. Multi-enzyme systems promote substrate channeling and proximity effects between enzymes. This greatly reduces the diffusion limitation between enzyme active centers, thus promoting enzyme synergy and improving catalytic efficiency[^6]. In the process of constructing a dual enzyme system, we used bioinformatics to simulate the molecular docking of the linker connecting the two enzymes, and after simulation prediction, we chose the G4S flexible peptide as the linker of FAST-PETase and MHETase, and constructed the two into a dual enzyme system. Moreover, considering the process of constructing the dual enzyme system, the N/C-terminal arrangement of PETase/MHETase may have an impact on its overall conformation, which in turn affects its physiological activity in degrading PET. Therefore, we constructed different systems and hoped to demonstrate the difference in their activities. We hoped that *E.coli* could exocytosis the PETase-MHETase dual enzyme system to degrade PET microplastics in the environment. To this end, the pelB signal peptide was added to enhance the ability of BL21 to secrete PETase-MHETase [^7].

{% include figure.html image="https://static.igem.wiki/teams/5175/resources/design-2/design-01.png" alt=" " caption="Fig 1. Schematic diagram of FAST-PETase, MHETase dual enzyme system function" %}

The final products of PET degradation by the two-enzyme system are TPA and EG. However, wild-type *E.coli* cannot rapidly utilize these substances for various life activities. In order to increase the efficiency of E. coli in utilizing the PET degradation products and to improve its viability, we overexpressed L-1,2-propanediol oxidoreductase and aldehyde dehydrogenase A. This modification was able to increase *E.coli* 's ability to efficiently utilize EG.

We chose fucO as the gene for L-1,2-propanediol oxidoreductase and aldA as the gene for aldehyde dehydrogenase A. L-1,2-propanediol oxidoreductase is an iron-dependent group III dehydrogenase [^8], and aldehyde dehydrogenase A is an enzyme with a relatively broad substrate specificity for small hydroxy aldehyde substrates [^9]. EG is first converted in *E.coli* to glycolaldehyde (GLA) by L-1,2 -propylene glycol oxidoreductase, which is subsequently converted to glycolic acid (GA) by aldehyde dehydrogenase A. GA can be metabolized by condensation with acetyl coenzyme A via the glyoxalate shunt to form malic acid. GA can also enter the metabolic pathway of H. coli by condensing with succinate via isocitrate lyase (encoded by the aceA gene), forming isocitrate [^10]. 

{% include figure.html image="https://static.igem.wiki/teams/5175/resources/design-2/design-02.png" alt=" " caption="Fig 2. Diagram of EG metabolic pathway in <em>E. coli</em>" %}

### Strategy 2: Utilization of TPA by *Pseudomonas putida* KT2440

*Pseudomonas putida* is a common soil microorganism with abundant metabolic pathways and the ability to adapt to harsh environmental conditions and a variety of physicochemical stresses, making it a flexible and engineered metabolic engineering platform in synthetic biology [^11], and the complete biosafety of the strain also makes it a common strain for environmental management and soil modification.
​     
However, wild-type *P.putida* is unable to directly take up and utilize TPA, which is naturally possessed in the β-ketoadipic acid pathway(PCA-4,5-cleavage-pathway) in which protocatechuic acid (PCA) is a metabolic intermediate [^12], and in certain strains that are able to degrade TPA based on this way, TPA can be converted to PCA. Therefore, one of the keys to the modification of KT2440 is the conversion of TPA to PCA

{% include figure.html image="https://static.igem.wiki/teams/5175/resources/design-2/design-03.png" alt=" " caption="Fig 3. β-ketoadipic acid pathway of <em>P.putida</em>" %}

*P.putida* KT2440 contains the introduced heterologous gene cluster (tphA2, tphA3, tphB, tphA1) from *Comamonas sp.*E6, which results in the conversion of *P.putida* intracellular TPA to PCA [^13], and each of the genes in the tph gene cluster collaborates in the conversion of TPA in *P.putida*.

TPA 1,2-dioxygenase (TPADO) is a two-component oxygenase consisting of three parts, TphA1, TphA2, and TphA3, which together enable TPADO to effectively catalyze the oxidative reaction of TPA, converting TPA to the intermediate product 1,2-dihydroxy-3,5-cyclohexadiene-1,4-dicarboxylic acid (DCD). TphB is a dehydrogenase that oxidizes the diol moiety (two hydroxyl groups) of DCD to a keto group, resulting in the production of PCA.TphA2, TphA3 constitute the large and small subunits of the TPADO oxidase component responsible for binding to the TPA substrate and catalyzing the oxygenation reaction in the active site.TphA2 contains the active site in direct contact with the substrate, TPA, and contains the Cys-X1-His X17-Cys-X2-His pattern, binds to Rieske-type [2Fe-2S] iron-sulfur clusters and participates in electron transfer, which is a key part of the catalytic reaction of dioxygenases , TphA3 participates in the construction of the substrate channel or the appropriate positioning of the active site, and assists TphA2 in completing the oxidation reaction; TphA1 does not directly participate in the oxygenation reaction, but it contains a [2Fe -2S] iron-sulfur cluster and a flavin adenine dinucleotide (FAD) binding site that transfers electrons from an electron donor (e.g., NADPH) to the oxidized component of TPADO [^14].     

{% include figure.html image="https://static.igem.wiki/teams/5175/resources/design-2/design-04.png" alt=" " caption="Fig 4. tph gene cluster core mechanism of converting TPA to PCA" %}

Due to the slow passive diffusion of aromatic carboxylates across the phospholipid bilayer of the bacterial inner membrane [^15], we believe that the introduction of TPA transporter proteins is necessary for the transformation of *P.putida*.

In *Comamonas sp.* E6, the TPA transport system resembles a three-part tripartite tricarboxylate transporter (TTT), which consists of three components, TphC, TpiA, and TpiB, with TphC acting as a Substrate-Binding TphC specifically recognizes and binds TPA as a Substrate-Binding Protein (SBP); TpiA and TpiB are transmembrane proteins that form part of the transporter protein complex, whereas TphC delivers TPA from the periplasm (extracellular space) to these membrane proteins. Thus only when tphC and tpiA and tpiB genes are introduced simultaneously, our engineered bacteria can transport TPA [^16]. While TpaK, another TPA transporter protein encoded in *Rhodococcus sp.* RHA1, does not require the presence of tpiA or tpiB to function as a transporter, we chose TpaK as the TPA transporter protein to be applied in engineering *P.putida*[^17]. 

{% include figure.html image="https://static.igem.wiki/teams/5175/resources/design-2/design-05.png" alt=" " caption="Fig 5. TPA transport pattern of TphC and TpaK" %}
​            
### Strategy 3: Synthesis of rhamnolipids and pathway optimization by *Pseudomonas putida* KT2440

We wanted to enhance the usefulness of our system for agricultural production by producing plant-friendly products while degrading microplastic-accumulating biomass. To this end, we introduced the rhlA and rhlB genes to allow *P.putida* to produce mono-rhamnolipids.

Rhamnolipid is a biosurface activator first isolated from *Pseudomonas aeruginosa* by Jarvis and Johnson [^18], Rhamnolipid emulsifies, disperses, and solubilizes hydrophobic organic pollutants and improves their bioavailability, facilitating the removal of hydrophobic organic pollutants. Rhamnolipids also have some metal chelating ability and are used to remove heavy metals from soil, sewage and other liquids. In agricultural applications, rhamnolipids can be used to improve soil, enhance the effects of pesticides and fertilizers, and inhibit agricultural diseases.

Rhamnosyltransferase I is a key enzyme necessary for the synthesis of rhamnolipids, which is a complex enzyme containing 2 subunits, RhlA and RhlB, encoded by the rhlAB gene on the same manoeuvre rhlABRI. Among them, RhlA encoded by the rhlA gene is a phthalyltransferase responsible for the synthesis of β-hydroxy fatty acids [^19], whereas RhlB encoded by the rhlB gene is responsible for catalyzing the synthesis of mono-rhamnolipids containing one rhamnose group from dTDP-L-rhamnose and β-hydroxy fatty acids [^20].
​     
PHA are a class of biopolyesters with plastic-like properties produced by microorganisms under nutrient-limited conditions [^21]. *P.putida* synthesizes PHA via the fatty acid β-oxidation pathway and fatty acid de novo synthesis pathway, which serves as an intracellular storage material for energy and carbon sources. Whereas during PHA synthesis, it competes with rhamnolipid synthesis for the same substrate, β-hydroxyl-ACP. In order to increase the proportion of the carbon source utilized by *P.putida* that flows to the rhamnolipid synthesis pathway, we overexpressed the gene encoding the poly(3-hydroxyalkanoate) depolymerase gene phaZ to inhibit PHA anabolic passway and to increase rhamnolipid production.[^22]

{% include figure.html image="https://static.igem.wiki/teams/5175/resources/design-2/design-06.png" alt=" " caption="Fig 6. Engineered rhamnolipid synthesis pathway in P.putida" %}

### Strategy 4: Metabolic coupling of *E.coli* BL21 and *P.putida* KT2440 for degradation of microplastics in water and agricultural production

Considering the difference in growth conditions and fermentation methods between *E. coli* and *P.putida*, we referenced the previous year's setup and separated the *E.coli* fermentation system from the *P.putida* fermentation system by using top and bottom tanks, with *E.coli* in the top tank being responsible for secretion of PET hydrolysis enzymes and utilizing a portion of the degradation product, EG, while *P.putida* was responsible for utilizing the other product of PET degradation, TPA, and the remaining EG in the bottom tank. Rhamnolipids are fermented to produce rhamnolipids, and the final rhamnolipids are sprayed into the soil to improve agricultural yields. For detailed hardware design, please refer to the [Hardware](../hardware).


{% include figure.html image="https://static.igem.wiki/teams/5175/resources/design-2/design-07.png" alt=" " caption="Fig 7. Sample lab diagram of the application hardware" %}

{% include button.html text="Click here to see the Hardware page" link="../hardware/" %}

## Pathway construction

We designed a total of three plasmids in *E.coli* BL21 and *P.putida* KT2440 respectively.

### In *E.coli* BL21

pPeteg-P: pT7-lac operator-PETase-MHETase-T7-pT7-fucO-aldA-T7
    
​For FAST-PETase-MHETase, fucO, and aldA genes, we chose the T7 promoter to ensure their higher level of expression. And the lactose manipulator was added before FAST-PETase-MHETase to control gene expression. 

{% include figure.html image="https://static.igem.wiki/teams/5175/resources/design-2/design-08.png" alt=" " caption="Fig 8. schematic diagram of pPeteg-P" %}

pPeteg-M: pT7-lac operator -MHETase-PETase -T7-pT7-fucO-aldA-T7
    
For MHETase-FAST-PETase, fucO, and aldA genes, we chose the T7 promoter to ensure their higher level of expression. And the lactose manipulator was added before FAST-PETase-MHETase to control gene expression. 

{% include figure.html image="https://static.igem.wiki/teams/5175/resources/design-2/design-09.png" alt=" " caption="Fig 9. schematic diagram of pPeteg-M" %}

### in *P.putida* KT2440

pTerephthalate: pT7- tphA2-tphA3-tphB-tphA1-T7-pT7- tpaK-T7

For both the heterologous genes tphA23B1 and tpaK, the T7 promoter was chosen to ensure their efficient expression.

{% include figure.html image="https://static.igem.wiki/teams/5175/resources/design-2/design-10.png" alt=" " caption="Fig 10. Schematic representation of pTerephthalate-A" %}

pRhamnolipid: pT7-lac operator-rhlA-rhlB-T7-pT7-lac operator-phaZ-T7
    
Both use the T7 promoter and lac operator to express rhlAB and phaZ to control the production of rhamnolipids by *P.putida*. 

{% include figure.html image="https://static.igem.wiki/teams/5175/resources/design-2/design-11.png" alt=" " caption="Fig 11. schematic representation of pRhamnolipid" %}

---

## References

[^1]: LORENZO V D, PéREZ-PANTOJA D, NIKEL P I. <i>Pseudomonas putida</i> KT2440: the long journey of a soil-dweller to become a synthetic biology chassis [J]. Journal of Bacteriology, 2024, 206(7): e00136-24.
[^2]: GU L F, HE J, HUANG X, et al. [Construction of a versatile degrading bacteria <i>Pseudomonas putida</i> KT2440-DOP and its degrading characteristics] [J]. Wei Sheng Wu Xue Bao, 2006, 46(5): 763-6.
[^3]: YOSHIDA S, HIRAGA K, TAKEHANA T, et al. A bacterium that degrades and assimilates poly(ethylene terephthalate) [J]. Science, 2016, 351(6278): 1196-9.
[^4]: LU H, DIAZ D J, CZARNECKI N J, et al. Machine learning-aided engineering of hydrolases for PET depolymerization [J]. Nature, 2022, 604(7907): 662-7.
[^5]: ZHANG J, WANG H, LUO Z, et al. Computational design of highly efficient thermostable MHET hydrolases and dual enzyme system for PET recycling [J]. Communications Biology, 2023, 6(1): 1135.
[^6]: ZHANG Y, HESS H. Toward Rational Design of High-efficiency Enzyme Cascades [J]. ACS Catalysis, 2017, 7(9): 6018-27.
[^7]: CUI L, QIU Y, LIANG Y, et al. Excretory expression of IsPETase in <i>E. coli</i> by an enhancer of signal peptides and enhanced PET hydrolysis [J]. International Journal of Biological Macromolecules, 2021, 188: 568-75.
[^8]: MONTELLA C, BELLSOLELL L, PéREZ-LUQUE R, et al. Crystal structure of an iron-dependent group III dehydrogenase that interconverts L-lactaldehyde and L-1,2-propanediol in <i>Escherichia coli</i> [J]. J Bacteriol, 2005, 187(14): 4957-66.
[^9]: ZHU Y, LIN E C. Loss of aldehyde dehydrogenase in an <i>Escherichia coli</i> mutant selected for growth on the rare sugar L-galactose [J]. J Bacteriol, 1987, 169(2): 785-9.
[^10]: PANDA S, FUNG V Y K, ZHOU J F J, et al. Improving ethylene glycol utilization in <i>Escherichia coli</i> fermentation [J]. Biochemical Engineering Journal, 2021, 168: 107957.
[^11]: NIKEL P I, DE LORENZO V. <i>Pseudomonas putida</i> as a functional chassis for industrial biocatalysis: From native biochemistry to trans-metabolism [J]. Metab Eng, 2018, 50: 142-55.
[^12]: HARWOOD C S, PARALES R E. THE β-KETOADIPATE PATHWAY AND THE BIOLOGY OF SELF-IDENTITY [J]. Annual Review of Microbiology, 1996, 50(Volume 50, 1996): 553-90.
[^13]: SASOH M, MASAI E, ISHIBASHI S, et al. Characterization of the Terephthalate Degradation Genes of Comamonas sp. Strain E6 [J]. Applied and Environmental Microbiology, 2006, 72(3): 1825-32.
[^14]: KINCANNON W M, ZAHN M, CLARE R, et al. Biochemical and structural characterization of an aromatic ring-hydroxylating dioxygenase for terephthalic acid catabolism [J]. Proc Natl Acad Sci U S A, 2022, 119(13): e2121426119.
[^15]: VERMAAS J V, DIXON R A, CHEN F, et al. Passive membrane transport of lignin-related compounds [J]. Proc Natl Acad Sci U S A, 2019, 116(46): 23117-23.
[^16]: HOSAKA M, KAMIMURA N, TORIBAMI S, et al. Novel tripartite aromatic acid transporter essential for terephthalate uptake in Comamonas sp. strain E6 [J]. Appl Environ Microbiol, 2013, 79(19): 6148-55.
[^17]: PATRAUCHAN MARIANNA A, FLORIZONE C, DOSANJH M, et al. Catabolism of Benzoate and Phthalate in Rhodococcus sp. Strain RHA1: Redundancies and Convergence [J]. Journal of Bacteriology, 2005, 187(12): 4050-63.
[^18]: JARVIS F G, JOHNSON M J. A Glyco-lipide Produced by <i>Pseudomonas Aeruginosa</i> [J]. Journal of the American Chemical Society, 1949, 71(12): 4124-6.
[^19]: ZHU K, ROCK CHARLES O. RhlA Converts β-Hydroxyacyl-Acyl Carrier Protein Intermediates in Fatty Acid Synthesis to the β-Hydroxydecanoyl-β-Hydroxydecanoate Component of Rhamnolipids in <i>Pseudomonas aeruginosa</i> [J]. Journal of Bacteriology, 2008, 190(9): 3147-54.
[^20]: WITTGENS A, TISO T, ARNDT T T, et al. Growth independent rhamnolipid production from glucose using the non-pathogenic <i>Pseudomonas putida</i> KT2440 [J]. Microb Cell Fact, 2011, 10: 80.
[^21]: LIU H, CHEN Y, ZHANG Y, et al. Enhanced production of polyhydroxyalkanoates in <i>Pseudomonas putida</i> KT2440 by a combination of genome streamlining and promoter engineering [J]. International Journal of Biological Macromolecules, 2022, 209: 117-24.
[^22]: 尹进, 车雪梅, 陈国强. 聚羟基脂肪酸酯的研究进展 [J]. 生物工程学报, 32(6): 726-37.

 