---
title: Human Practices
permalink: /human-practices/
feature_text: |
  ## Human Practices
  An excellent humanistic practice is one of the pillars of a responsible and beneficial iGEM project for the world.
feature_image: "https://static.igem.wiki/teams/5175/resources/background/bg-hp.jpg"
excerpt: "Welcome to iGEM HUST-China 2024 wiki! It's still under construction. Please stay tuned for more information."
---

## Overview

An excellent humanistic practice is one of the pillars of a responsible and beneficial iGEM project for the world. Through humanistic practices, we hope that our project will be able to solve real-life problems in a more practical way and understand how society perceives our project.

Our project aims to use engineered *E.coli* and engineered *P.putida* to degrade microplastics in agricultural fields in order to reduce the harmful effects of microplastics on agricultural fields and humans. To understand the extent of the microplastic problem, we integrated academic research and conducted field studies; we discussed our project with microplastic degradation experts and companies involved in environmental protection to gather their insights into finding more realistic, efficient and convenient solutions to microplastics; and we discussed bioethics with social organizations and gathered grassroots government views on biotechnology. By integrating a wide range of perspectives, from the people to the corporate government, we hope to provide a variety of suggestions and views that may be needed to inspire other iGEMers in all aspects of the project.


## Topic Selection 
**Section 1: Topic Selection--Aware Microplastic Pollution in Agriculture**

During the summer of 2023, while participating in our university's "Triple Services Activity into Rural Areas" social practice activities, we accidentally observed the alarming presence of black and transparent plastic bag waste piled up beside rice fields. This litter starkly contrasted with the beautiful natural environment and was in direct contact with the food destined for local households. Such a scene raised our concerns about whether plastic waste could contaminate and harm farmland. Motivated by these questions, we conducted a thorough literature review.

{% include figure.html image="https://static.igem.wiki/teams/5175/resources/hp/hp-01.webp" caption="Fig 1. Plastic Waste in Agricultural Fields" %}

According to the Food and Agriculture Organization (FAO),  the agricultural industry chain consumes 12.5 million tons of plastic products every year, and the consumption of food packaging is as high as 37.3 million tons. Experts predict that the increased demand for greenhouse films, mulch films, and silage films will lead to a 50% or greater increase in plastic usage within the agricultural sector in the coming years. In Asia, around 30 million acres of land require 1.45 million tons of mulch plastic film each year, representing 75% of global plastic film consumption.[^1] And what is worse, the degradation of these materials in soil is exceedingly poor; for instance, polyethylene films may take 300 to 400 years to decompose completely in soil. In China, approximately 200,000 to 300,000 tons of residual film remain in agricultural fields each year, leading to high concentrations of microplastics(MP) accumulating in the soil.

Research indicates that MP can change soil properties. They affect environmental conditions, such as soil bulk density and water retention capacity, by modifying soil aggregate structure and porosity. For example, adding 0.3% of polystyrene (PS) fibers with a particle size of 5 μm can promote soil aggregate formation, increase soil porosity, and reduce water retention capacity. In addition,0.4% of polypropylene (PP) fibers at 18 μm and PS fibers at 8 μm can decrease soil aggregation, resulting in soil degradation.[^2] Changes in soil porosity and water retention may impact oxygen levels, thereby altering the diversity and distribution of both aerobic and anaerobic microorganisms, ultimately interfering with crop growth. MPs also significantly affect carbon storage in agricultural soils, impacting nitrogen and phosphorus cycles as well as microbial activity.[^3]

The presence of MPs in soil can also disrupt plant growth by interfering with metabolic processes, leading to oxidative stress in plants, increasing the bioavailability and toxicity of heavy metals, and reducing soil bulk density, which ultimately decreases yield and crop quality. Additionally, nanoparticles of plastic (<100 nm) can be absorbed by root systems and transferred to the above-ground parts of plants, serving as a main source of MPs in food.[^4]

