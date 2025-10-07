---
title: Human Practices
permalink: /human-practices/
feature_text: |
feature_image: "https://static.igem.wiki/teams/5569/description/hpbg.webp"
excerpt: ""
---

## Human Practices: From Waste Oil to Sustainable Squalane

### Stakeholder Engagement Overview

| Stakeholder Type | Specific Representatives | Role in Ensuring Values |
|------------------|--------------------------|-------------------------|
| Academic & Research Institutions | Prof. Yan Yunjun, Researcher Xie Xiaoman, Prof. Tang Qiang, Prof. Ning Kang, Prof. Sylvain FISSON | Validated the scientific merit and innovation of the technical route, ensured the realization of its scientific value, and provided key guidance on metabolic pathways, computational design, and compartmentalization strategies. |
| Enterprises & Industries | Proya, Bloomage Bio, Wuhan Berca, Hubei Hongfuda, Zhejiang Zhengda Environmental Protection | Ensured project meets market demands and industry standards (Social Values). Clarified safety requirements (Ethical Values), understood waste oil treatment pain points (Environmental Values). |
| Government & Public Institutions | Wuhan Municipal Bureau of Ecology and Environment, Ministry of Agriculture and Rural Affairs | Ensured project complies with national environmental policies and shark protection regulations (Environmental & Ethical Values), advancing within compliant framework. |
| Frontline Producers & Practitioners | Fisherman Uncle Sun from Weihai, Manager Cai from waste oil recycling company | Obtained first-hand information about shark fishing industry and waste oil treatment, ensuring project addresses real social and environmental problems. |
| Engineering & Design Experts | Yang Xuezhi from National Bio-manufacturing Industry Innovation Center, Teacher Wang Jinchun from HUST Engineering Innovation Center | Ensured hardware design has industrial feasibility, considering both durability and contamination resistance. |
| Public & End Consumers | 200+ questionnaire respondents | Directly understood public acceptance, concerns, and preferences, ensuring product positioning aligns with social values and ethical transparency. |

## Part I: Problem Definition & Value Discovery

{% include dropdown.html
   title="Confirming the Unsustainability of Animal-Derived Squalene"
   content="
   **Who we contacted**: Fisherman Uncle Sun from Weihai, Shandong; Oceana reports; Policies from China's Ministry of Agriculture and Rural Affairs.

   **Why**: To understand from the source whether large-scale commercial shark fishing for squalene exists in China's coastal areas.

   **What we learned**:
   - No specialized shark fishing industry in Chinese coastal waters
   - Sharks caught are mostly 'bycatch' during deep-sea operations
   - Oceana reports reveal threat to shark populations from cosmetics industry
   - National policies prohibit new construction of vessels primarily targeting sharks

   **How we adapted**: Strengthened our fundamental stance on finding alternatives, anchoring project value in ecological protection and sustainable development."
%}

{% include dropdown.html
   title="Clarifying Industry Demand for Sustainable Ingredients"
   content="
   **Who we contacted**: Proya Cosmetics, Wuhan Berca Biomedical, Hubei Hongfuda Biotechnology, and other industry players.

   **What we learned**:
   - Market strongly prefers 'non-animal derived' ingredients
   - Extreme requirements for safety and stability
   - Insufficient supply is a real industry pain point

   **How we adapted**: Defined final product as squalene and planned full third-party safety testing procedures."
%}

{% include dropdown.html
   title="Discovering High-Value Conversion Potential of Waste Oil"
   content="
   **Who we contacted**: Zhejiang Zhengda Environmental Protection, waste oil recycling managers.

   **What we learned**:
   - Current waste oil to biodiesel conversion has meager profits (~8.5 RMB/kg)
   - Industry urgently needs high-value conversion pathways
   - 20mg high-purity squalene worth 800 RMB vs 1kg biodiesel at 8.5 RMB

   **How we adapted**: Solidified core innovation of 'upgrading waste oil to squalene', extending story from environmental protection to circular economy."
%}

