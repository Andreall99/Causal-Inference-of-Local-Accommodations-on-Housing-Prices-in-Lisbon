# Causal-Inference-of-Local-Accommodations-on-Housing-Prices-in-Lisbon

## 1. Introduction

Residential real estate prices in Lisbon have been growing exponentially, raising concerns about their affordability for local residents. This increase is driven by various factors, including economic recovery, foreign direct investment, and the city's tourism appeal. Additionally, many property owners have been converting residential properties into short-term local accommodations due to their higher profitability. However, few studies quantify the causal effect of this growth on housing prices. Descriptive analysis shows that the parishes with the highest growth in local accommodations do not exactly correspond to those where the greatest increases in housing prices have been observed, suggesting the influence of other variables in this relationship. This study uses observational time series data on the variables under study, including potential confounding variables, at the level of the Lisbon municipality and its parishes, between 2007 and 2023. Using econometric methods such as first-difference linear regression and fixed effects models, while controlling for potential confounding variables, the causal effects of the increase in local accommodation supply on the average housing prices per square meter at the municipal and parish levels were estimated.

This work will consist of two files. The "Time Series" file will correspond to the study conducted on the municipality of Lisbon, and the "Data Panel" file will focus on its parishes

## 2. Data and Variables Definition

Statistical inference methods, on which most current artificial intelligence is based, are used to make predictions assuming that the future will be similar to the past. They take advantage of the associations between observed data in independent variables (predictors) and the dependent variable (response) that is to be predicted. However, identifying the independent variables in a predictive model built on statistical methods that maximize the correlation between the independent and dependent variables does not guarantee that there is a causal relationship between them.

The existence of a cause-and-effect relationship between variables X and Y implies that a change in the cause X leads to a change in the distribution of the variable Y. To draw conclusions about the existence of a causal relationship between two variables X and Y, it is necessary to be able to intervene in the cause X. The gold standard method for identifying causality between two variables is to conduct randomized controlled experiments. However, it is not always technically, economically, or ethically feasible to perform these experiments in real-world contexts. In such cases, an alternative method of causal inference involves representing the causal model of the observed data qualitatively through a directed acyclic graph or quantitatively through a structural causal model, and subsequently controlling for confounding variables that influence both the causal variable X and the dependent variable Y, in order to eliminate the effects and spurious associations that these confounding variables might create in the causal relationship between X and Y being studied (Pearl et al., 2016; Hernán & Robins, 2020). This initial causal model cannot be defined based on statistical methods alone; it must be proposed through empirical knowledge of the reality, obtained from experts and/or literature. In this context, five potential confounding variables have been identified between the supply of short-term rentals (AL) and housing prices in the city of Lisbon, for the following reasons:

##### a) Number of housing units in the city of Lisbon: 
The number of housing units affects, on one hand, the availability of properties to be converted into short-term rentals and, on the other hand, the housing prices due to the greater or lesser supply of housing in the market.

##### b) Number of overnight stays in tourist accommodations in the city of Lisbon: 
The number of tourist overnight stays influences, on one hand, the supply of short-term rentals induced by higher demand for this type of accommodation, and on the other hand, the housing prices due to the gentrification of the city.

##### c) Gross Domestic Product (GDP) of the Lisbon Metropolitan Area (AML): 
GDP represents economic activity in the AML and consequently influences, on one hand, the capacity and willingness of investors in the region to increase or decrease the supply of short-term rentals, and on the other hand, the housing prices due to changes in demand and the purchasing power of its inhabitants.

##### d) Foreign Direct Investment (FDI) in the real estate market in Greater Lisbon: 
The variation in FDI in the real estate market influences, on one hand, the ability of foreign investors to increase or decrease the supply of short-term rentals in Lisbon, and on the other hand, the housing prices due to the construction, purchase, and sale of properties by such investors.

##### e) 6-month Euribor interest rate: 
The reference interest rate for loans influences, on one hand, the ease of financing for converting housing into short-term rentals and, on the other hand, the housing prices due to the greater or lesser purchasing capacity of demand.



## 3. Model Definition


Three causal models were studied, measuring the absolute and relative effect (in €/m² and %) of the supply of local accommodations (ALs) on housing prices in Lisbon. At the municipal level, the impact of a new AL on housing prices across the entire city is analyzed, while at the parish level, the effect is measured within the specific parish where the AL is located. Above are the three Models.