Numerous studies have highlighted the dangers of MPs to human health. For instance, in cardiovascular research, the accumulation of MPs and nanoplastics has been closely linked to the formation of atherosclerotic plaques and cardiovascular events. These particles can penetrate biological barriers, enter the vascular endothelium, exacerbate inflammatory responses, and increase the risks of cardiovascular diseases and thrombosis. [^5]

Furthermore, a study targeting pregnant women in Hawaii found MP particles in approximately 12% of placenta samples, suggesting that these particles may be transmitted from mother to fetus and could disrupt normal placental functions, affecting fetal development and increasing risks of preterm birth, miscarriage, and fetal malformations. [^6]Given these findings, it is evident that addressing the issue of MP pollution is critical. Therefore，our team aims to provide a synthetic biology solution to mitigate MP pollution in agricultural settings.

## Background Investigation 

**Section 2: Background Investigation--Exploring Solutions for MP Pollution & Targeting the PET**

To gain deeper insights into the impact of MPs on agricultural ecosystems, we shared our ideas with Professor Yongming Luo from the Nanjing Institute of Soil Science, Chinese Academy of Sciences. Since Professor Luo was on a business trip, we had an in-depth communication online. He specializes in soil pollution processes and remediation, with significant achievements in the evolution and regulation of regional soil environmental quality, risk assessment and benchmark standards for soil environments, principles and techniques for the remediation of polluted soils, and the soil processes and food chain transmission of emerging pollutants like MPs.

During the conversation, Professor Luo introduced the current research status of MP to us. He mentioned that approximately 90% of globally produced MPs enter the soil environment through various pathways, including infiltration, wind erosion, diffusion, and runoff. Studies have shown that in 347 cities in China, the penetration depth of microplastics into the soil increases by 1.48~7.42 m per 100 years, with an average penetration depth of 5.24 meters.[^7] In addition to residual film, urban solid waste is another significant source of MPs in soils. During water treatment processes, sludge can recover 70% to 99% of MPs, with concentrations reaching 10³ to 10⁵ particles/kg, leading to significant MP accumulation in soils. Urban landfills represent point sources of soil MPs, as leachate generated from landfill waste contains a high concentration of MP pollutants. The long-term accumulation of waste exacerbates MP pollution in the soil. We contemplated whether we could utilize synthetic biology to engineer a strain of bacteria capable of addressing this issue. Given the rapid metabolism and low cultivation costs of microorganisms, coupled with the potential to engineer high-yield strains through synthetic biology, this could provide a novel solution for MP remediation in soils.

Additionally, Professor Luo outlined the current methods for MP remediation, which can be categorized into three main approaches: physical separation, chemical degradation, and biological degradation. Physical separation involves techniques such as sieving and filtration to isolate MPs from other materials; however, these methods exhibit low efficiency and struggle to remove nanoparticles. Chemical degradation utilizes reagents under specific conditions to further break down MPs into smaller molecules, but the high cost of reagents and potential secondary pollution from improper use pose significant drawbacks. Biological degradation employs microorganisms to decompose MPs into gases, water, and non-toxic substances, making this method particularly applicable for MP remediation in soil and water. Although biological degradation has a lower environmental impact during the decomposition process, the degradation rate is relatively slow and significantly influenced by environmental factors, making precise control challenging. We considered whether we could immobilize enzymes to enhance transport efficiency and convert degradation products into high-value products, rather than solely focusing on MP degradation, thereby achieving a waste-to-resource effect. And in a subsequent literature review, we realised that enzymes cannot remain activity for long in soil or natural waters, and that the use of enzymes to remove microplastics from soil would incur high costs, so we considered applying our idea in the form of a bacteria agent for the treatment of microplastics in soil or water.

{% include figure.html image="https://static.igem.wiki/teams/5175/resources/hp/hp-02.webp" caption="Fig 2. Online Meeting with Professor Yongming Luo" %}

To better understand the methods for plastic waste management and the challenges faced during the process, we visited the Wuhan Green Power Renewable Energy Co., Ltd., the garbage incineration plant in Qingshan District, Wuhan.

