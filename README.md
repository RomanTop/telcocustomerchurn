# Telco Customer Churn Project
"Predict behavior to retain customers. Analyze all relevant customer data and develop focused customer retention programs." [IBM Sample Data Sets]
## Introduction
This is one of the Kaggle Datasets https://www.kaggle.com/blastchar/telco-customer-churn. Each row represents a customer, each column contains customer’s attributes described on the column Metadata.
The data set includes information about:
*	Customers who left within the last month – the column is called Churn.
*	Services that each customer has signed up for – phone, multiple lines, internet, online security, online backup, device protection, tech support, and streaming TV and movies.
*	Customer account information – how long they have been a customer, contract, payment method, paperless billing, monthly charges, and total charges.
*	Demographic info about customers – gender, age range, and if they have partners and dependents.
The goal of the project is to explore this type of models, learn more about the subject and come up with recommendations for customer retention program.
## Preprocessing
After loading data, I checked for duplicated and missing values. There were no duplicated values but the column ‘Total Charges’ had 11 missing rows. It turned out that those rows were for the customers with '0' month of tenure. That means that they are very new customers and have been using provided services for less than 1 month. So, it is too early for them to decide whether to stay with the provider or not and it was clearly seen that the values in column Churn for all of them is 'No'. As a result, the missing values were replaced with ‘0’.
## Exploratory Data Analysis
I started to analyze data with calculations of the churn rate.  The dataset contains 7043 rows which means 7043 customers. The number of customers that stayed with the company (no-churn) is 5174, and the number of customers that left (churn) is 1869. The churn rate is 26.5% which is quite a big number. More than a quarter of customers left the company within last month and taking care of this serious problem should be one of the main priorities in company’s strategy. Looking at the data closely should help with revealing the reasons of customer churn and thus developing retain program. 
Building a pairplots showing distribution of numeric variables for churned and non-churned customers revealed a tendency of the customers with higher monthly charges are more likely to leave the company comparing to the ones with lower monthly charges.
![](https://github.com/RomanTop/telcocustomerchurn/blob/main/Pictures/Numvar_distribution_plots.png)
The individual pairplot ‘Tenure / Monthly charges’

![](https://github.com/RomanTop/telcocustomerchurn/blob/main/Pictures/MonthlyCharges_tenure_churn.png)

Just building tenure distribution plot without dividing customers on non-churned and churned can already tell some facts about customers’ behavior and company itself:
![](https://github.com/RomanTop/telcocustomerchurn/blob/main/Pictures/tenure_distrib.png)