{% include dropdown.html
   title="Project Positioning in 'Fashion' Track"
   content="
   **Who we contacted**: 200+ consumer questionnaire respondents.

   **What we learned**:
   - 75% of respondents had positive or curious first reaction
   - 68% concerned about safety
   - 'Fashion Pioneer Story' (41%) most popular narrative preference

   **How we adapted**: Positioned project in 'Fashion' track, creating brand narrative combining technology, environmental protection, and lifestyle."
%}

## Part II: Technical Path Construction & Key Iterations

{% include dropdown.html
   title="Ideal Chassis Organism Finalization"
   content="
   **Consultation**: Prof. Tang Qiang from USTC

   **Key Insight**: *Yarrowia lipolytica* is ideal choice - natural lipid metabolism capability and complete MVA pathway.

   **Adaptation**: Formally selected *Yarrowia lipolytica* as project chassis."
%}

{% include dropdown.html
   title="Lipase Introduction"
   content="
   **Consultation**: Prof. Yan Yunjun from HUST

   **Problem**: Wild-type strain degradation efficiency insufficient

   **Solution**: Introduced exogenous TLL lipase from *Aspergillus oryzae*"
%}

{% include dropdown.html
   title="Rate-Limiting Enzyme Optimization"
   content="
   **Consultation**: Prof. Ning Kang from HUST

   **Approach**: Used ProteinMPNN and Rosetta for protein redesign to reduce conformational frustration and improve stability."
%}

{% include dropdown.html
   title="Mining Novel HMGR Homologs"
   content="
   **Consultation**: Prof. Shi Mang from Sun Yat-sen University

   **Tool**: Integrated Foldseek for 3D structure-based homology search

   **Method**: Set 90% structural consistency threshold for reliable functional inference"
%}

{% include dropdown.html
   title="Compartmentalization Strategy"
   content="
   **Consultation**: Researcher Xie Xiaoman from HUST

   **Problem**: Squalene accumulation toxicity and feedback regulation

   **Solution**: Relocated entire MVA pathway to peroxisomes for optimized micro-reaction environment"
%}

## Part III: Product Positioning & Engineering Implementation

{% include dropdown.html
   title="Establishing Integrated Hardware Design Principles"
   content="
   **Challenge**: Expensive micro-fermentation equipment, complex operations, contamination risk

   **Consultation**: National Bio-manufacturing Industry Innovation Center, Hubei University

   **Solution**: Designed Integrated Fermentation & Processing System (iFPS)"
%}

{% include dropdown.html
   title="Hardware Material and Automation Upgrades"
   content="
   **Consultations:** HUST Engineering Innovation Center, Dr. Chen Yulong

   **Improvements:**
   - Photosensitive resin for better density and temperature resistance
   - PCB boards replacing breadboards
   - Baffled fermentation design for oxygen dissolution
   - Expanded application scenarios"
%}

## Part IV: Compliance, Safety & Future Planning

{% include dropdown.html
   title="Strengthening Raw Material Safety & Compliance"
   content="
   **Consultation**: Bloomage Bio Chief Formulator

   **Key Concerns**: Complex waste oil composition may inhibit microbial growth

   **Adaptation**: Added waste oil pretreatment module and mandatory third-party safety assessment"
%}

{% include dropdown.html
   title="Recognizing Downstream Industrialization Bottlenecks"
   content="
   **Experience**: Visit to Zhejiang Lanhaixing filling line

   **Learning**: Downstream packaging can become efficiency bottleneck due to product viscosity

   **Adaptation**: Enhanced focus on compatibility with industrial equipment"
%}

{% include dropdown.html
   title="Project Prospects"
   content="
   **International Recognition:** Prof. Sylvain FISSON from University of Evry Paris-Saclay

   **Assessment:** Project has significant practical meaning and scientific prospects

   **Future:** Invitation for further discussion and development"
%}

## Project Origin

> The project began when team members questioned the term "Natural Plant Squalane" on cosmetics during 2024 summer vacation, 
> sparking investigation into this high-value cosmetic ingredient and its sustainability challenges.

**Key Findings:**
- Animal sources involve ecological ethical controversies
- Plant sources face high environmental costs and prices
- China produces millions of tons of waste cooking oil annually
- Opportunity to create "waste oil to squalene" green cycle