During the visit, we observed the waste treatment design of the facility and, through discussions with management and staff, gained insights into the methods and specific processes for urban plastic waste disposal. They explained that while incineration is commonly believed to permanently eliminate plastic waste by converting polymers into carbon dioxide and other inorganic substances, significant amounts of unburned material remain in the ash produced. It is estimated that the average abundance of MPs in ash can reach 100 to 300 particles/kg, with each ton of waste incinerated generating between 360,000 and 1.02 million MP particles.

In our discussions with professionals from the company, we specifically inquired about the composition of MPs in the ash. We learned that nine types of MPs were identified, primarily including polyethylene (PE), polyethylene terephthalate (PET), polystyrene (PS), and polypropylene (PP). Among these, PE constituted the largest proportion, accounting for about 30% of the total; PET followed at approximately 25%. These plastics typically originate from everyday consumer products and packaging, with proportions varying based on regional consumption habits and waste management practices. We also learned that these non-biodegradable ash materials are uniformly landfilled in the suburbs. We speculated that the MPs within this ash could migrate with groundwater, directly influencing the MP composition in agricultural ecosystems. Furthermore, we considered that plastic films from industrial pipelines near the suburbs might also generate MPs through physical erosion, leading to contamination in leachate that could affect the quality of irrigation water. After this exchange, we decided to focus on the more prevalent PE and PET.

{% include figure.html image="https://static.igem.wiki/teams/5175/resources/hp/hp-03.webp" caption="Fig 3. HUST-China Members Visit Plastic Waste Recycling Facility" %}

On another front, we visited Guangzhou Kingfa Technology Co., Ltd. during an open day to inquire about the market for plastics and the development of alternatives. As a leading enterprise in the field of new plastic manufacturing, their R&D encompasses nine categories, including modified plastics, environmentally friendly high-performance recycled plastics, and fully biodegradable plastics. Kinfa Technology has conducted extensive research on the composition of MPs and the utilization of plastic materials, providing them with a comprehensive understanding and judgment on the development situation and trend of plastics.

We presented our focus on the degradation of PET and PE to the company and inquired about the production status, costs, yields, and application scenarios of traditional plastics and their new alternatives. The technical staff affirmed our approach and provided detailed insights into various common plastics. PE is currently the most widely produced resin, known for its excellent electrical insulation and chemical stability, resisting corrosion from most acids, bases, and salts. It is easy to process and is commonly used in everyday items such as cling film and plastic food bags, with a global production capacity of 145 million tons. PET is the most produced polyester plastic globally; due to its outstanding physical properties and plasticity, it is widely used in products like beverage bottles, disposable cup lids, and transparent trays for fruits and vegetables. Furthermore, PET is also the largest source of synthetic fibers, with total production surpassing that of traditional natural fibers. More than 50% of fabrics produced globally are made from PET fibers, with annual production exceeding 100 million tons.

We discussed the future trends in plastic development with the staff. They informed us that the production technologies for new plastics are not yet fully mature and are more expensive; for instance, the unit cost of Poly (butyleneadipate-co-terephthalate)PBAT is 16% higher than that of PE, while Polylactic Acid(PLA)'s unit cost is approximately 50% higher than that of PET. Meanwhile, PET remains a significant component in the MPs used in the production of both existing and new plastics. After all these considerations, we decided to target PET, which is used more and has a smaller alternative possibility.

{% include figure.html image="https://static.igem.wiki/teams/5175/resources/hp/hp-04.webp" caption="Fig 4. Public Open Day Discussion Session in Guangzhou Kingfa Technology Co., Ltd." %}

## Project Initial Design

**Section 3: Project Initial Design--Pathway Establishment & Component Enhancement**

