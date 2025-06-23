---
title: Parts
permalink: /parts/
feature_text: |
  ## Parts
  This page contains the parts of the project.
feature_image: "https://static.igem.wiki/teams/5175/resources/background/bg-parts.jpg"
excerpt: "This page contains the parts of the project."
---

## Introduction

Biology is different from other engineering fields due to a lack of modular nature of the structure and function, which means the expression of gene will change when transferred from one species to another. What synthetic biology is dedicated to is the modularization and standardization of functional gene, to make the expression of it predictable in different chassis organism. Our project has registered 15 basic parts and 14 composite parts, all qualified for standardized requirement of RFC[10] or RFC[1000]. We have also tested these parts. We hope that everyone can utilize our parts based on our research through registry and that the information for parts can further be completed so that more people can make use of them.

 

## Basic parts

<figcaption class="caption table_caption">Table 1. Basic parts</figcaption>

| **Part Number**                                         | **Type**   | **Part Name**       | **Length** |
| ------------------------------------------------------- | ---------- | ------------------- | ---------- |
| BBa_K5175000                                            | Regulatory | T7 promoter         | 48         |
| BBa_K5175001                                            | Coding     | lac operator        | 25         |
| BBa_K5175002                                            | Coding     | PETase-MHETase      | 2703       |
| BBa_K5175003                                            | Coding     | fucO                | 1194       |
| BBa_K5175004                                            | Coding     | aldA                | 1458       |
| BBa_K5175005                                            | Coding     | MHETase-PETase      | 2703       |
| BBa_K5175006                                            | Coding     | tphA2               | 1242       |
| BBa_K5175007                                            | Coding     | tphA3               | 465        |
| BBa_K5175008                                            | Coding     | tphA1               | 1011       |
| BBa_K5175009                                            | Coding     | tphB                | 948        |
| BBa_K5175010                                            | Coding     | tpaK                | 1377       |
| BBa_K5175011                                            | Coding     | rhlA                | 906        |
| BBa_K5175012                                            | Coding     | rhlB                | 1299       |
| BBa_K5175013                                            | Coding     | phaZ                | 870        |
| BBa_K5175014                                            | RBS        | RBS for T7 promoter | 12         |
| BBa_K731721                                             | Terminator | T7 terminator       | 48         |
| BBa_K4701231                                            | RBS        | RBS for *tphA2*     | 25         |
| BBa_K4701232                                            | RBS        | RBS for *tphA3*     | 25         |
| BBa_K4701234                                            | RBS        | RBS for *tphA1*     | 25         |
| BBa_K4701233                                            | RBS        | RBS for *tphB*      | 25         |
| BBa_K4701230                                            | RBS        | RBS for *tpaK*      | 25         |

## Improvement

This year, we tried to introduce new genes and optimize gene expression to enable *E. coli* BL21 to degrade PET and utilize EG, and to enable *P. putida* KT2440 to convert TPA to rhamnolipids.

We introduced the PETase-MHETase double enzyme expression system into *E. coli* BL21, and optimized the flexible peptide linking PETase and MHETase through molecular docking simulation, so that the double enzyme system showed high PET affinity while maintaining flexibility. We also optimized the gene expression of *E. coli* BL21, overexpressing fucO and aldA genes to enhance its ability to utilize EG.

For *P. putida* KT2440, we introduced tpaK gene to enable it to transport TPA. At the same time, phaZ gene was overexpressed, which inhibited PHA anabolic bypass and increased rhamnoolipid production. We also optimized the codon of several genes of tph gene cluster (tphA2, tphA3, tphA1, tphB), which provides a reliable basis for experimental research and development. 

## Composite parts

<figcaption class="caption table_caption">Table 2. Composite parts</figcaption>

| **Part Number** | **Type**  | **Part Name**                                                | **Length** |
| --------------- | --------- | ------------------------------------------------------------ | ---------- |
| BBa_K5175030    | Composite | T7 promoter-lac operator-pelB-FAST-PETase-G4S-MHETase-T7 terminator | 2868       |
| BBa_K5175031    | Composite | T7 promoter-lac operator-pelB-MHETase-G4S-FAST-PETase-T7 terminator | 2868       |
| BBa_K5175032    | Composite | T7 promoter-fucO-aldA-T7 terminator                          | 2808       |
| BBa_K5175033    | Composite | T7 promoter-lac operator-pelB-FAST-PETase-G4S-MHETase-T7 terminator-T7  promoter-fucO-aldA-T7 terminator | 5684       |
| BBa_K5175034    | Composite | T7 promoter-lac operator-pelB -MHETase-G4S-FAST-PETase-T7 terminator-T7  promoter-fucO-aldA-T7 terminator | 5684       |
| BBa_K5175035    | Composite | T7 promoter-tphA2-tphA3 -tphA1-T7 terminator                 | 2939       |
| BBa_K5175036    | Composite | T7 promoter-tphB-tpaK-T7 terminator                          | 2510       |
| BBa_K5175037    | Composite | T7 promoter-tphA2-tphA3-tphA1-T7 terminator-T7 promoter-tphB-tpaK-T7  terminator | 5457       |
| BBa_K5175038    | Composite | T7 promoter-tphA2-tphA3-tphB-tphA1-T7 terminator           | 3926       |
| BBa_K5175039    | Composite | T7 promoter-tpaK-T7 terminator                               | 1523       |
| BBa_K5175040    | Composite | T7 promoter-tphA2-tphA3-tphB-tphA1-T7 terminator-T7 promoter-tpaK-T7  terminator | 5457       |
| BBa_K5175041    | Composite | T7 promoter-rhlA-rhlB-T7 terminator                          | 2358       |
| BBa_K5175042    | Composite | T7 promoter-phaZ-T7 terminator                               | 1033        |
| BBa_K5175043    | Composite | T7 promoter-lac operator-rhlA-rhlB-T7 terminator-T7 promoter-phaZ-T7 terminator | 3399       |
