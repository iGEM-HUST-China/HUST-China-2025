---
title: Machine Learning
permalink: /model/machine-learning/attachment/
feature_text: |
  ## Model
  All models are wrong, but some are useful.——George E. P. Box
feature_image: "https://static.igem.wiki/teams/5175/resources/background/bg-model.jpg"
excerpt: "The model is a means of assisting the overall completion and implementation of a project through computational methods."
---

## Attachments

Supplementary Information includes Supplementary text S1-2, and Table S1.

#### Text S1

**Source and sink factors of soil microplastics**

1. Source factors: clay, silt, sand, total organic carbon (TOC), electrical conductance (EC), pH, bulk density (BD);
2. Sink factors: population density (PD), point of interest (POI), farmland area (FA), road area (RA), construction land area (CA).

#### Text S2

**POI databases**

POI data is the core data of location-based services. In GIS, POI data records the spatial and attribute information of geographical entities. In addition, POI data can identify different pollutant emission point sources, which can easily and accurately correlate pollutants and establish relevant and quantitative models. Microplastics are new pollutants produced by human activities, among which plastic waste and domestic sewage are important sources of microplastics. Therefore, we used Ospider 3.0 to capture 9 types of POI data related to plastics, including.Recycle-POI: Recycling station or waste or garbage.

1.	Shopping-POI: Supermarket, Mall.
2.	Electronic-POI: Electronic factory.
3. 	Auto-tyre-POI: Automobile service, Tyre production.
4.	Plastic-POI: Plastic production, Package production, manufacturing, sales.
5.	Express-POI: Express delivery or logistics express.
6.	Lanudry-POI: Dry cleaning, laundry.
7.	Clothing-POI: Clothing, shopping services.
8.	Accommodation-POI: Hotel, Residence.

#### Table S1

Comparison of simulation goodness and prediction accuracy of different machine learning models in predicting soil microplastics abundance

<figcaption class="caption table_caption">Comparison of simulation goodness and prediction accuracy of different machine learning models in predicting soil microplastics abundance</figcaption>

|                          | **BP-GAO** | **RF**   | **LSTM** | **XGBoost** | **RBF**  | **SVR-RBF** |
| ------------------------ | ---------- | -------- | -------- | ----------- | -------- | ----------- |
| **Train_$\mathrm{R^2}$** | 0.53891    | 0.920112 | 0.468024 | 0.999997    | 0.999728 | 0.935819    |
| **Train_RMSE**           | 0.140926   | 0.059283 | 0.138087 | 0.000374    | 0.003821 | 0.062681    |
| **Train_MAE**            | 0.120594   | 0.054773 | 0.09757  | 0.00026     | 0.002627 | 0.045125    |
| **Test_$\mathrm{R^2}$**  | 0.482759   | 0.96512  | 0.963398 | 0.828356    | 0.410678 | 0.984548    |
| **Test_RMSE**            | 0.164101   | 0.038982 | 0.182309 | 0.085429    | 0.147808 | 0.015366    |
| **Test_MAE**             | 0.137078   | 0.030853 | 0.134099 | 0.072607    | 0.129603 | 0.011207    |

{% include button.html link="../" text="Go back to Model-Machine Learning" %}