With a sufficient background gathered, we initiated the preliminary design of our project, aiming to provide a solution for the MP issue in soils.

 In selecting chassises, we first considered using *Escherichia coli* due to its well-defined metabolic pathways and common use for protein overexpression. After reviewing the literature and examining the metabolic pathways of *E. coli*, we proposed introducing the genes corresponding to the target proteins PETase and MHETase, which would enable the breakdown of PET into ethylene glycol (EG) and terephthalic acid (TPA).

We focused on various soil microorganisms mentioned in the literature and screened for structural analogues that are similar to TPA in metabolic pathways and can be transformed through a short reaction chain，also without the toxic effects on plants. The most promising candidate was *Pseudomonas putida*. After discussing the project design and application background with Professor Abdelghani Sghir in France, he endorsed our decision to use *Pseudomonas putida* as the chassis bacteria.

{% include figure.html image="https://static.igem.wiki/teams/5175/resources/hp/hp-05.webp" caption="Fig 5. HUST-China Members with Prof. Abdelghani Sghir in France" %}

Ultimately, we selected *E. coli* BL21 and *Pseudomonas putida* KT2440 as our chassises. Through genetic engineering, we aim for *E. coli* BL21 to synthesize and secrete PETase to decompose PET and synthesize MHETase to further break down MHET produced from incomplete PET degradation, ensuring all products convert to EG and TPA, so we plan to construct a PETase~MHETase dual-enzyme system. Additionally, we will overexpress the fucO and aldA genes in *E. coli* BL21, channeling all EG into glycolic acid (GA). GA will then be converted into malate and acetyl-CoA via the ethanolamine pathway, subsequently entering the tricarboxylic acid cycle for metabolism by *E. coli* BL21. For TPA, we plan to introduce the tph gene cluster (tphA2A3A1, tphB) and tpaK into *Pseudomonas putida* KT2440. The TPA transporter protein encoded by tpaK will transport TPA into the cell, where it will be converted into the key metabolic intermediate Protocatechuic acid (PCA) under the action of the tph gene cluster. We will also introduce the PhaC1 gene to transform the metabolic products into polyhydroxyalkanoates (PHA). To strengthen our design, we discussed methods for efficiently adsorbing PET from the soil with Professor Xiaoman Xie, who suggested integrating an adhesion module into our design.

After a thorough literature review and consideration, we decided to incorporate her recommendations into our project. We consider adding an adhesion module to the exoenzyme protein system to facilitate PET adsorption, or alternatively, directly using the enzyme system as membrane protein to adsorb PET. We finally selected an adhesion module that enhances the adhesion of *E. coli* BL21 to PET in the presence of TPA by expressing cp52k. When the plastic concentration is high, the water-soluble nature of PETase makes it difficult to adsorb to the PET surface. As a hydrophobic protein, cp52k can spontaneously polymerize to produce hydrophobic polymers and construct hydrophobic layers on the surface of biofilms. We reported the design to Ms. Xie and she was positive about our idea.

{% include figure.html image="https://static.igem.wiki/teams/5175/resources/hp/hp-06.webp" caption="Fig 6. HUST-China Members with Teacher Xiaoman Xie" %}

Professor Yan Yunjun has high attainments in multi-enzyme catalysis. After learning about our project, he first confirmed our project design, but considering the application scenario and environmental conditions of our project, he suggested that we abandon PHA as the final product and consider fertilizers such as urea as additional products, so that our engineered microorganisms are no longer simply alleviating soil microplastic pollution, it's about reducing pollution while restoring soil and promoting plant growth. However, after reviewing the literature, we found that it was very difficult to construct the pathway between TPA, EG and urea in microorganisms, so we gave up urea, but retained the idea of seeking engineered microorganisms to repair soil quality while reducing pollution provided by teacher Yan, and continued to search for additional products according to this idea.

{% include figure.html image="https://static.igem.wiki/teams/5175/resources/hp/hp-07.webp" caption="Fig 7. HUST-China Members with Prof. Yunjun Yan" %}

