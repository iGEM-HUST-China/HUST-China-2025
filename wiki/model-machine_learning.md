---
title: Machine Learning
permalink: /model/machine-learning/
feature_text: |
  ## Model
  All models are wrong, but some are useful.——George E. P. Box
feature_image: "https://static.igem.wiki/teams/5175/resources/background/bg-model.jpg"
excerpt: "The model is a means of assisting the overall completion and implementation of a project through computational methods."
---

## Machine Learning

Microplastic pollution has become a global environmental problem, widely found in oceans, lakes and soils, posing a potential threat to ecosystems and human health, and urgently requiring enhanced monitoring and treatment. Microplastics(MPs) pose a threat to ecology and human health, and may affect organisms through the food chain, leading to the accumulation of toxins. If the spread of microplastic pollution is not properly controlled, microplastics will destroy local ecosystems and the land on which many people depend. To further understand current and future soil microplastic contaminated areas, we integrate existing microplastic abundance data and relevant environmental variables (12 source-sink factors) to model and predict the distribution of microplastic in the region through machine learning. Ultimately, we selected SVR-RBF to predict and map the simulated spatial distribution of soil MPs in the study area after comparing six machine learning models. This part can help to carry out the siting of microplastic degrading bacterial liquid fermenters for hardware and the  quantitative spraying of degrading microbial agents that may be made in the future, which can provide a more accurate guidance for the management of microplastic pollution.


### Model data selection and processing

{% include figure.html 
    image="https://static.igem.wiki/teams/5175/resources/model/model-machine-learning-01.jpg" 
    alt="Sampling data of microplastics abundance in Wuhan" 
    caption="Fig 1. Sampling data of microplastics abundance in Wuhan" 
%}

Soil MP pollution is influenced by source-sink factors, which exhibit spatial variability, dynamic changes and uncertainty[^1][^2].Referring to the existing literature, the multiple regression decision tree (MRT) method was used to isolate the source-sink correlation factors with good interpretations for the spatial abundance of MPs, and we chose five source factors and seven sink factors (TXT S1), in which the soil attribute data  [^3]  were obtained from<a href="https://www.fao.org/soils-portal/data-hub/en/" target="_blank">the World Soil Database (HWSD)</a>with a spatial resolution of 1km and a geographic coordinate system of WGS_1984_Albers. Population density data are from <a href="https://www.geodata.cn" target="_blank">the National Earth System Science Data Center </a>. Cultivated land, road network, and building data are from <a href="https://www.openstreetmap.org/" target="_blank">OpenStreetMap</a>. Point of interest (POI) data can identify different point sources of pollutant emissions and can easily and accurately correlate pollutants to build relevant quantitative models. Eight different types of POIs were selected, and the POI data were grabbed based on <a href="https://github.com/Civitasv/AMapPoi" target="_blank">AMapPOI</a>. POI data were gained from Baidu map API SDK service. The data were processed by ArcGIS 10.7 (ESRI, USA).

Utilizing the previous measured data of MPs abundance sampled in Wuhan [^4](Fig. 1), the data were divided into training and testing sets for model training at a ratio of 3:1. Since the source-sink factors differed in dimension and order of magnitude, the input data were normalized using the min-max method to avoid potential problems.

### Model selection and evaluation

We chose six commonly used machine learning models for testing and comparison, which can be categorized into single and integrated models in terms of the number and nature of models.
The single model contains three neural networks (BP-GAO, LSTM, RBF) and the SVR-RBF model. The integrated model, on the other hand, contains XGBoost, RF, which combines multiple single models into one powerful model that utilizes all the individual models to achieve superior performance. They each have their own advantages: BP-GAO optimizes the initial parameters of the neural network through a genetic algorithm, and then uses a back propagation algorithm to further adjust the network weights, which improves the learning efficiency and performance; the RBF hidden-layer neurons use a radial basis function as the activation function, usually with the Euclidean distance as the input, and the output layer is a linear combination of the outputs of the hidden layer, which has a local approximation property; LSTM introduces a gating mechanism to solve the problem of gradient vanishing in traditional RNNs, with the ability to maintain long-term dependent information; SVR-RBF predicts continuous numerical outputs by minimizing the regularization error while maintaining the model's generalization ability; XGBoost improves the model's performance by optimizing the first-order and second-order derivatives of the objective function, and has the ability to deal with large-scale datasets and automatic feature selection; RF has an excellent performance when handling high-dimensional data and is able to naturally handle classification and regression problems.

We consider the simulation and prediction accuracy of different machine learning models based on three criteria: goodness-of-fit ($\mathrm{R^2}$), root mean square error ($\text{RMSE}$), and mean absolute error ($\text{MAE}$).

