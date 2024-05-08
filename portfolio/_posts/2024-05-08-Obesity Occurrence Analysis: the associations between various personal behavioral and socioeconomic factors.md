---
layout: post
title: Obesity Occurrence Analysis <br>-- the associations between various personal behavioral and socioeconomic factors
truncated_preview: true
excerpt_separator: <!--more-->
---

<div class="message">
  This is the term project of SI618 Data Manipulation and Analysis at the University of Michigan. The project is 
  co-authorized by Jessie Hu, Huanyu Ren and Elizabeth Wang, with equal work division. <br>
</div>
<br>

[![Click for Video Presentation](../image/SI618obesity/machine_learning.png?raw=true)](https://www.youtube.com/watch?v=BPoTLzTc3eE&t=235s)

### Overview <br>

This study examines the correlation between obesity rates and various other factors, utilizing two robust datasets: 
the CDC's PLACES: Census Tract Data (GIS Friendly Format), 2023 release, and the American Community Survey Data from 
the US Census. The PLACES data offers a deep dive into the prevalence of obesity and other chronic conditions, 
as well as lifestyle habits such as physical activity levels, sleep duration, diabetes management, and alcohol 
consumption. The American Community Survey complements this with demographic and socioeconomic insights, encompassing 
factors like median household income and poverty rates within census tracts. <br>

By merging these datasets, the analysis aims to reveal the associations between obesity prevalence and a spectrum of 
lifestyle choices and socioeconomic conditions at the neighborhood level. The goal is to disentangle the intricate web 
of factors—from individual behaviors to community-wide economic indicators—influencing obesity and chronic disease rates. 
Employing advanced statistical analysis and data visualization tools, the research intends to pinpoint critical determinants 
of obesity, shedding light on the multifaceted nature of health disparities within Michigan's diverse communities. <br>

### Motivation <br>

This research is motivated by the urgent need to address the growing burden of obesity, which poses a significant threat 
to public health systems. Obesity is also a major contributor to increased healthcare costs and reduced quality of life. 
Addressing obesity effectively requires a comprehensive approach that accounts for individual behavior and the broader 
societal and environmental determinants of health. <br>

In Michigan, like in many other regions, the prevalence of chronic diseases varies significantly across different communities, 
suggesting that factors at the neighborhood level may play a critical role in influencing health outcomes. These factors 
include, but are not limited to, socioeconomic status, access to healthcare services, environmental conditions, and the 
availability of resources supporting healthy lifestyles. Moreover, personal behaviors and lifestyle choices, such as smoking, 
physical activity, and dietary habits, interact with these neighborhood factors, creating a complex web of influences that 
affect health. <br>

Furthermore, understanding the spatial distribution of chronic diseases and their determinants can guide the allocation of 
resources and health services to the communities that need them the most. This is particularly important in a state like 
Michigan, which displays wide variations in economic conditions, racial and ethnic composition, and health outcomes across 
its regions. Through this analysis, the research seeks to contribute to the development of more equitable health policies 
and programs that can adapt to the specific needs of diverse populations, ultimately leading to a healthier, more resilient 
society. <br>

Specifically, **the "real-world" questions** central to this research are:  <br>
- How do personal health behaviors correlate with the obesity rates across different socioeconomic contexts in Michigan? <br>
By answering this question, we aim to identify specific behaviors that significantly contribute to chronic diseases within
varying socioeconomic backgrounds. This knowledge could lead to targeted behavioral interventions. <br>

- Do demographic factors such as race and income level within census tracts in Michigan have a predictive relationship with prevalence of obesity? <br>
This question seeks to explore the social determinants of health, with the expectation to learn how demographic factors may exacerbate or alleviate the risk of chronic diseases. Insights from this analysis could be pivotal in addressing health disparities and crafting equitable health promotion strategies. <br>

- What are the most relevant socioeconomic factors and personal health behaviors associated with each chronic disease, and how do these factors compare across different chronic conditions?  <br>
By dissecting the relationships between multiple chronic diseases and a broad range of influencers, we hope to dentify the strongest socioeconomic and behavioral predictors for each chronic disease to understand targeted prevention opportunities. <br>

In summary, we are willing to utilize the findings to inform public health officials and healthcare providers about which interventions could be most effective for each condition and demographic.The anticipated outcomes of this research include a clearer picture of the socioeconomic and behavioral dimensions of chronic diseases, an understanding of the commonalities and differences in their determinants, and actionable data to guide the crafting of nuanced health promotion campaigns. This will be instrumental in reducing health disparities and enhancing the wellbeing of individuals across Michigan's varied communities. <br>

### Data Sources <br>

Our research utilizes two pivotal data sets: <br>

- **Primary Dataset**:  <br>
  - *Name*: PLACES: Census Tract Data (GIS Friendly Format), 2023 release <br>
  - *Details*: Contains data on the incidence of chronic diseases and personal health habits (smoking status, sleep duration, frequency of dental visits, alcohol consumption). <br>
  - *Access*: [CDC Chronic Disease Data](https://data.cdc.gov/500-Cities-Places/PLACES-Census-Tract-Data-GIS-Friendly-Format-2023-/yjkw-uj5s/about_data "cdc_chronic_disease") <br>

- **Secondary Dataset**: <br> 
  - *Name*: Census-based data on area socioeconomic factors <br>
  - *Details*: Includes area name, ID and their socioeconomic indicators such as poverty rates, education levels, race, and gender. <br>
  - *Access*: [US Census Data](https://www.census.gov/programs-surveys/acs/data.html "US CENSUS") <br>
  - *Scraping Method*: [PyGIS Instructions](https://pygis.io/docs/d_access_census.html "Instructions") <br>

- **Relationship Between Datasets**: <br>
    - The datasets we've selected provide a comprehensive view of both chronic disease incidence and the socioeconomic fabric of Michigan's regions. Our primary dataset offers detailed information on health behaviors and chronic disease prevalence. The secondary dataset complements this with socioeconomic data from the census, including area identifiers and demographic information. <br>
    - In the forthcoming analysis, we will integrate these datasets using unique regional identifiers. This will allow us to delve into a nuanced analysis of how chronic disease rates correlate with personal health practices and socioeconomic conditions, enhancing our understanding of health disparities within Michigan's diverse communities. <br>


### Data Description <br>

- Primary Dataset <br>
    - data selection <br>
        - We selected some variables related to personal behavior (such as alcohol abuse, smoking, lack of sleep) and some chronic disease variables (arthritis, hypertension, etc.) in the original data set. However, we only selected some chronic diseases as analysis samples, because the data set is a little too large. <br>
    - list of some key variables <br>
        - some identifiers like `StateAbbr`,`StateDesc`,`CountyName`,`CountyFIPS`,`Geoid` and `TractFIPS` help us identify the areas;  <br>
        - There are also categories that represent the prevalence of chronic diseases, such as `ARTHRITIS_CrudePrev`,`ARTHRITIS_Crude95CI`,`DEPRESSION_CrudePrev`,`DEPRESSION_Crude95CI`,`DIABETES_CrudePrev`,`DIABETES_Crude95CI` and other such indicators. <br>
        - There are categories that represent individual behavioural indicators, such as `BINGE_CrudePrev` for the prevalence of alcohol abuse among adults, `CSMOKING_CrudePrev` for the prevalence of smoking among adults, and `SLEEP_CrudePrev` for the proportion of people who sleep less than seven hours. <br>
    - The DataFrame comprises 2,745 entries, indicating the presence of 1,000 rows indexed from 32376 to 35120. It includes 15 columns, each representing different attributes potentially associated with various health metrics related to chronic diseases across different counties and states. The dataset is complete with no missing values. The columns `StateAbbr` (State Abbreviation) and `CountyName` are of the object type. The column `TractFIPS` is the int64 data type. The remaining columns are of the float64 data type. <br>

- Secondary Dataset <br>
    - data selection <br>
        - We used the API to download the data related to regional socioeconomic indicators in the 2023 U.S. Census from the U.S. Census Bureau's website as variables. Website:[US census](https://www.census.gov/programs-surveys/acs/data.html "US CENSUS") <br>
    - list of some key variables <br>
        - we use `Geoid` (renamed as `TractFIPS` for merge purposes) as the area identifier. <br>
        - We selected some socioeconomic indicators as variables. For example, we select `male` and `female` as gender indicators; we use `black`, `white`, `Asian`, `American Indian`, `Native Hawaiian`, and `other races` as racial indicators. Similarly, we also used income, poverty rate, and education level as variables. <br>
    - The DataFrame displayed consists of 2,813 entries, suggesting that it contains data across a variety of census tracts, likely numbered from 0 to 2812. It encompasses 20 columns, each representing different attributes which linked to various health metrics and socioeconomic factors related to chronic diseases. The dataset appears almost complete, with only the `Poverty_Rate` column showing a lesser number of non-null entries, indicating some missing values. there are 2,813 (total entries) - 2,740 (non-null entries for 'Poverty_Rate') = 73 missing values in the 'Poverty_Rate' column. <br>

The columns are a mix of data types: the `NAME`, `state`, `county`, and `tract` columns are of the object type, presumably containing textual data. The `TractFIPS` column is of the int64 data type, likely a numerical identifier for each tract. All other columns, which include demographic information such as `Total_Population`, `Male`, `Female`, as well as race categories and socioeconomic indicators like `Median_HH_Income` and `Poverty_Rate`, are of the float64 data type. This structure suggests a detailed and rich dataset suitable for in-depth analysis of chronic disease factors at the tract level within Michigan. <br>

### Descriptive Statistics <br>

#### Histogram of Health Outcome <br>

![Histograms of Health-related Columns](../image/SI618obesity/1.png?raw=true)

#### Visualizaiton of Population by Race in Percentage <br>

![Race Percentage](../image/SI618obesity/2.png?raw=true)

This diagram shows the racial composition across 50 randomly selected census tracts, with each racial group represented by a unique color. The population percentages are scaled to a total of 100% for comparative purposes. It should be noted that the Hispanic population overlaps with other racial categories; therefore, when all groups are combined, the total percentage exceeds 100%. This overlap allows for a detailed examination of the distribution and concentration of the Hispanic population alongside other groups. For clarity, the representation of the Hispanic population extends beyond the 100% mark to highlight its integration with other racial demographics. <br>

Observations include: <br>

- **White Population:** Predominantly the majority in most of the census tracts. <br>
- **African American Population:** Significant concentrations of African American residents dominate in certain tracts. <br>
- **Hispanic, Asian and Other Racial Group:** There is a noticeable agglomeration of Hispanic individuals in several tracts, with the Asian and other racial groups also showing presence but to a lesser extent. <br>

#### Visualization of Median Household Income by County <br>

![Median Household Income by County](../image/SI618obesity/3.png?raw=true)

In order to observe the distribution of median household income, the data has been further aggregated by county. Ten county were randomly selected in this process. The violin charts depict the distribution of median household income in the 10 counties respectively. Each diagram demonstrates the median household income distribution from the census tracts of each county. For example, Lenawee county is relatively wealthier, the median value of median household income is above 50,000. Berrien county has smaller gap among wealthier and less wealthy households. Genesee county's median value of median household income is around 30,000, lower than other counties. <br>

### Multivariate Analysis <br>

#### Correlation Matrix and Visualization <br>

Due to the large number of variables, we break this visualization into two steps. In the firs step, we would like to focus on the correlation of all health outcome (from the primary dataset - CDC PLACE). Then the merged dataset is uesd to visualize correlation among all health related along with socio-economic fators. <br>

![Correlation Matrix 1](../image/SI618obesity/4.png?raw=true)

The heatmap uses a red-blue color scheme (`coolwarm`). Blue represents a a positive correlation, red represents a negative correlation, and the intensity of the color indicates the strength of the correlation. <br>

- **Red (Positive Correlation):** Darker shades of red indicate a stronger positive correlation, where an increase in one condition tends to be associated with an increase in another. Lighter shades of red indicate a weaker positive correlation. <br>
- **Blue (Negative Correlation):** Darker shades of blue indicate a stronger negative correlation, where an increase in one condition tends to be associated with a decrease in another. Lighter shades of blue indicate a weaker negative correlation. <br>


**Significant Correlations Between Obesity and Other Conditions** <br>

1. **Obesity and Physical Activity:** There appears to be a strong positive correlation between obesity and physical activity (as indicated by a dark red color). This suggests that higher levels of lacking physical activity are associated with lower levels of obesity. <br>
2. **Obesity and Sleep Less Than 7 Hours:** There was a strong positive correlation indicated (around 0.84), suggesting that individuals with obesity may also experience less sleep (fewer than 7 hours), or vice versa. <br>
3. **Obesity and Diabetes:** A strong positive correlation was also noted between obesity and diabetes, which is consistent with medical understanding that obesity can be a risk factor for type 2 diabetes. <br>
4. **Obesity and Stroke:** There seemed to be a positive correlation between obesity and stroke, which aligns with the known health risks associated with obesity. <br>
5. **Obesity and Fair or Poor Health:** A positive correlation between obesity and fair or poor health suggests that  higher levels of obesity within the dataset could be associated with a higher probability of having fair or poor health status. <br>
6. **Obesity and Binge Drinking:** The blue coloring suggests a negative correlation between obesity and binge drinking. This means that as binge drinking increases, obesity levels tend to decrease, and vice versa. <br>

![Correlation Matrix 2](../image/SI618obesity/5.png?raw=true)
![Correlation Matrix bar](../image/SI618obesity/6.png?raw=true)

Beside correlation among health conditions, we would like to further understand the correlation among health and socio-economic factors. This heatmap demonstrates correlation among such variables using green for positive correlation and pink for negative one. <br>

- **Green (Positive Correlation):** Darker shades of red indicate a stronger positive correlation. Lighter shades of red indicate a weaker positive correlation. Zero is dislayed in white. <br>
- **Pink (Negative Correlation):** Darker shades of blue indicate a stronger negative correlation. Lighter shades of blue indicate a weaker negative correlation. <br>


**Significant Correlations Among Health and Socio-economic Features** <br>

1. **Education and Disease Occurance:** Education background has been categorized into those holding a bachelor's degree and above, and those who have not attended university. It is stunning how education background shows negative correlation with disease occurance (including diabetes, obesity and stroke, bad mental and physicla health) and risky health behaviors (including sleeping less, smoking, lack of exercises). <br>
2. **Poverty Rate and Disease Occurance:** Poverty rate also shows a strong positive correlation with most disease occurance and bad health behaviors. This includes diabetes, obesity, poor mental and physical health, smoking, sleeping less, and lack of exercise - all of these features show over 0.5 correlation. <br>
3. **Race and Disease Occurance:** Both white and black population demonstrate strong correlation with disease occurance and risky health behaviors, wheras in oppisite patterns. White population shows strong negative correlation with smoking, diabetes, obesity, stroke, sleeping less, and poor physical health. As comparison, black population unveils positive correlation with these factors. However, white population has strong positive correlation with binge drinking, whereas black population shows strong negative correlation. <br>
4. **Household Financial Status and Disease Occurance:** Similarly, the median household income also demonstrates a strong negative correlation with the occurance of dieases including stroke, obesity, dieabtes, etc., as well as poor health behaviors such as lack of exercise and sleep. However, household income shows strong correlation with binge drinking. <br>

#### Pairplot by Dominant Race Group <br>

![Correlation Matrix bar](../image/SI618obesity/7.png?raw=true)

To add a dimention to the pairplot, the original numeric data for racial groups have been converted to categorical data. The method is to pick the dominant group in population and create a new column with the race as the value. This is a relatively simple and brutal approach for the purpose of data visualization. <br>

Pairplots of selected variables are depicted in the chart above. We would like to focus on the correlation of other variables with obesity. <br>
**Health outcome:**  lack of sleep, lack of physical activity, and stroke show positive correlation with the occurence of obesity. Depression and binge drinking shows negative correlation with the occurence of obeisty. <br>
**Racial groups:** the majority census tracts are dominated by either white or black population. The census tracts with the same dominant groups shows agglomerations in the distribution. For example, with the same level of blood pressure, white population has lower obesity occurence as compared to black population. On the contrary, white population shows higher chance in binge drinking, but obesity occurence is still relatively higher with the black population. <br>

### Inferential Analysis <br>

## MODEL 1: Multiple Linear Regression Model (Obesity as the dependent variable. Multiple indicators of personal lifestyle habits as the dependent variable.) <br>

- $Y$:`Obesity`; $X_1$:`PhysicalActivity`; $X_2$:`SleepLess7Hrs`; $X_3$:`Diabetes`; $X_4$:`Stroke`; $X_5$:`FairPoorHealth`; $X_6$:`BingeDrinking` <br>
- $Y=\beta_0+\beta_1X_1 +\beta_2X_2 + \beta_3 X_3 + \beta_4 X_4+ \beta_5 X_5 + \beta_6 X_6 + \epsilon$ <br>
- $H_0:\beta_1=\beta_2=\beta_3=\beta_4=\beta_5=\beta_6=0$ <br>
- $H_A$: at least one $\beta_i$ is non-zreo <br>
- Confidence Interval: We chose a 99% confidence interval. <br>
- We chose the variables in this way because we attempted to illustrate the linear relationship between obesity and indicators of personal lifestyle habits through multiple linear regression modeling. <br>

![Correlation Matrix bar](../image/SI618obesity/model1.png)

So the funcution can be expressed as: $\text{Obesity} = -4.3476 + 1.0794 \times \text{PhysicalActivity} + 0.2330 \times \text{SleepLess7Hrs} + 
2.7568 \times \text{Diabetes} - 4.7811 \times \text{Stroke} - 1.0357 \times \text{FairPoorHealth} + 0.6658 \times \text{BingeDrinking} + \varepsilon$ <br>

