**Lending Club: Loan Default Prediction Case Study
Author: Lena Arora**

**Table of Contents**
1. General Info
2. Problem Statement & Approach
3. Data Cleaning & Sanity Checks
4. Univariate & Bivariate Analysis
5. Observations & Conclusions
6. Technologies Used
7. Acknowledgements
8. General Information

**Project Background**
This case study revolves around Lending Club, a consumer finance company that provides personal loans to individuals. Lending Club needs to assess the risk of loan default before issuing loans to applicants. The main objective of this analysis is to identify patterns in applicant data that predict whether a loan will be paid back in full or charged off (defaulted).
The company is particularly interested in analyzing applicant attributes such as income, loan amount, debt-to-income ratio (DTI), home ownership, and loan purpose to develop a robust model that can reduce the rate of loan defaults. By analyzing the loan applicant data, Lending Club hopes to make more informed lending decisions, minimize financial losses, and reduce the risks associated with loan issuance.

**Business Problem**
Lending Club is facing the challenge of high default rates on loans. Understanding the key factors influencing loan defaults will help in:
Identifying high-risk applicants before loan approval.
Adjusting loan conditions (interest rates, amounts, etc.) to account for risk.
Minimizing financial losses and improving profitability.

**Dataset**
The dataset used for the analysis includes historical loan data with various attributes such as:
**Applicant Info:** Annual income, home ownership status, verification status, etc.
**Loan Info**: Loan amount, loan purpose, interest rate, and loan status (Charged Off or Paid).
**Other Financial Info:** Debt-to-income ratio (DTI), revolving utilization rate, etc.

**Problem Statement & Approach
Problem Statement**
The goal of this project is to predict loan default risk by identifying factors that influence whether a loan will be paid back or charged off. By analyzing historical data, Lending Club aims to:
Improve loan approval processes by using data-driven decision-making.
Minimize financial losses due to defaults.
Offer personalized loan terms based on predicted risk.

**Approach
Data Cleaning & Sanity Checks:**

Remove or handle missing values in key columns.
Remove unnecessary columns that do not contribute to loan decisions.
Perform sanity checks on the target variable (loan status) and continuous variables.

**Univariate & Bivariate Analysis:**
Analyze individual variables and their distributions using charts like box plots and histograms.
Investigate relationships between pairs of variables using scatter plots and correlation matrices.
Outlier Treatment:

**Identify and remove outliers that could skew the analysis.
Modeling and Predictions:**

Based on insights from the analysis, propose a model that can predict loan defaults.

**Data Cleaning & Sanity Checks
Data Cleaning
Null Data Treatment:**

Any columns with null values that are critical for loan decision-making are either dropped or filled with appropriate values (e.g., mode for categorical columns, median for continuous ones).
Dropping Unnecessary Columns:

Columns irrelevant to the loan decision process (e.g., applicant’s name, date of birth) are removed.

**Handling Missing Values:**
Columns with missing values are either dropped or filled with mode values for categorical features (like home ownership) and median for continuous variables (like annual income).
Sanity Checks:

We use info() and describe() to get an overview of the data, ensuring no erroneous entries are present.
Columns like loan_status, revol_util, and interest_rate are cleaned by removing unwanted characters (e.g., percentage signs).

**Sanity Check Results**
**Loan Status:** Checked for unique values (e.g., Charged Off, Paid).
**Revolving Utilization Rate (revol_util):** Cleaned percentage signs.
**Interest Rate:** Cleaned to remove percentage signs for better analysis.
**Home Ownership:** Columns with missing values are handled by placing them under a "Others" category.

**Univariate & Bivariate Analysis
Univariate Analysis
Box Plot:**
A box plot was used to display the distribution of annual income and loan amount, highlighting potential outliers.

**Distribution Plot (Distplot):**
Histograms and KDE (Kernel Density Estimation) plots are used to visualize the distribution of key variables like annual income, DTI, and interest rate.

**Bivariate Analysis
Bar Chart:**
Bar charts were used to visualize the distribution of categorical variables like loan status (Charged Off vs. Paid) against other features such as home ownership, loan purpose, and verification status.

**Correlation Matrix:**
A correlation matrix was created to explore relationships between continuous variables like annual income, loan amount, DTI, and revolving utilization.

**Scatter Plot:**
Scatter plots were used to observe relationships between numerical variables like annual income and interest rate, and their influence on loan status.

**Observations from Analysis
Loan Default (Charged Off):**

Around 14-16% of applicants default on their loans, based on the loan status analysis.
High DTI (greater than 1) correlates strongly with default, as individuals with higher DTI ratios are over-leveraged and more likely to default.
Home Ownership:

Renters are more likely to default compared to homeowners or those with mortgages.

**Verification Status:** Non-verified applicants tend to default more frequently, suggesting that lack of verification increases default risk.
**Loan Purpose:**
Applicants seeking loans for debt consolidation are more likely to default, highlighting that people consolidating debt might already be financially strained.

**DTI vs. Loan Default:**
Higher DTI ratios (above 2) show a substantial increase in defaulted loans. Most loans charged off have a DTI greater than 1.

**Annual Income & Interest Rate:**
Individuals with annual incomes between $25,000 and $75,000 tend to default more frequently.
Loans with an interest rate between 10%-17.5% also show higher default rates.
Correlation Matrix Insight
A weak negative correlation of -0.075 between annual income and revolving utilization indicates that higher income slightly reduces credit utilization.
Stronger positive correlations were observed between DTI and credit utilization, suggesting that individuals with higher debt burdens use more credit.