As our project progressed, we contacted Associate Professor Sheng Wang, who has been instrumental in the rational molecular design of structures and mechanisms. He confirmed our idea of building a two-enzyme system and suggested that we screen suitable linkers to optimize the two-enzyme system and improve the transport efficiency of intermediate products to enhance catalytic activity. After careful review of the literature, we decided to adopt Associate Professor Wang Sheng's suggestion. After consulting relevant data and screening part of linker for modeling, we used flexible linker G4S to connect PETase and MHETase together to construct a PET-MHET enzyme dual-enzyme system model, and conducted molecular docking experiments to simulate the efficiency of the dual-enzyme system.

{% include figure.html image="https://static.igem.wiki/teams/5175/resources/hp/hp-16.webp" caption="Fig 8. HUST-China Members with Prof. Sheng Wang" %}


## project Design Refinement

**Section 4: Project Design Refinement--Product Design and Design Optimisation**

After clarifying the significance and feasibility of our project, we visited Professor Divya Ail from Saclay University in Wuhan for further advice. After understanding our design, she suggested not using the adhesion module because it relies on strong hydrophobicity, which may not be specific enough in the complex agricultural environment. If the module adsorbs on bacteria, it could affect their growth by encapsulating them, potentially disrupting the microbial growth balance. After a thorough literature review and consideration, we decided to adopt Professor Ail's suggestion, removing the adhesion module and actively exploring other efficient ways to capture PET.

{% include figure.html image="https://static.igem.wiki/teams/5175/resources/hp/hp-08.webp" caption="Fig 9. HUST-China Members with Prof. Divya Ail" %}

In the same month, we visited Hubei Nitrogen Energy Biotechnology Co., a leading soil improvement company in China, pioneering in biological nitrogen fixation, emission reduction, and efficiency enhancement. They have significant expertise in the post-application of agricultural products. We sought to learn from them about product application methods. During our discussion about the applications of PET degradation products, they suggested we further explore high-value degradation products from *Pseudomonas putida* that can be directly utilized for plant growth, making product application more flexible and straightforward. Following this, we identified β-ketoadipic acid (β-KA) and rhamnolipids as targets by researching the metabolic pathways of TPA in *Pseudomonas putida* KT2440.

{% include figure.html image="https://static.igem.wiki/teams/5175/resources/hp/hp-09.webp" caption="Fig 10. HUST-China Members in Hubei Nitrogen Energy Biotechnology Co." %}

We were pleasantly surprised to find that rhamnolipids have numerous benefits in agricultural production. They can act as biosurfactants, enhancing the adhesion of *E. coli* BL21 under surfactant conditions, thereby improving PET capture and degradation capabilities. Additionally, when added to fertilizers, rhamnolipids can enhance wetting, spreading, and penetration, increasing soil moisture retention and promoting plant growth, ultimately improving nutrient absorption efficiency. More importantly, rhamnolipids exhibit broad-spectrum effects against pathogens and have shown excellent control of certain fungal diseases, with widespread application in foreign agricultural production for crop disease prevention. Moreover, rhamnolipids possess chelation functions for trace and metal elements, helping to improve saline soil and reduce nutrient loss, ensuring fertilizer persistence, and alleviating soil compaction and heavy metal contamination. However, current fermentation production primarily relies on the pathogenic bacterium *Pseudomonas aeruginosa*, which poses certain safety risks.[^8]

Ultimately, we abandoned the PHA synthesis pathway originally constructed in *Pseudomonas putida* KT2440, deleting the phaC1 gene; we chose rhamnolipid as our target product. To increase the carbon flux toward rhamnolipid synthesis during metabolism, we overexpressed phaZ to degrade PHA synthesized from β-hydroxyacyl-ACP, enhancing rhamnolipid synthesis. We also introduced the rhlAB genes into *Pseudomonas putida* to enable the synthesis of mono-rhamnolipids, replacing the original adhesion module function and enhancing PET capture capabilities while supplying plant growth and soil improvement needs. We re-established contact with Hubei Nitrogen Energy Biotechnology Co., and they expressed surprise at our findings.

