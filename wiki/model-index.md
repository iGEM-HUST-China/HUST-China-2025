---
title: Model
permalink: /model/
feature_text: |
  ## Model
  All models are wrong, but some are useful. -- George E. P. Box
feature_image: "https://static.igem.wiki/teams/5175/resources/background/bg-model.jpg"
excerpt: "The model is a means of assisting the overall completion and implementation of a project through computational methods."
---

The model is a means of assisting the overall completion and implementation of a project through computational methods.
We attempt to delve into various components of the project from design to implementation for model construction and computation.

{% include figure.html image="https://static.igem.wiki/teams/5175/resources/model/model-workflow.jpg" alt="Introduction of Modeling" caption="Fig 1.Introduction of Modeling" %}

## Optimization of Dual-Enzyme System

In project design, we aim to optimize the dual enzyme system of PETase-MHETase. We consider the impact of the types and lengths of linkers, with the order of PETase and MHETase in the peptide chain. With molecular docking, we use docking simulations and scoring function to obtain the optimal dual enzyme system.

{% include button.html link="./molecular-docking" text="More about Molecular Docking"  %}

## Genome-scale Metabolic Modeling

To support the results from Wet Lab, we have developed a genome-scale metabolic model for the engineered *Pseudomonas putida* KT2440. This model predicts its growth behavior, TPA absorption rate, and rhamnolipid product yield. We estimate that the engineered strain can efficiently absorb and degrade TPA while producing rhamnolipids in the process.

{% include button.html link="./genome-scale" text="More about Genome-scale Metabolic Modeling"  %}


## Spatial Prediction Model for Microplastics

Understanding the spatial distribution characteristics of microplastics is an important prerequisite for controlling soil pollution, which can assist the location selection of the fermentation tank for hardware. We plan to use machine learning to predict the spatial distribution with existing microplastic abundance data and environmental source-sink data.

{% include button.html link="./machine-learning" text="More about Machine Learning"  %}
