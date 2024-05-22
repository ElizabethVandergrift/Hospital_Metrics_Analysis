# Project-1: The Hospital Value-Based Purchasing (VBP) Program - Questions and Overview

## Contributors
This project is a collaborative effort by Elizabeth Vandergrift and Juan Camilo Bohórquez Rozo, who are responsible for the code and data analysis.

## Table of Contents
- [Overview](#overview)
- [Importance of the Hospital VBP Program](#importance-of-the-hospital-vbp-program)
- [Measures Used in the Hospital VBP Program](#measures-used-in-the-hospital-vbp-program)
- [Questions of Investigation](#questions-of-investigation)
- [Procedure](#procedure)
- [Results](#results)
- [Resources](#resources)
- [Project Structure](#project-structure)

## Overview
**CMS, What is it?** The Centers for Medicare and Medicaid Services (CMS) provides health coverage to over 100 million people through Medicare, Medicaid, the Children’s Health Insurance Program, and the Health Insurance Marketplace. CMS aims to strengthen and modernize the Nation’s healthcare system, providing access to high-quality care and improved health at lower costs.

**What is the Hospital VBP Program?** The Hospital Value-Based Purchasing (VBP) Program rewards acute care hospitals with incentive payments based on the quality of care provided in the inpatient hospital setting. Hospitals with high VBP scores are incentivized through:
- 2% Medicare payments withheld from participating hospitals.
- Reductions in payments are used to fund value-based incentives based on hospital performance.
- The reduction and incentive are applied as a claim-by-claim adjustment in the fiscal year associated with a performance period.

## Importance of the Hospital VBP Program
- Improves the quality of care for hospital patients.
- Enhances the patient experience.
- Reduces adverse events (healthcare errors resulting in patient harm).
- Encourages the adoption of evidence-based care standards and protocols.
- Incentivizes hospitals to improve patient experience.
- Increases transparency of care quality for consumers, clinicians, and others.
- Recognizes hospitals that provide high-quality care at a lower cost to Medicare.

## Measures Used in the Hospital VBP Program
Hospitals are scored on measures including:

### Clinical Outcomes
- 30 Day Mortality (Acute Myocardial Infarction, Coronary Artery Bypass Grafting, Chronic Obstructive Pulmonary Disease, Heart Failure, Pneumonia)
- Hip or Knee Arthroplasty Complication Rate

### Safety
- Infections (Catheter, Central Line Bloodstream, Clostridium, Resistant Bacterial, Surgical Site)
- Patient Safety and Adverse Events Composite

### Efficiency and Cost Reduction
- Medicare Spending per Beneficiary

### Person and Community Engagement
- Communication (Nurses and Doctors)
- Responsiveness of Staff
- Communication about Medication
- Cleanliness and Quietness
- Care Transition
- Overall Rating of Hospital

## Questions of Investigation
1. How is each measure type of the VBP score correlated to the Total Performance Score? Are some measure types driving the Total Performance Score more than others?
2. Does the Person and Community Engagement Measure have relationships with the other measures on the VBP score?
3. How do the measures of the VBP score behave depending on the hospital's ownership?
4. Which state has the best hospital based on the VBP Total Performance Score?
5. Based on the VBP Total Performance Score, where are the best hospitals in the United States?
6. Are state-census variables like the size of population, per capita income, and poverty influencing the Total Performance Score of the VBP evaluated hospitals?

## Procedure
Using Python and libraries such as Pandas, Pathlib, Matplotlib, and APIs, we performed the following steps:

### Merging Information
- Merged datasets from Kaggle.com and Data.CMS.gov using ‘Provided ID’ and ‘Facility ID’ columns.

### Selecting Information
- Counted columns to see the number of hospitals and filtered for columns of interest. Analyzed only weighted values.

### Cleaning Information
- Eliminated empty or NoN values from the dataset.

### Analysis
- Created scatter plots and calculated R-values to investigate correlations.
- Analyzed ownership and performance by categorizing hospitals and plotting averages.
- Grouped information by state and evaluated performance.
- Mapped high-performing hospitals in the US.
- Included state census variables to analyze their influence on hospital performance.

## Results
1. **Correlation with Total Performance Score:** Efficiency and Cost Reduction (0.65) and Safety (0.59) had the highest correlations with the Total Performance Score, but the relationship is not entirely linear due to weighted and normalized scores.
2. **Relationship between Measures:** Low Pearson coefficients indicate no observed correlation among variables.
3. **Hospital Ownership Analysis:** Voluntary non-profit hospitals show consistent performance. Government - State hospitals excel in Clinical Outcomes, while Safety and Person and Community Engagement metrics are high in Physician-owned hospitals.
4. **State Performance:** Alaska has the highest VBP score with few hospitals. Oregon and Wisconsin excel both in high VBP scores and hospital count.
5. **Best Hospitals in the US:** High population density areas have more high-scoring hospitals. Top 25 hospitals are mostly Voluntary Non-Profit - Private.
6. **State-Census Variables:** No direct correlation, but indirect influences are observed. Slight negative relationships between Poverty Count/Rate and Total Performance Score, and a slight positive relationship between Per Capita Income and Total Performance Score.

## Resources
- [CMS.gov - Hospital Value-Based Purchasing](https://www.cms.gov)
- [Data.Medicare.gov - Hospital Compare](https://data.medicare.gov)
- [AHRQ.gov - Patient Safety and Quality](https://www.ahrq.gov)
- [HealthData.gov - Hospital General Information](https://healthdata.gov)
- [United States Census Bureau API](https://www.census.gov/data/developers/data-sets.html)

## Project Structure
- **Jupyter Lab File:** `Project-1.ipynb` - Contains all the code and analysis for the project.
- **Output Folder:** `output/` - Contains 15 figures answering the analysis questions.
- **PDF Files:** `project_presentation.pdf` - Summarized presentation.
- **Read Me:** `writeup.md` - Topic overview, summarized procedure, and detailed results analysis.
