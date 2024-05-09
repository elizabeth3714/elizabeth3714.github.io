---
layout: post
title: Continuous Growth in the Delaware Valley Region <br>-- Forecasting Demand- and Supply-Driven Developments in 2020
tags: ["R", "SpatialAnalytics", "UrbanPlanning", "MachineLearning"]
truncated_preview: true
excerpt_separator: <!--more-->
---

**To:** Sean Thompson, Chair of the Delaware Valley Regional Planning Commission (DVRPC) <br>
**From:** Leila Bahrami and Elizabeth Wang, Policy Analysts at Penn Urbanistics Initiative (PUSI) <br>
**Re:** Continuous Growth in the Delaware Valley Region: Forecasting Demand- and Supply-Driven
Developments in 2020 <br>
--------------------------------------------------------------------------

#### 1. Executive Summary <br>

Comprehensive regional development rooted in multi-nodal growth engines has been the new
norm in the context of American urban planning. Cross-boundary collaboration brings benefits towards
resource distribution, a balanced growth and overall sustainable development. Conjoining Pennsylvania,
New Jersey, and Delaware and in proximity to New York City and Washington D.C., the Delaware
Valley Region (DVR) serves as an example of regional collaboration in growth management. With the
forecasts of next ten-to-thirty years development, the region witnesses the potential of increased
population joining the workforce, along with the expansion and enhancement of regional infrastructure
networks. <br>

This report will summarize our recent study predicting future development demand based on
the demand-driven factor of population change and the supply-driven factor of infrastructure network
enhancement. It is predicted that development would intensify in Chester and Gloucester County as the
northern parts of Montgomery, Bucks and Burlington County. The development would be further
intensified along the proposed highway, concentrating in north Montgomery and Burlington County. The
findings provide insights for planners to formulate better policies to manage urban sprawl, leverage smart
growth and balance regional development. <br>

#### 2. Background <br>

The DVR as core urban clusters of the Greater Philadelphia Region connects five adjacent states.
While population grew from 5.1 million to 5.6 million, the developed area expanded by 1.5 times,
signaling significant urban sprawl. The DVR region is forecasted to receive over 658,000 residents and
more than 372,000 job opportunities from 2015 to 2045. (DVRPC, 2017) The region will face severe
environmental damage if urban clusters continue sprawling at the preceding speed. Therefore, a
projection study of future development demand will help observe development patterns and strategically
alleviate sprawl through formulation of policy instruments. <br>

#### 3. Data and Study Methods <br>

The study adopted a quantitative approach using spatial and demographic data, along with
regression analysis to predict future development demands. <br>

<ins>3.1 Data</ins> <br>

Data of land cover in 2000 to 2010 were obtained from USGS. 2010 and 2011 population census
and Esri Data and Maps have been referred to for demographic and transportation features. Population
and employment projections came from DVRPC’s studies. <br>

<ins>3.1.1 Land Cover Change as Development Indicators</ins> <br>

The change of land cover from 2001 to 2011 indicates major developments in the decade.
**(Figures 1 to 3)** <br>

<img src="{{site.baseurl | prepend: site.url}}/portfolio/image/CPLN675/3.png" alt="Fig1-3"/> <br>

<ins>3.1.2 Major Development Engines</ins> <br>

Population is the foremost driving factor in development since an increase in population will
bring about growth of density and employment. Intensive population growth has been observed in
Montgomery County and Bucks County in the north of Philadelphia, and northwest Gloucester County
and Burlington County. **(Figures 4 to 6)** <br>

<img src="{{site.baseurl | prepend: site.url}}/portfolio/image/CPLN675/6.png" alt="Fig4-6"/> <br>

Road network is another critical development engine to consider. In view of the high level of
auto-dependency and consequently highway-oriented development patterns, our assumption is that
development demand is likely to occur near highways to access better connection to destinations. 
**(Figure 7)** <br>

<img src="{{site.baseurl | prepend: site.url}}/portfolio/image/CPLN675/7.png" alt="Fig7"/> <br>


<ins>3.2 Methods</ins> <br>

To achieve a level of accuracy, the study divided the roughly 8 thousand square-kilometers land
into over 12 million grids and used the roughly one-acre grids as units of analysis. By joining spatial data
including land cover change, population distribution and distance to highway to the grids of both 2000
and 2010, we used logit regression analysis to study the development patterns <1>. Based on the hypothesis
that future development demand shares continuity of current development, the patterns learned from the
previous decade would serve as the model of development demands in the upcoming decades. Both
demand- and supply-side development demand are projected based on future population projection and a
proposed highway respectively. <br>

#### 4. Machine Learning of Development Patterns <br>

<ins>4.1 Exploratory Analysis</ins> <br>

The spatial lag (i.e. the calculation of spatial weighted average) to 2001 development illustrates
development probabilities. Higher chance of development occurs in the periphery of the region and close
to certain sections of the highway networks. **(Figures 8 and 9)** Land cover change also indicated positive
correlation with population change from 2000 to 2001. **(Figure 10)** Among different types of land cover,
farmland has the highest conversion rate, follow by developed land and forests, at 1.16%, 1.07%, and
0.67% respectively. **(Figure 11)** <br>



**Footnotes:** <br>
<1> Spatial lag of development will be used to identify current developed locations from 2000 to 2010 and logit
regression will be used to predict future developments. <br>