<center>
  $$
  \left\{
    \begin{aligned}
      \mathrm{R^2} & =1-\frac{\sum_{i=1}^{N}{\left( p_i-a_i \right)}^2}{\sum_{i=1}^{N}{\left( a_i-\bar{a} \right)}^2} \\
      \mathrm{RMSE} & =\sqrt{\frac{1}{N}\sum_{i=1}^{N}\left( p_i-a_i \right) ^2} \\
      \mathrm{MAE} & =\frac{1}{N}\sum_{i=1}^{N}\left|p_i-a_i\right|
    \end{aligned}
  \right.
  $$
</center>

### Results

{% include figure.html 
    image="https://static.igem.wiki/teams/5175/resources/model/model-machine-learning-02-changed.jpg" 
    alt="Different machine learning results for microplastics prediction" 
    caption="Fig 2. Different machine learning results"
%}

The SVR-RBF model was finally selected from several machine learning models such as BP-GAO, LSTM, RF, and XGBoost.
Support vector regression allows global optimization, while BP neural networks usually only allow local optimization[^5].BP neural networks have low quantization accuracy, too much data fitting, and over-reliance on hidden layer settings. Other neural network models (RBF and LSTM) also suffer from high accuracy in the training set but high fitting error in the testing set. Support vector machines have the advantage of applying the kernel function expansion theorem, which does not require an explicit representation of the nonlinear mapping, and therefore can use known efficient algorithms to find the global minimum of the objective function. Compared with other machine learning models (Fig. 2,Table S1), the SVR-RBF model (R<sup>2</sup>=0.9845481376179647, RMSE=0.01536591336885121, MAE=0.011207557068397008) provides a better fitting and prediction for the microplastic dataset.
Inputting 12 source-sink factor data from Wuhan City to the trained model to get the spatial distribution of soil MPs within the predicted study area, we can identify the potential risk areas of microplastics and plot a spatial map of soil MP pollution in that area. From the map, it can be seen that the urban centers of Wuchang, Hanyang, and Jianghan districts, as well as the areas along the banks of the Yangtze River have higher abundance of microplastics, which may require more control and management.

{% include figure.html 
    image="https://static.igem.wiki/teams/5175/resources/model/model-machine-learning-03.jpg" 
    alt="Predicted microplastics distribution in Wuhan"
    caption="Fig 3. Predicted microplastics distribution in Wuhan"
%}

### Discussion

We completed the training and comparison of the above six machine learning models, and finally selected the SVR-RBF model to get the distribution of microplastic abundance within the study area, and the three standard parameters of $\mathrm{R^2}$, RMSE, and MAE validated the accuracy and reliability of our model. We hope that future teams can improve its accuracy and validation by further expanding the sample size of the sampling data.

The inclusion of environmental factors affecting the source-sink of soil MPs completed the construction of a machine learning model suitable for predicting the spatial distribution of soil MPs. However, the possibility of other unknown sources of soil contamination in the region cannot be ruled out. If in regions with large differences in spatial layout, it is necessary to reconsider the environmental factors to maintain a high accuracy of the model.

Despite these limitations, we still believe that this study will provide data and material support for subsequent work.Moreover, there is more room for expanding the application of this method in the future by changing the object of study from microplastic abundance to specific microplastic species, size, or related data (e.g., studying the spatial distribution of PET microplastics in different regions).


### Attachment

<a href="attachment">Click here</a> to see all the attachments in this page.


{% include button.html link="../" text="Go back to Model Introduction" %}

---

## References
[^1]:Wang, C., Zhao, J., & Xing, B. (2021). Environmental source, fate, and toxicity of microplastics. Journal of hazardous materials, 407, 124357.
[^2]:Yang, H., Huang, K., Zhang, K., Weng, Q., Zhang, H., & Wang, F. (2021). Predicting heavy metal adsorption on soil with machine learning and mapping global distribution of soil adsorption capacities. Environmental Science & Technology, 55(20), 14316-14328.
[^3]: FAO & IIASA. 2023. Harmonized World Soil Database version 2.0. Rome and Laxenburg. doi: 10.4060/cc3823en
[^4]: Zhou, Y., Wang, T., Zou, M., et.al. (2023). Trends in the occurrence and accumulation of microplastics in urban soil of Nanjing and their policy implications. Science of The Total Environment, 903, 166144.
[^5]:Jia, X., Hu, B., Marchant, B. P., Zhou, L., Shi, Z., & Zhu, Y. (2019). A methodological framework for identifying potential sources of soil heavy metal pollution based on machine learning: A case study in the Yangtze Delta, China. Environmental Pollution, 250, 601-609.

