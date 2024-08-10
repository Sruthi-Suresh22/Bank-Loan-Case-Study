# BANK LOAN CASE STUDY

### Table of Contents

- [Project Description](#project-description)
- [Dataset Details](#dataset-details)
- [Data Preparation](#data-preparation)
- [Tasks and Insights](#tasks-and-insights)
- [Conclusion](#conclusion)

### Project Description

This project focuses at a finance company that specializes in lending various types of loans to urban customers. 

The company faces a challenge : some customers who don't have a sufficient credit history take advantage of this and default on their loans. 

As a data analyst, the task is to use Exploratory Data Analysis (EDA) to analyze patterns in the data and ensure that capable applicants are not rejected.

When a customer applies for a loan, your company faces two risks:
 - If the applicant can repay the loan but is not approved, the company loses business.
 - If the applicant cannot repay the loan and is approved, the company faces a financial loss.

The dataset contains information about loan applications. It includes two types of scenarios:
 - Customers with payment difficulties: These are customers who had a late payment of more than X days on at least one of the first Y installments of the loan.
 - All other cases: These are cases where the payment was made on time.

When a customer applies for a loan, there are four possible outcomes:
 - Approved: The company has approved the loan application.
 - Cancelled: The customer cancelled the application during the approval process.
 - Refused: The company rejected the loan.
 - Unused Offer: The loan was approved but the customer did not use it.

### Dataset Details

There are 3 CSV files containing the information:
1. **application_data.csv** : Provides details about the current loan applications
 - No. of records : 49,999
 - No of Columns : 122
2. **previous_application.csv** : Contains information about previous loan applications.
 - No. of records : 49,999
 - No of Columns : 37
3. **columns_description.csv** : Describes the columns present in the other datasets, explaining what each column represents.

### Data Preparation

- **For Categorical Columns**:
  - For the column `OCCUPATION_TYPE`, the blank values were replaced with "Occupation not known".
  - For the column `NAME_TYPE_SUITE`, the blank values were replaced with "Unaccompanied" as it is the mode (most occurring) in the column.
- **For Numerical Columns**:
  - All the numerical columns: `AMT_ANNUITY`, `AMT_GOODS_PRICE`, `CNT_FAM_MEMBERS`, `EXT_SOURCE_2`, `EXT_SOURCE_3`, `OBS_30_CNT_SOCIAL_CIRCLE`, `DEF_30_CNT_SOCIAL_CIRCLE`, `OBS_60_CNT_SOCIAL_CIRCLE`, `DEF_60_CNT_SOCIAL_CIRCLE`, `DAYS_LAST_PHONE_CHANGE`, `AMT_REQ_CREDIT_BUREAU_HOUR`, `AMT_REQ_CREDIT_BUREAU_DAY`, `AMT_REQ_CREDIT_BUREAU_WEEK`, `AMT_REQ_CREDIT_BUREAU_MON`, `AMT_REQ_CREDIT_BUREAU_QRT`, `AMT_REQ_CREDIT_BUREAU_YEAR`  were replaced with the median of the respective columns.
  - 1 Missing value was replaced with 0 in the `DAYS_LAST_PHONE_CHANGE` column.
- **Feature Engineering**:
  - Created new columns `CLIENTS_AGE`, `YEARS_EMPLOYED`, `YEARS_REGISTRATION`, `YEARS_ID_PUBLISH`, `YEARS_LAST_PHONE_CHANGE` which shows duration in years for the existing columns `DAYS_BIRTH`, `DAYS_EMPLOYED`, `DAYS_REGISTRATION`, `DAYS_ID_PUBLISH`, `DAYS_LAST_PHONE_CHANGE` respectively. 
  - Also created `AVG_EXT_SOURCE` column which is the average of `EXT_SCORE_2` and `EXT_SOURCE_3`.

### Tasks and Insights

**TASK A : Identify Missing Data and Deal with it Appropriately**

As a data analyst, you come across missing data in the loan application dataset. It is essential to handle missing data effectively to ensure the accuracy of the analysis.

*Task:* Identify the missing data in the dataset and decide on an appropriate method to deal with it using Excel built-in functions and features.

*Hint:* Utilize Excel functions like COUNT, ISBLANK, and IF to identify missing data. Consider using functions like AVERAGE or MEDIAN for imputation or other appropriate methods available in Excel.

*Graph suggestion:* Create a bar chart or column chart to visualize the proportion of missing values for each variable.

**Insights**

- There were 49 columns with null values > 40 %  and remaining 73 columns where null values were < 40 %. 

- Columns with null values > 40 % :
  
![image](https://github.com/user-attachments/assets/a87d4d9b-7465-4864-90fa-f413c43741d0)
![image](https://github.com/user-attachments/assets/980052af-671c-4e7c-a69d-b3e1b203f297)

- Columns with null values < 40 % :
  
![image](https://github.com/user-attachments/assets/44da5b4b-4ae3-4867-9762-a20cd1441f14)

**TASK B: Identify Outliers in the Dataset**

Outliers can significantly impact the analysis and distort the results. You need to identify outliers in the loan application dataset.

*Task:* Detect and identify outliers in the dataset using Excel statistical functions and features, focusing on numerical variables.

*Hint:* Utilize Excel functions like QUARTILE, IQR, and conditional formatting to identify potential outliers. Consider applying thresholds or business rules to determine if the outliers are valid data points or require further investigation.

*Graph suggestion:* Create box plots or scatter plots to visualize the distribution of numerical variables and highlight the outliers.

**Insights**

 - Outliers were detected for the below columns by plotting Box and Whisker plot : 
![image](https://github.com/user-attachments/assets/e00b600c-309b-4ba8-b436-30c762ef65be)
![image](https://github.com/user-attachments/assets/b68055b1-625a-4d88-b830-9a8627b294d3)
![image](https://github.com/user-attachments/assets/5d3245fe-cd3c-495c-b136-fbd574e34d57)
![image](https://github.com/user-attachments/assets/665ec96e-58a2-421f-8e29-2d29e5296a5d)
![image](https://github.com/user-attachments/assets/4d06a461-2719-401c-b375-9710c886f02f)
![image](https://github.com/user-attachments/assets/3454343f-bd9f-4a43-9902-dee23d6eca5a)
![image](https://github.com/user-attachments/assets/0f6b2ed2-269e-470f-987e-3e96c285e3b1)
![image](https://github.com/user-attachments/assets/4792caa4-7201-4819-b052-4a314e795331)
![image](https://github.com/user-attachments/assets/9e7107ca-88a5-4d21-8a11-0d902637c60f)
![image](https://github.com/user-attachments/assets/076bad2e-b55f-4e42-aeeb-424a4706b0c3)
![image](https://github.com/user-attachments/assets/a6b3688f-d0d1-43d6-b93a-f33c42de9f14)
![image](https://github.com/user-attachments/assets/fa40bc3e-733d-401d-ad13-c562f8bce25a)
![image](https://github.com/user-attachments/assets/fa45410c-8d52-4f22-95d3-5ca9e131587e)

- Removing Outliers:
  - There were 8924 records where the `YEARS_EMPLOYED` was given as 1000.7 which is technically not possible. So, these records were deleted.
  - In the `AMT_INCOME_TOTAL`, there was a record with income as 11700000 which was removed to prevent skewness.
  - Overall, 8925 records were deleted and remaining 41704 records for analysis.

**TASK C: Analyze Data Imbalance**

Data imbalance can affect the accuracy of the analysis, especially for binary classification problems. Understanding the data distribution is crucial for building reliable models.

*Task:* Determine if there is data imbalance in the loan application dataset and calculate the ratio of data imbalance using Excel functions.

*Hint:* Utilize Excel functions like COUNTIF and SUM to calculate the proportions of each class. Compare the class frequencies to assess data imbalance.

*Graph suggestion:* Create a pie chart or bar chart to visualize the distribution of the target variable and highlight the class imbalance.

**Insights**

![image](https://github.com/user-attachments/assets/c94d680e-b58f-408d-b329-97a695c96de9)

- Around 9 % of the clients belong to Class -1 i.e., client with payment difficulties: he/she had late payment more than X days on at least one of the first Y installments of the loan in our sample.
- Remaining 91 % falls under Class – 0 i.e., clients with no payment difficulties.

![image](https://github.com/user-attachments/assets/2acffeb6-fa02-454e-8350-062e89770023)

- Around 10 % of the clients have applied for Revolving loans.
- Remaining 90 % clients have applied for Cash loans.

**TASK D: Perform Univariate, Segmented Univariate, and Bivariate Analysis**

To gain insights into the driving factors of loan default, it is important to conduct various analyses on consumer and loan attributes.

*Task:* Perform univariate analysis to understand the distribution of individual variables, segmented univariate analysis to compare variable distributions for different scenarios, and bivariate analysis to explore relationships between variables and the target variable using Excel functions and features.

*Hint:* Utilize Excel functions like COUNT, AVERAGE, MEDIAN, and statistical functions for descriptive analysis. Utilize Excel features like filters, sorting, and pivot tables for segmented and bivariate analysis.

*Graph suggestion:* Create histograms, bar charts, or box plots to visualize the distributions of variables. Create stacked bar charts or grouped bar charts to compare variable distributions across different scenarios. Create scatter plots or heatmaps to visualize the relationships between variables and the target variable.

**Insights**

1. **Univariate Analysis**

- Most of the clients have applied for Consumer Loans followed by Cash loans. 
![image](https://github.com/user-attachments/assets/a1ed67b9-0687-4412-b739-214430bd972f)

- About more than half of the previous applicants loans were approved by the company. 
![image](https://github.com/user-attachments/assets/1cf4f3d5-925f-4c28-9fc6-0989f266791f)

- Most of the clients have chosen to pay “Cash through the bank” as the Payment method for the previous application.
![image](https://github.com/user-attachments/assets/cef2f108-cfdc-4f84-b435-b2f4f494c63b)

- This shows that  72% of the clients were old clients when applying for the previous application.
![image](https://github.com/user-attachments/assets/43d9072e-1b3e-4054-8748-5d38a5fe838d)

2. **Univariate Segmented Analysis**

- Most of the loans that were currently applied were “Cash Loans” in which almost 10% are defaulters.
![image](https://github.com/user-attachments/assets/2c222454-336d-4f05-9f80-6ab0c15e0697)

- The number of female clients is higher than the number of male clients. Also based on the analysis, we can infer that males have higher chance of not returning their loans (11%).
![image](https://github.com/user-attachments/assets/e84559d9-5cc5-45d9-aac9-4ff8f1cc757f)

- Majority of the applicants falls under the age group of Late 20s to Early 50s and their chance of defaulting is also higher when compared with applicants of above 50 years. 
![image](https://github.com/user-attachments/assets/8df45de1-1107-4fea-98ae-9431e606f0b8)

- Majority of the applicants have been employed in between 0-10 years but the chance of defaulting is also the highest (~10%) followed by clients having 10-20 years of experience.
![image](https://github.com/user-attachments/assets/5152e78d-a95f-45de-b282-d213ad420cd1)

- Most of the applicants / clients were not accompanied by anyone while he/ she was applying for the loan. 
![image](https://github.com/user-attachments/assets/bb1a6bbc-fa05-47b7-9f41-1ab5ddb308ed)

- Most of the applicants / clients have their income type as Working followed by Commercial associate and State Servant.
![image](https://github.com/user-attachments/assets/6c91b7a2-288d-4548-b95e-3acb05d51660)

- Most of the applicants / clients have Secondary / secondary special education followed by Higher education. Only a few clients holds an Academic degree.
![image](https://github.com/user-attachments/assets/f0748799-c9a0-4a2a-823d-b4c4c8a4f711)

- Most of the applicants / clients are Married followed by Single / not married and Civil Marriage.
![image](https://github.com/user-attachments/assets/649962a0-4a59-4b8c-a569-ff88c084c8a0)

- Majority of the clients owns a House/apartment. Clients living with parents and Rented apartment have higher chance of defaulting (~12%) and clients living in office apartments have lower chance of defaulting.
![image](https://github.com/user-attachments/assets/c158f4c0-40b8-4933-9ddb-b8f7803aa8fe)

- Most of the loans are applied by the laborer's followed by Sales staffs, Core staff and Mangers. A significant amount of Applicants occupation is not known. Low-skill Laborers have higher chance of defaulting (~17%) followed by Cooking staffs, Drivers, Laborers, Realty agents, Security staff and Waiter /Barman staffs (~10-11%). Only few loans have been taken by IT Staffs.
![image](https://github.com/user-attachments/assets/9ae85b94-012e-4a6c-ad9e-df55aecf2bd0)

- Most of the applicants / clients have only 2-3 family members.
![image](https://github.com/user-attachments/assets/ef72f8c5-8ef9-4306-80fd-19af7984f39e)

- Most of the applicants / clients have no children or <2 children however, their chance of defaulting is also on the higher side.
![image](https://github.com/user-attachments/assets/42c3f9a2-cd91-4d57-b755-51f03a5536cc)

- Majority of the loans are taken between the range 245000-345000 followed by 445000-545000. The highest chance of defaulting is shown to happen from the clients who have taken loans between 545000-645000 (~12%).
![image](https://github.com/user-attachments/assets/bc9ddb9b-43d4-4b81-83ab-cdcbf02445d1)

- Most of the clients have the Loan annuity range of 22000-32000.
![image](https://github.com/user-attachments/assets/3584a121-ade0-4453-8294-38bc97b6cbdb)

- Most of the clients have the Annual income that falls in the range of 125650-225650.
![image](https://github.com/user-attachments/assets/a64e6071-40c7-4567-aa90-757656af85d9)

- Most of the clients are from the region having the rating as 2. The clients from region 3 have higher chance of defaulting(~12%).
![image](https://github.com/user-attachments/assets/a9e6adc6-9d0c-4bb9-a81f-fcc548f69ac4)

- Majority of the loans are taken by the clients on weekdays. Although the number of loans taken on weekends is less, the chance of not repaying the loans is higher(~8-9%)
![image](https://github.com/user-attachments/assets/3356662d-5511-43e2-aba7-0d88f202f8b5)

- Most of the clients didn’t own a Car but had their own property.
![image](https://github.com/user-attachments/assets/816e3e68-5082-4002-b111-88e0a00e8da1)
![image](https://github.com/user-attachments/assets/597d02a1-8910-4931-a2bc-118742b737cf)

3. **Bivariate Analysis**

- As the age increases, the average credit amount of the loan also increases.
![image](https://github.com/user-attachments/assets/4fe3c217-c765-436f-816e-5096b46e8d31)

- As the income increases, the average credit amount of the loan also increases.
![image](https://github.com/user-attachments/assets/337f0414-d20d-4589-bfb4-db03866404bb)

4. **Bivariate Segmented Analysis**

- Businessman, Maternity leave people, Pensioner, Students have the highest amount credited and they do not tend to default. However, Commercial associate, State Servant, working professionals have higher chance of defaulting.
![image](https://github.com/user-attachments/assets/be7fbf5d-f3f6-4cd3-a842-f5c7916d2772)


**TASK E: Identify Top Correlations for Different Scenarios**

Understanding the correlation between variables and the target variable can provide insights into strong indicators of loan default.

*Task:* Segment the dataset based on different scenarios (e.g., clients with payment difficulties and all other cases) and identify the top correlations for each segmented data using Excel functions.

*Hint:* Utilize Excel functions like CORREL to calculate correlation coefficients between variables and the target variable within each segment. Rank the correlations to identify the top indicators of loan default for each scenario.

*Graph suggestion:* Create correlation matrices or heatmaps to visualize the correlations between variables within each segment. Highlight the top correlated variables for each scenario using different colors or shading.

**Insights**

- Correlation coefficient is a statistical concept which helps in understanding the strength and direction of a linear relationship between two variables. The correlation coefficient value always liesbetween -1 and +1.
- There are mainly two types of correlations:
  1. Positive correlation : The value of one variable increases lineraly with an increase in another variable. This indicates a similar relation between both the variables. So its correlation coefficient would be positive or 1 in this case.
  2. Negetive correlation : When there is a decrease in the value of one variable with an increase in the value of another variable, in that case, the correlation coefficient would be negetive.
  3. Zero correlation or No correlation :  There is one more situation when there is no specific relation between two variables.

- **CLASS – 0 CORRELATION FOR DIFFERENT SCENARIOS**
 ![image](https://github.com/user-attachments/assets/b449d5ea-547c-469e-b6bf-819bd23d8a60)
 
- **CLASS – 1 CORRELATION FOR DIFFERENT SCENARIOS**
![image](https://github.com/user-attachments/assets/a747a424-a754-4fa6-a822-2b12e7b85e44)

### Conclusion

This project used EDA to understand how customer attributes and loan attributes influence the likelihood of default. From the analysis, loans can be approved for those clients who are senior age group, educated, clients having higher income and whose previous loans have been approved. The approval of loans for the clients having low income, unemployed should be thoroughly monitored for the benefit of the company.Through this analysis we could identify patterns that indicate if a customer will have difficulty paying their installments. This information can be used to make decisions such as denying the loan, reducing the amount of loan, or lending at a higher interest rate to risky applicants. This will help the company to understand the key factors behind loan default so it can make better decisions about loan approval.