Next, we consulted Prof. Ning Kang from Huazhong University of Science and Technology regarding rhamnolipid production in *Pseudomonas putida*. Professor Ning focuses on biobig data and microbial community exploration and its applications in health and environmental fields. He suggested we utilize dry experiments to simulate metabolic flow, predict engineered bacteria's growth behavior, TPA absorption rates, and rhamnolipid product yields. By refining the genome-scale metabolic model of engineered *Pseudomonas putida*, we could assist future teams in further metabolic engineering of *Pseudomonas putida* while advancing the prospect of utilizing it for plastic degradation.

{% include figure.html image="https://static.igem.wiki/teams/5175/resources/hp/hp-17.webp" caption="Fig 11. HUST-China Members with Prof. Kang Ning" %}

In July, we met again with Professor Divya in Paris to report on our project progress and received further feedback. 

Detailed designs can be found in the design section.

{% include button.html text="Click to see Design Page" link="../design/" %}

## Hardware Design

**Section 5: Hardware Design**

After the research at Hubei Nitrogen Energy Biotechnology Co., we considered adding a suicide switch and designing the system as a microbial agent or microbial fertilizer. It could be applied to the soil to allow the system to autonomously degrade MPs, producing rhamnolipids.

To understand the production and research process of agricultural microbial agents, as well as the development prospects of microbial agents, we visited the National Engineering Research Center for Biological Pesticides. The staff informed us that microbial agents primarily contain bacterial agents and can include or exclude organic matter, existing in various types of bacteria. They mainly supplement soil microbial agents and fermentation products to address issues like soil compaction, resistance to continuous cropping, and crop stress. The use of microbial agents significantly reduces chemical fertilizer use and pollution, and they can enhance plants' resistance to diseases and stress through interactions with other microbes or plants, playing an essential role in improving crop quality, yield, and extending harvest and preservation periods.

The market scale of China's microbial agent industry has been growing year by year, and with the acceleration of agricultural modernization and changes in agricultural production methods, the market scale is expected to continue to grow, reaching 50.24 billion yuan. However, as of now, the mechanisms of action of various microbes in microbial agents remain unclear, and foundational research is severely lacking. To ensure the safety of agricultural ecosystems, the national approval process for microbial agents is very strict. The development of microbial agents is a long-term process, with testing and approval cycles reaching over two years, making it unfeasible in the short term. Considering these factors, we prioritize designing a closed system to ensure safety. 

For future application scenarios, please refer to the Proposed Implementation section.

{% include figure.html image="https://static.igem.wiki/teams/5175/resources/hp/hp-10.webp" caption="Fig 12. HUST-China Members in the National Engineering Research Center for Biological Pesticides" %}

{% include button.html text="Click to see Proposed Implementation Page" link="../proposed-implementation/" %}

After shifting the application direction of our product, we communicated with Researcher Han Huawen from Lanzhou University. She had previously conducted research on PET degradation in soil and was pleased to offer advice for our project. After listening to our design, she affirmed our goal of producing rhamnolipids. She also shared some unresolved issues from her past research, advising us to avoid similar pitfalls, which greatly aided our project advancement. Additionally, she informed us that due to the high complexity of soil environments, estimating the interactions between soil microbial communities and engineered bacteria is challenging. Groundwater, as a crucial part of the soil ecosystem, is closely related to the MP content in the soil. After a thorough literature review, we decided to incorporate their suggestions into our project. We are considering shifting the treatment environment from solid to aquatic to facilitate the enrichment of PET MPs.

After completing the main design of the hardware, we had an online feedback session with Researcher Han Huawen, showcasing our hardware ideas. She expressed approval and encouragement regarding our progress.

{% include figure.html image="https://static.igem.wiki/teams/5175/resources/hp/hp-11.webp" caption="Fig 13. Online Meeting with Researcher Huawen Han" %}

 

