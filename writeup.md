# Project-1

# The Hospital Value-Based Purchasing (VBP) Program - Questions and Overview

## Contributors

This project is a collaborative effort by Elizabeth Vandergrift, Juan Camilo Bohórquez Rozo who are responsible for the code and data analysis.

## Table of Contents

1. [Overview](#overview)
2. [Importance of the Hospital VBP Program](#importance-of-the-hospital-vbp-program)
3. [Measures Used in the Hospital VBP Program](#measures-used-in-the-hospital-vbp-program)
4. [Questions of Investigation](#questions-of-investigation)
5. [Procedure](#procedure)
6. [Results](#results)
5. [Resources](#resources)
6. [Project Structure](#project-structure)

## Overview

CMS, What is it?
The Centers for Medicare and Medicaid Services (CMS) provides health coverage to more than 100 million people through Medicare, Medicaid, the Children’s Health Insurance Program, and the Health Insurance Marketplace. The CMS seeks to strengthen and modernize the Nation’s health care system, to provide access to high-quality care and improved health at lower costs.

What is it?
The Hospital VBP Program rewards acute care hospitals with incentive payments for the quality of care provided in the inpatient hospital setting and, it is based on the quality of care they deliver. Hospitals with high VBP scores are incentivized like this: 

- 2% Medicare Payments withheld from Participating Hospitals.
- Reductions in payments are used to fund Value-Based Incentives based on Hospital Performance
- Apply the reduction and incentive as a claim-by-claim adjustment in the fiscal year associated with a performance period

Why is it important?
- It makes the quality of care better for hospital patients.
- Hospitals create a better experience for patients.
- Helps to eliminate or reduce adverse events (healthcare errors resulting in patient harm).
- They are adopting evidence-based care standards and protocols to obtain the best outcomes for Medicare patients.
- Incentivates hospitals to improve patient experience.
- Increases the transparency of care quality for consumers, clinicians, and others.
- Recognizes hospitals that provide high-quality care at a lower cost to Medicare.

What measures are used in the Hospital VBP Program?
Hospitals are scored in measures like: 

Clinical Outcomes: At least 2 Measures with at least 25 eligible discharges
- 30 Day Mortality- Acute Myocardial Infraction, Coronary Artery Bypass Grafting, Chronic Obstructive Pulmonary Disease (COPD), Heart Failure, Pneumonia
- Hip or Knee Arthroplasty Complication Rate
Safety: At least two measures with one being predicted infection by CDC
- Infections- Catheter, Central Line Bloodstream, Clostridium, Resistant Bacterial, Surgical Site
- Patient Safety and Adverse Events Composite
Efficiency and Cost Reduction: Minimum 25 Episodes of Care
- Medicare Spending per Beneficiary
Person and Community Engagement- Survey- At least 100 Surveys Completed
- Communication- Nurses and Doctors
- Responsiveness of Staff
- Communication about Medication
- Cleanliness and Quietness
- Care Transition
- Overall Rating of Hospital

## Questions of Investigation

1. How is each Measure Type of the VBP score correlated to the Total Performance score?  Are some Measure Types driving the Total Performance Score more than others?
2. Does the Person and Community Engagement Measure have relationships with the other Measures on the VBP score?
3. How do the Measures of the VBP score behave depending on the hospital's ownership?
4. Which state has the best Hospital based on the VBP Total Performance Score? 
5. Based on the VBP Total Performance Score where are the best hospitals in the United States?
6. Are state-census variables like the size of Population, the Per Capita Income and the poverty influencing the Total Performance Score score of the VBP evaluated hospitals?

## Procedure

Using Python as a coding language, libraries like Pandas, Pathlib, Matplotlib, and APIs we were able to make  the following

- Merging Information

We merged datasets found in Kaggle.com and in Data.CMS.gov, one of them including the Hospital information (Hospital General Information), another one with the scores of each hospital in the VBP score (Hospital Value-Based Purchasing (HVBP) - Total Performance Score), and last another one that included the Latitude and Longitude of each hospital (US Hospital Locations). This was possible due to the ‘Provided ID’ and ‘Facility ID’ columns each of the data files possess.

- Selecting information

To see the number of hospitals in the study we made a count of each column in the data frame; and this also allowed us to see the columns of information we were working with, in that way, we were able to filter just the columns that were part of our interest. Only weighted values were analyzed in this study; a selection of only those was made as the data presented unweighted values as well.

- Cleaning information

Empty values or NoN Values were eliminated from the dataset

1. How is each Measure Type of the VBP score correlated to the Total Performance score?  Are some Measure Types driving the Total Performance Score more than others?

We created a scatter plot of each variable against the Total Performance Score, created the graph equation, and also calculated the R-value for each case

2. Does the Person and Community Engagement Measure have relationships with the other Measures on the VBP score?

We created a scatter plot of each variable against the Community and Personal Engagement, created the graph equation, and also calculated the R-value for each case

3. How do the variables of the VBP score behave depending on the hospital's ownership?

We counted the values of the amount of hospitals we had in each ownership and graphed it in a piechart. Also, grouped the values by ownership and calculated an average of each variable in the VBP score. This was also plotted.

4. Which state has the best Hospital based on the performance of their VBP score?

We grouped the information by state and created a count to calculate the amount of hospitals per state evaluated, we also created an average of the Total Performance Score per state, and we finally plotted the result.

5. Based on the VBP score Where are the best hospitals in the United States?

We filtered the highest values of the VBP score for all the hospitals and displayed a map, first with all the hospitals in the US and then with the best ones.

6. Are state-census variables like the size of the Population, the Per Capita Income, and poverty influencing the score of the VBP-evaluated hospitals

We included information from a State Census API and created a scatter plot for ‘Poverty’, ‘Per Capita Income’, and ‘Population’ against the Total Performance Score, We created the graph equation and also calculated the R-value for each case. The Census API was utilized to gather state-census variables such as population size, per capita income, and poverty levels. By leveraging these resources, we aim to answer our investigative questions and provide insightful analysis on the performance of hospitals under the VBP Program.


## Results

- Question 1
Considering that the "R" value or Pearson correlation coefficient gauges the strength of the linear relationship between two variables, with a range from -1 to 1, it's notable that the highest correlation with the VBP Total Score is observed in Efficiency and Cost Reduction (0.65), followed by Safety (0.59), Person and Community Engagement (0.41), and Clinical Outcomes (0.33).
However, due to the utilization of normalized and weighted scores rather than raw scores, the Pearson correlation tool may not fully capture the complexity of the data. This suggests that while Efficiency and Cost Reduction, as well as Safety, exhibit the strongest correlations with the total score, the relationship is not entirely linear, reflecting the influence of the weighted and normalized scores on the overall VBP assessment.

- Question 2
There is no observed correlation among the variables, as indicated by the low Pearson coefficient, suggesting a lack of linear relationship between them. This outcome is expected, considering that in the VBP equation, the variables are not interdependent; they collectively influence the Total Score but do not exert influence on one another. 

- Question 3
Most hospitals in our dataset fall under the Voluntary non-profit ownership category, with a significant portion being privately owned. The next largest sub-category comprises proprietary hospitals, while our sample size for hospitals under Federal and Physician Ownership is relatively small. Upon examining the behavior of variables across different ownership types, we observe that the Voluntary non-profit category demonstrates consistent behavior across its subcategories (Church, Private, Other). Government - State hospitals exhibit the best Clinical Outcomes, while Safety and Person and Community Engagement metrics excel in Physician-owned hospitals, although our dataset lacks a substantial representation of this ownership type. Efficiency and cost reduction, on the other hand, are notably high in Government - Federal hospitals.

- Question 4 
This graph illustrates the distribution of Hospital Value-Based Purchasing (VBP) scores across different states. Notably, Alaska stands out with the highest VBP score despite having a small number of hospitals included in the analysis (3). Conversely, states like Montana and Idaho exhibit a larger count of hospitals, yet their average VBP scores remain notably high. This suggests that hospitals in these states are more likely to possess commendable VBP scores and consequently provide an enhanced patient experience.
Oregon and Wisconsin emerge as the top-performing states, boasting both high VBP scores and a substantial number of hospitals. This alignment between VBP score and hospital count indicates that these states consistently excel in delivering quality healthcare services across a larger healthcare infrastructure.

- Question 5
Regions with high population densities, such as the Northeast, West Coast, and Great Lakes areas, exhibit substantial clusters of Value-Based Purchasing (VBP) participating hospitals as well as high-scoring institutions. In contrast, rural areas in the central United States show a notable absence of participating hospitals. The top 25 hospitals based on Total Performance Scores are predominantly located outside the central region. Within this top-performing group, a greater number of hospitals are classified as Voluntary Non-Profit - Private compared to any other category. Notably, there are no Government or Physician-owned hospitals among the top 25.

- Question 6
No direct correlation is evident in the graphs we've generated, likely due to these variables not being directly assessed by the VBP score. However, factors such as poverty, population size, and per capita income can indirectly influence healthcare outcomes, including those measured by the Hospital Value-Based Purchasing (VBP) program. While these variables are not typically included in the VBP program's direct measures, they play a crucial role in shaping population health, healthcare access, and utilization patterns, which in turn can impact hospital performance and outcomes.
There is a slightly negative relationship between Poverty Count and Total Performance Score and Poverty Rate and Total Performance Score. There is a slight postitive relationship between Per Capita Income and Total Performance Score.  There are areas of the country that are less populated and may also have less income that did not have hospitals included in VBP program.  We used zip codes as reference for poulation which might not show the full picture because people from multiple zip codes may use a singular hospital.


## Resources

To further understand the Hospital VBP Program and access relevant data, refer to the following resources:

- [CMS.gov - Hospital Value-Based Purchasing](https://www.cms.gov/Medicare/Quality-Initiatives-Patient-Assessment-Instruments/Value-Based-Programs/HVBP/Hospital-Value-Based-Purchasing)
- [Data.Medicare.gov - Hospital Compare](https://data.medicare.gov/)
- [AHRQ.gov - Patient Safety and Quality](https://www.ahrq.gov/topics/patient-safety-and-quality.html)
- [HealthData.gov - Hospital General Information](https://healthdata.gov/dataset/hospital-general-information)
- [United States Census Bureau API](https://www.census.gov/data/developers/data-sets.html)


## Project Structure

- **Jupyter Lab File**: `Project-1.ipynb` - Contains all the code and analysis for the project.
- **Output Folder**: `output/` - Contains 15 figures answering the analysis questions.
- **PDF Files**:`project_presentation.pdf` - Summarized presentation.
  **Read Me**: `writeup.md` - Topic overview, summarized procedure and detailed results analysis.
