# telemarketing-ai-improvements
The data is from a Portuguese banking institution and is a collection of the results of multiple marketing campign .  goal is to compare the performance of the classifiers (k-nearest neighbors, logistic regression, decision trees, and support vector machines) you encountered in this section of the program. 

# Using Classification Models to Improve Telemarketing Strategies
Business Context
A Portuguese banking institution was conducting a telemarketing campaign to solicit new business for its Term Deposit products. The marketing campaigns were based on phone calls. Often, more than one contact to the same client was required.

# Research Objectives
The institution compiled over 40,000 records encompassing a wide array of attributes, including demographic information, details of previous customer interactions, and macroeconomic indicators. This exploratory data analysis and research aims to leverage the information to improve the bank's telemarketing strategies for promoting Term Deposit products.

# Data Source
The data is obtained from the work of Moro, S., Rita, P., and Cortez, P. (2012). Bank Marketing. UCI Machine Learning Repository. https://doi.org/10.24432/C5K306. "The data is related to direct marketing campaigns of a Portuguese banking institution."

## Data Dictionary
 Bank client data:
 age (numeric)
 job: type of job (categorical: "admin.", "blue-collar", "entrepreneur", "housemaid", "management", "retired", "self-employed", "services", "student", "technician", 
 "unemployed", "unknown")
  marital: marital status (categorical: "divorced", "married", "single", "unknown"; note: "divorced" means divorced or widowed)
  education (categorical: "basic.4y", "basic.6y", "basic.9y", "high.school", "illiterate", "professional.course", "university.degree", "unknown")
  default: has credit in default? (categorical: "no", "yes", "unknown")
  housing: has housing loan? (categorical: "no", "yes", "unknown")
  loan: has personal loan? (categorical: "no", "yes", "unknown")
 ## Related to the last contact of the current campaign:
  contact: contact communication type (categorical: "cellular", "telephone")
  month: last contact month of year (categorical: "jan", "feb", "mar", ..., "nov", "dec")
  day_of_week: last contact day of the week (categorical: "mon", "tue", "wed", "thu", "fri")
  duration: last contact duration, in seconds (numeric). Important note: this attribute highly affects the output target (e.g., if duration=0 then y="no"). Yet, the duration is not known before a call is performed. Also, after the end of the call y is obviously known. Thus, this input should only be included for benchmark purposes and should be discarded if the intention is to have a realistic predictive model.
  ### Other attributes:
  campaign: number of contacts performed during this campaign and for this client (numeric, includes last contact)
  pdays: number of days that passed by after the client was last contacted from a previous campaign (numeric; 999 means client was not previously contacted)
  previous: number of contacts performed before this campaign and for this client (numeric)
  poutcome: outcome of the previous marketing campaign (categorical: "failure", "nonexistent", "success")
 ### Social and economic context attributes
  emp.var.rate: employment variation rate - quarterly indicator (numeric)
  cons.price.idx: consumer price index - monthly indicator (numeric)
  cons.conf.idx: consumer confidence index - monthly indicator (numeric)
  euribor3m: EURIBOR 3 month rate - daily indicator (numeric)
  nr.employed: number of employees - quarterly indicator (numeric)
  Output variable (desired target): y ("yes", "no")
## Exploratory Data Analysis
 ### Data Quality and Missing Value Treatments:
The dataset contains 41,188 records with 20 attributes and one outcome variable - whether a customer subscribes to a term deposit product. The data quality is generally good with some issues. Here are the highlights:

    There are no duplicates.
    Missing values are observed in several attributes. 26% of the records have at least one missing value in the record. In most cases, missing values are indicated by the 
    term "unknown" as the value in the database.
    One data integrity issue was discovered and these 4,110 (10% of total) records are excluded from the dataset to ensure the reliability of the analysis.
  ### Missing values treatments
In most cases, missing values are indicated by the term "unknown" as the value in the database. Records with missing values are kept. The term 'unknown' is preserved as a categorical value to build the models so that models can process these incomplete records and predict their likely outcomes.