We designed a fermentation tank as the main hardware facility. The overall idea is to collect groundwater used for irrigation, enrich PET using strong current and the electronegativity of PET, then mix it with bacterial liquid in the fermentation tank. Through the cooperation of *E. coli* BL21 and KT2440, we can convert PET into rhamnolipids. Finally, we designed a drip irrigation device to apply the liquid rich in rhamnolipids to crops.

 For specific hardware design details, please refer to the Hardware section.

{% include button.html text="Click to see Hardware Page" link="../hardware/" %}

After completing our fermentation tank model, we had an online discussion with Zhendian (Suzhou) Medical Technology Co. regarding our hardware model. They expressed approval of our hardware design and suggested we continue to optimize the function of the adsorption module.

## On-site Research

**Section 6: On-site Research**

After our hardware design was mostly completed and experiments progressed, our team traveled to rural areas in five provinces, including Hubei and Heilongjiang, to conduct field research. We conducted a comprehensive survey of the layout of agricultural land and groundwater used for irrigation, which played a crucial role in selecting the best locations for project implementation, improving hardware design, and determining future application possibilities.

We then engaged in on-site discussions with farmers working in the fields. They expressed ongoing concerns about waste buried in suburban areas, which not only detracts from the environment's aesthetics but also deteriorates water quality when it enters irrigation sources. However, they felt powerless to find suitable solutions. We introduced our project's purpose, and they were astonished. When asked about the hardware's use, they responded positively, stating that as long as it did not affect their normal farming or increase costs, they would be very willing to address soil MP issues.

Furthermore, we communicated with the staff at the grass-roots level in communes and townships in the area. After introducing our project, they also shared their suggestions and opinions. We learned that from the government's perspective, they are most concerned about the efficiency and extent of PET degradation by our product. Although they did raise some questions about the project's potential for widespread and rapid adoption in the short term, they acknowledged the innovative and practical design of our project. Importantly, they expressed confidence that our project would play a significant role in tackling soil MP pollution.

{% include figure.html image="https://static.igem.wiki/teams/5175/resources/hp/hp-12.webp" caption="Fig 14. HUST-China Members Exchange in Rural Areas" %}

## Public Evaluation

**Section 7: Public Evaluation**

To gain a deeper understanding of the progress, social awareness, and future prospects in the field of MP pollution remediation, we visited the Wuhan Ecological Environment Volunteer Service Team to better understand bioethics and comprehensively evaluate the prospects of our project in the remediation of MPs in agricultural fields. 

The head of the volunteer service team indicated that in recent years, MP pollution in farmland soil in Wuhan has become increasingly serious, posing threats to agricultural production and the ecological environment. China's plastic film coverage area for crops is nearly 300 million mu, consuming over 1.3 million tons of plastic film annually, accounting for about 75% of global usage, which greatly exacerbates MP pollution in agricultural fields. To effectively tackle this challenge, the team actively organizes volunteers for farmland cleaning initiatives and collaborates with research institutions for MP pollution monitoring and remediation studies. However, they acknowledged that the effectiveness of cleaning and remediation remains to be improved, and they hope our project can leverage biotechnology to effectively improve the MP pollution status in agricultural fields.

 During our research and interviews with the Wuhan Ecological Environment Volunteer Service Team, we specifically introduced the potential applications of synthetic biology in environmental remediation and emphasized the importance of addressing bioethical issues in this field. The team leader indicated that they believe that with advancements in technology and improvements in policy, the issue of microplastic pollution in agricultural fields is likely to be effectively controlled. In particular, the rapid development of synthetic biology provides new ideas and methods for environmental governance and is expected to play an important role in the future. However, they also stressed the necessity of fully considering bioethical issues in the process of promoting remediation efforts, ensuring the reasonable application of technology and the sustainable development of the ecological environment. Additionally, they recommended that we carefully review guidelines such as the "Environmental Safety Assessment Guidelines for Microbial Agents in Environmental Protection" to ensure the safety and controllability of the technology.

{% include figure.html image="https://static.igem.wiki/teams/5175/resources/hp/hp-13.webp" caption="Fig 15. HUST-China Members with the Wuhan Ecological Environment Volunteer Service Team" %}


