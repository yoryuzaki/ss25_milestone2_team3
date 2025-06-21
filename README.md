# Predictive Asthma Prevalence Modeling

This repository contains the code and data used for our Milestone II porject, which aims to understand and predict asthma prevalence at the census tract level using social determinants of health (SDOH) and environmental factors. 

Team Members: 
Daida, K.      kdaida@umich.edu
Petrov, A.     alynap@umich.edu
Ryuzaki, Y.    yryuzaki@umich.edu


## Problem, Impact, and Motivation
Asthma is a chronic respiratory condition that has a high economic burden (Bhattacharya et al., 2024) and an increasing prevalence rate in the United States (Pate & Zahran, 2024). Assessing the socioeconomic and environmental factors related to asthma prevalence allows us to identify communities that are vulnerable to health disparities, such as decreased access to medical care and increased rates of poor air quality indices. One of the study authors works for a managed care organization (MCO) that serves Medicaid and dual Medicare/Medicaid recipients, and is interested in providing additional asthma prevention funding for communities with high asthma prevalence rates. 


## Data Source
Our study used the following data sources: 

Centers for Disease Control and Prevention (CDC) PLACES: Used for asthma prevalence at the census-tract level (PLACES: Local Data for Better Health, 2024). This dataset is located and accessed through the CDC API URL (https://data.cdc.gov/resource/cwsq-ngmh.json). 

Social Vulnerability Index (SVI): Used for socioeconomic status, household characteristics, racial or ethnic minority status, housing type and transportation, and other social determinants of health (Social Vulnerability Index, 2024). This dataset is located and downloaded at the SVI landing page (https://www.atsdr.cdc.gov/place-health/php/svi/svi-data-documentation-download.html) filtered on the year 2022. 

Air Quality System (AQS): Used for air quality and other environmental factors (Air Quality System (AQS) | US EPA, 2025). This dataset is located and  accessed through the CDC API URL (https://data.cdc.gov/resource/96sd-hxdt.json). 

Census Regions: Used for mapping the FIPS to US regions for visualizations (U.S. Census Bureau, n.d.) and considered an auxiliary dataset. This file is a PDF that maps the state FIPS to a US region. We manually converted the mapping to a CSV file and stored it as 'Region.csv' within the repository. 


## Project Setup
The study methodology was set up as follows: 
- Data collection and cleaning of three datasets, joined at the census-tract level. 
- Data exploration analysis. 
- Unsupervised algorithms for: 
  - i. Dimensionality reduction using principal component analysis (PCA). 
  - ii. Feature engineering using clustering and community detection. 
- Supervised algorithms for prediction:
  - i. Two baseline models were evaluated: linear regression and random forest models. Each baseline model had three approaches:
      -  Raw features only
      -  PCA transformed features
      -  Raw features combined with outputs from K-Means clustering and community detection
  - ii. An additional two models were evaluated: gradient boosting and XGBoost. 
- Failure analysis and advanced model evaluation on the best performing supervised learning model.


All of the above sections can be found in the Predictive Asthma Modeling notebook. Additionally, an auxiliary analysis was performed on the input data to estimate the severity of the multicollinearity issue, and the details of this analysis can be found in the Auxiliary SVI Data Analysis notebook.


## How to Run the Code
Clone this repo using:
```bash
git clone https://github.com/yoryuzaki/ss25_milestone2_team3.git
cd ss25_milestone2_team3
```

Start with either the Predictive Asthma Modeling or Auxiliary_SVI_Data_Analaysis notebook. If it's your first time running any of the notebooks, ensure you uncomment the following section within the notebooks to install the necessary libraries:
```bash
!pip install -r requirements.txt
```