****Observations & Conclusions**
**1. DTI and Loan Default** **
**Observation:** Loans with a DTI ratio greater than 1 are more likely to default. Most charged-off loans fall into the high DTI category (DTI > 1). Borrowers with high DTI ratios are already heavily burdened with debt, making it harder for them to repay additional loans.
Conclusion: DTI ratio is a strong indicator of financial strain and a critical factor in loan default risk. Lending Club should prioritize low DTI applicants and consider using DTI thresholds for loan approvals or adjusted loan terms (such as higher interest rates for higher DTI).
**2. Home Ownership and Default Risk**
Observation: Applicants who rent are significantly more likely to default on their loans than homeowners or individuals with a mortgage. Renters may have less financial stability and lower asset accumulation compared to homeowners.
Conclusion: Home ownership status should be a key factor in risk assessment. Renters might represent a higher default risk and may require higher scrutiny or different loan conditions (e.g., lower loan amounts or higher interest rates).
**3. Verification Status and Default Risk**
Observation: Non-verified applicants (i.e., those not verified by Lending Club) show a much higher tendency to default on loans than those who have been verified. This suggests that lack of verification could be a proxy for unreliable applicants or applicants with lower financial transparency.
**Conclusion:** Verification status should be strongly factored into loan approval decisions. Applicants who are not verified may represent a higher risk and should be carefully evaluated before approval.
**4. Loan Purpose and Default Rate**
**Observation:** Applicants who took out loans for debt consolidation are more likely to default than those applying for personal or business loans. This may indicate that debt consolidation applicants are already in financial distress.
**Conclusion:** Loan purpose should be considered when assessing risk. Applicants applying for debt consolidation loans should be viewed with caution, and Lending Club might want to offer stricter criteria or higher interest rates for such loan types.
**5. Income Level and Default Risk**
**Observation:** Applicants with annual income between $25,000 and $75,000 tend to default more frequently compared to individuals in other income brackets. This could be because they might not have sufficient disposable income to cover loan payments, or they may have other financial obligations.
**Conclusion:** Income level is a moderate but significant factor in predicting loan default. While income alone may not be a strong predictor, applicants with annual income in this range should be closely monitored, especially if they have high DTI ratios or are seeking loans for debt consolidation.
**6. Interest Rate and Default Correlation**
**Observation:** Loans with an interest rate between 10% and 17.5% tend to have a higher default rate, suggesting that loans in this range may be offered to borrowers who are higher risk. While higher interest rates can reflect higher perceived risk, they may also make loan repayment more challenging for borrowers, pushing them into default.
**Conclusion:** Interest rates need to be calibrated based on the applicant’s risk profile. Lending Club could consider offering lower interest rates to lower-risk borrowers and adjusting rates for high-risk applicants (e.g., higher DTI or lower income).
**7. Annual Income and Interest Rate by Home Status**
**Observation:** Individuals with an annual income between $25,000 and $75,000 and an interest rate between 10% and 17.5% are most likely to default. This income range, coupled with mid-tier interest rates, presents a potential risk segment.
**Conclusion:** Lending Club might consider offering tailored loan products or adjusting loan amounts and interest rates for individuals in this income range to reduce the likelihood of default. Lower-risk applicants with higher income could be offered more favorable loan terms.
**8. Revolving Utilization Rate (Revol_util) and Default Risk**
**Observation:** Higher revolving utilization rates (e.g., the ratio of debt on revolving credit lines) correlate with a higher likelihood of default. This suggests that individuals who are more reliant on credit for daily expenses may have trouble paying off loans.
**Conclusion:** Revolving utilization is a strong indicator of financial health. Lending Club should assess applicants’ revolving credit usage as part of the risk evaluation. Lower revolving utilization (below 30%) could indicate better financial management and a lower risk of default.
**9. Correlation Matrix Insights
Observation:** The negative correlation between annual income and revolving utilization rate suggests that individuals with higher incomes tend to use less credit. Additionally, DTI and loan amount show strong positive correlations with credit utilization, indicating that borrowers with higher debt loads or larger loans tend to use more credit.
**Conclusion:** Credit utilization should be closely monitored alongside income levels and loan amount. Lending Club could leverage these correlations to build a more accurate risk model by taking into account both credit behavior and income patterns.
**10. Loan Amount and Default Rate**
**Observation:** Higher loan amounts generally correlate with a higher probability of default. Borrowers with larger loans are often more leveraged and might have trouble repaying large sums if their financial situation worsens.
**Conclusion:** Lending Club should consider loan amount as a critical factor in its risk assessment. Large loans may warrant stricter approval criteria (e.g., higher DTI or income thresholds) or adjustments to loan terms.
**11. Time-Series Analysis (Not Included in Data)**
**Observation:** In future analyses, examining loan status trends over time (e.g., defaults by month, quarter, or year) could provide insights into how economic cycles or company policy changes impact default rates.

**Conclusion:** Incorporating time-series analysis could help Lending Club anticipate future default risks and adjust lending strategies based on external economic factors (e.g., recession periods, rising interest rates).

**Technologies Used**
**Pandas -** Version 1.5
**NumPy -** Version 1.23
**Matplotlib -** Version 3.6
**Seaborn -** Version 0.11
**Scikit-learn -** Version 1.0

**Contact:
Lena Arora**
