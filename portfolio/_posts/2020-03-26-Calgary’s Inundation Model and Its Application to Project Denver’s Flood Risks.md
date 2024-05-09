---
layout: post
title: Calgary’s Inundation Model and Its Application to Project Denver’s Flood Risks
tags: ["R", "SpatialAnalytics", "UrbanPlanning", "MachineLearning"]
truncated_preview: true
excerpt_separator: <!--more-->
---
Click for Video Presentation: <br>
[<img src="{{site.baseurl | prepend: site.url}}/portfolio/image/CPLN675/calgary_screen.png" alt="CalgaryScreen"/>](https://www.youtube.com/watch?v=sw-GyF2KQ1M&t)

### Overview <br>

This exercise applied geo-spatial machine learning to learn the inundation model in Calgary and predicted flooding hazard in another geography that is the city of Denver. <br><!--more-->

### Motivation <br>
To adopt a scientific approach for studying and predicting natural disasters; to
assist policy makers in the environment and infrastructure section to formulate adaptive
strategies; and to protect assets and finance of local residents. <br>

### Methodology & Algorithm <br>

The data analysis exercise will take the following steps:<br>

* Determining a city for comparison: Denver<br>
* Collecting data for Calgary and Denver<br>
* Feature engineering<br>
* Create fishnet<br>
* Forward and Backward Selection for non-multicollinear criteria<br>
* Logistic regression for significant factors<br>
* Training vs Testing<br>
* Model validation & cross validation<br>
* Prediction on Denver<br>

### Variables <br>

<img src="{{site.baseurl | prepend: site.url}}/portfolio/image/CPLN675/p1.png" alt="p1"/> <br>
<img src="{{site.baseurl | prepend: site.url}}/portfolio/image/CPLN675/p2.png" alt="p2"/> <br>
<img src="{{site.baseurl | prepend: site.url}}/portfolio/image/CPLN675/p3.png" alt="p3"/> <br>
<img src="{{site.baseurl | prepend: site.url}}/portfolio/image/CPLN675/p4.png" alt="p4"/> <br>

### Confusion Matrix and ROC Curve <br>

<img src="{{site.baseurl | prepend: site.url}}/portfolio/image/CPLN675/p_confusion_matrix.png" alt="confusion_matrix"/> <br>
<img src="{{site.baseurl | prepend: site.url}}/portfolio/image/CPLN675/p_ROC.png" alt="ROC"/> <br>

### Prediction with Calgary Test Geography and Denvor <br>

<img src="{{site.baseurl | prepend: site.url}}/portfolio/image/CPLN675/p_prediction_actual.png" alt="prediction_actual"/> <br>
<img src="{{site.baseurl | prepend: site.url}}/portfolio/image/CPLN675/p_calgary_denver.png" alt="calgary_denver"/> <br>

![CPLN675 repository](https://github.com/elizabeth3714/CPLN675) <br>

<br>
<br>

<div class="message">
  This is the term project of CPLN675 Environmental Modelling at the University of Pennsylvania. The project
  was co-authorized by Leila Bahrami and Elizabeth Wang. <br>
</div>