## Positive Feedback

**Section 8: Positive Feedback**

Our project is a soil purification system that transforms waste into fertilizer, featuring low costs and no pollution while degrading soil microplastics and increasing crop yields. After completing our project, we submitted a brief project report to Researcher Han Huawen, expressing our gratitude for her valuable suggestions, which significantly contributed to the refinement and improvement of our project. 

Throughout the project development process, Guangzhou Kinfa Technology Co., Ltd. expressed great curiosity about our ideas and followed our project progress. After completion, we reached out to them again to share our final hardware design. They emphasized the importance of achieving high PET concentration and low costs in future developments. They expressed strong confidence in our project and eagerly anticipated its performance in potential industrial applications.

{% include figure.html image="https://static.igem.wiki/teams/5175/resources/hp/hp-15.webp" caption="Fig 16. HUST-China Members Receiving Feedback from Guangzhou Kinfa Technology Co., Ltd." %}

## Integrating Human Practice with Synthetic Biology Education and Communication

**Section 9: Leading Education/Integrating Human Practice with Synthetic Biology Education and Communication**

During interactions with other students at the public open day of Guangzhou Kinfa Technology Co., Ltd., we found that students from other majors were not well-informed about synthetic biology and had certain misconceptions about genetically modified organisms. Therefore, we decided to use interesting themes to educate university students about synthetic biology in a way that integrates it with other cultures. 

While engaging with French professors, we also established friendly communication with French teams. 

During our field research journey, we discovered that the general public is largely unaware of synthetic biology and does not recognize that biological methods have become optimal solutions for many problems. Consequently, we resolved to educate the public about biology and synthetic biology applications. We visited the Wuhan Science and Technology Museum and decided to start our outreach with children—an age group characterized by great curiosity and interest in the world. 

For more details, refer to the Education Page.

{% include button.html text="Click to see Education Page" link="../education/" %}

## References


[^1]:Assessment of agricultural plastics and their sustainability: A call for action[J].
[^2]:WAN Y, WU C, XUE Q, at el. Effects of plastic contamination on water evaporation and desiccation cracking in soil[J/OL]. Science of The Total Environment, 2019, 654: 576-582[2024-10-02]. 
[^3]:吕一涵, 周杰, 杨亚东, 等. 微塑料对农田生态系统的影响:研究现状与展望[J/OL]. 中国生态农业学报(中英文), 2022, 30(1): 1-14. 
[^4]:李连祯, 周倩, 尹娜, 等. 食用蔬菜能吸收和积累微塑料[J/OL]. 科学通报, 2019, 64(9): 928-934. 
[^5]:Wang X, Tian S. Microplastics and Nanoplastics in Atheromas. N Engl J Med. 2024 May 9;390(18):1727. doi: 10.1056/NEJMc2404154. PMID: 38718366.
[^6]: Rodrigo Barbano Weingrill, Men-Jean Lee, Paula Benny, Jonathan Riel, Kevin Saiki, Jacob Garcia, Lais Farias Azevedo de Magalhaes Oliveira, Eduardo Jorge da Silva Fonseca, Samuel Teixeira de Souza, Flavio de Oliveira Silva D'Amato, Ueslen Rocha Silva, Mariana Lima Dutra, Aldilane Lays Xavier Marques, Alexandre Urban Borbely, Johann Urschitz,Temporal trends in microplastic accumulation in placentas from pregnancies in Hawaiʻi,Environment International,Volume 180,2023,108220,ISSN 0160-4120
[^7]:O’CONNOR D. Microplastics undergo accelerated vertical migration in sand soil due to small size and wet-dry cycles[J]. Environmental Pollution, 2019.
[^8]:邢芳芳, 孟祥坤, 徐文凤, 等. 鼠李糖脂在农业上的应用研究[J/OL]. 农业工程技术, 2023, 43(16): 109-111[2024-08-12]. 