![Captura de ecrã 2024-09-10 191038](https://github.com/user-attachments/assets/369d8bd6-76a9-47d5-8d30-af3bd980818e)

## 4. Estimators of causal effects 
### 4.1 Municipal level
The causal effect at the municipal level in Model 1 was estimated based on the following multiple linear regression equations using first differences (∆) (and standard errors with the Newey-West estimator).
The image below illustrates the multiple linear regressions used at the municipal level for the first model. For models 2 and 3, we only replace the respective dependent and independent variables.


![image](https://github.com/user-attachments/assets/6f62d207-86ad-4820-88d0-41caf9fa524d)
##### α: Average variation in the price per square meter when all independent variables are zero;
##### β1: Average causal effect of each additional unit of short-term rental (AL) in year 𝑡 on the variation in price per square meter in the same year 𝑡;
##### β2: Average causal effect of each additional unit of short-term rental (AL) in year 𝑡−1 on the variation in price per square meter in year 𝑡;
##### δ1 to δ5: Average effects of the confounding variables on the variation in price per square meter in year 𝑡;

### 4.2 Parish level
The causal effect at the parish level was estimated based on the following multiple linear regression equations with two fixed effects αi and 𝜃𝑡 (with standard errors clustered at the parish 𝑖 and year 𝑡):

![image](https://github.com/user-attachments/assets/8e179906-5959-4edb-94da-83d0f0be54f3)
##### β1: Average causal effect of each additional unit of short-term rental (AL) in year 𝑡 on the variation in price per square meter in the same year 𝑡;
##### β2: Average causal effect of each additional unit of short-term rental (AL) in year 𝑡 −1 on the variation in price per square meter in year 𝑡;
##### ρ1 to ρ3: Average inverse causal effect of each additional unit of short-term rental (AL) on the anticipated variation in price per square meter;
##### δ1 to δ2: Average effects of the confounding variables on the variation in price per square meter in year 𝑡;

## 5. Results

### 5.1 Municipal Level

![image](https://github.com/user-attachments/assets/1d83a135-a493-4db7-91ac-56ef31c2b629)

##### An increase of 1 new short-term rental (AL) causes an average increase of €0.05 per square meter in housing prices at the municipal level.

##### A 1% increase in the AL/H ratio causes an average increase of €160 per square meter in housing prices at the municipal level.

##### A 1% increase in the AL/H ratio causes an average increase of 7.5% in the price per square meter of housing.

There is no evidence that these effects are lagged to the following year.

The causal effects are statistically significant at the 90% level.

### 5.2 Parish Level

![image](https://github.com/user-attachments/assets/502ec820-bf83-458e-b277-c40d0b2681e9)

##### An increase of 1 new short-term rental (AL) causes an average increase of €0.35 per square meter in housing prices in the parish of that AL.

##### A 1% increase in the AL/H ratio causes an average increase of €45 per square meter in housing prices in the parish of that AL.

##### A 1% increase in the AL/H ratio causes an average increase of 0.5% in the price per square meter of housing in the parish of that AL.

These effects are lagged by the current year and the following year.

There is evidence of a potential reverse causality (the increase in prices also leads to a higher supply of AL).

The causal effects are statistically significant at the 99% level.

## 6. Conclusions

The analysis demonstrated a statistically significant positive causal effect between the supply of short-term rentals (AL) and the average price per square meter of housing at both the parish and municipal levels in Lisbon.

The results show that each AL increases the average price of housing in the respective parish by €0.35 per square meter and by €0.05 per square meter at the municipal level. Note that €0.35 per square meter corresponds to approximately 10% of the average €3 per square meter determined through the initial descriptive analysis.

A 1% increase in the AL/H ratio leads to an average increase of 0.5% (or €45 per square meter) in housing prices at the parish level.

The presence of a reverse causality phenomenon is statistically significant: the increase in housing prices has also led to a higher supply of AL, creating a difficult-to-break vicious cycle.

These results contribute to the literature and the formulation of more informed public policies (e.g., limiting or taxing the issuance of licenses based on the number of AL or the % AL/H by geographic area).

Public policies should consider both negative externalities (e.g., housing prices, gentrification) and positive externalities (e.g., economic activity, urban renewal) through multicriteria decision analyses.






















