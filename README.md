# Data-Driven Well-Being: Predicting Life Satisfaction

This project aims to explain and predict life satisfaction using large-scale survey data and machine learning techniques. The objective is to identify key factors influencing individual well-being and provide insights into what drives happiness across different populations.

## Project Overview

The project is based on the **European Social Survey (ESS)** dataset and follows a data engineering and analytics pipeline inspired by the **Medallion Architecture**. The workflow includes data ingestion, cleaning, transformation, feature engineering, and predictive modeling.

The final goal is to build a model that predicts life satisfaction and identifies the most important determinants of well-being.

## Dataset

**Source:** European Social Survey (ESS)  
**Website:** https://ess.sikt.no/en/  

Due to file size limitations, the dataset is not stored in this repository.

**Download the data here:**  
https://drive.google.com/drive/folders/1FY-zySFCDLBAn1MUeTkgcKyk7X0SQQb6?usp=sharing  

### Dataset Details
- 17 CSV files and 17 SPSS files  
- Covers **11 ESS rounds**  
- **500,000+ observations** across **39 countries**  
- CSV files used as raw data  
- SPSS files used for metadata (variable definitions and value labels)

## Architecture

The project follows a **Medallion Architecture** implemented in Databricks:

### Bronze Layer (Data Ingestion)
- Raw ESS data ingestion from multiple rounds  
- Storage of unprocessed datasets  

### Silver Layer (Data Preparation)
- Feature selection and classification of variables:
  - Context variables (e.g., country, age, gender)
  - Partially controllable variables (e.g., income, health, education)
  - Controllable variables (e.g., social activity, internet use)
- Harmonization of variables across ESS rounds  
- Handling missing values using SPSS metadata  
- Merging all rounds into a unified dataset  
- Recoding target variable (life satisfaction)  
- Creation of final analytical dataset (Delta table)

## Machine Learning & Analytics
- **Target variable:** Life satisfaction (3-class ordinal)
- **Features:** 17 predictors across economic, social, health, and demographic domains  
- **Model:** Random Forest  
- **Balanced accuracy:** 59.24% (above baseline 58.68%)  

### Key Findings
- Economic satisfaction and income perception are the strongest predictors  
- Economic variables account for ~42% of total feature importance  
- The model generalizes well across training and validation datasets  

---

## My Contribution
I was responsible for the **data engineering and preparation stages**, specifically:

- **Bronze Layer:** Data ingestion and raw data handling  
- **Silver Layer:** Data cleaning, transformation, feature engineering, and dataset construction  

The **Machine Learning modeling and Power BI visualization components** were developed by other members of the project team.

## Project Objective

The main objective of this project is to better understand the drivers of life satisfaction and provide data-driven insights into what influences human well-being.

As described in the project presentation :contentReference[oaicite:0]{index=0}, the goal is to help individuals and researchers identify key factors contributing to happiness and support evidence-based decision-making.

## Technologies Used

- Python  
- Databricks  
- Pandas / PySpark  
- Scikit-learn  
- Power BI (visualization)

## Notes

- Due to dataset size, data is hosted externally (Google Drive link above)  
- Full methodology and results are documented in the project materials  
