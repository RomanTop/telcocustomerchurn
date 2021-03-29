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

We see two distinct spikes at the end of the charts. The spike on the left tells that there is a relatively big number of new customers 0-4 months meaning that company has a good ability to attract new customers. It looks like that marketing and sales departments of the company are working well. However, a big number of those new customers will leave the company during next months. In an ideal situation when there is no churn, tenure distribution chart should have a spike only at its right end, meaning that over the time number of customers is building up at the very end of the analyzed period. In our situation the spike at the right end tells that there are always customers who keep their loyalty since company was capable to satisfy them with the service all this time. 

Customer tenure Distribution Churn vs No Churn is showing it even clearer:

![](https://github.com/RomanTop/telcocustomerchurn/blob/main/Pictures/tenure_distrib_churn.png)

Number of churned customers is significantly bigger than no churn for the first 20 months, but the peak of churn is at 0–4-month period and then number of churned customers decreasing over the time. That means that the company has no time for analyzing customers’ behavior and should act right away to retain clients because otherwise most of them will leave even after the first month. So, when a customer joins the company, we should be able to assess his/her risk of churn immediately. And we hope that the set of parameters (variables) that describe each customer will help us to identify patterns which lead customers to churn.

Let us go back to the parameter we already touched Monthly Charges and take a closer look at it. So far, we know that the customers with higher charges are more likely to churn. Here is the distribution of monthly charges:

![](https://github.com/RomanTop/telcocustomerchurn/blob/main/Pictures/MonthlyCharges_distrib.png)

Looking at this chart we can visually combine customers into three groups. The low charges - 20-30$ per month, moderate charges – 40-60$ per month and high charges – 70-110$ per month. With regards to churn vs no churn monthly charges distribution is as follows:

![](https://github.com/RomanTop/telcocustomerchurn/blob/main/Pictures/MonthlyCharges_distrib_churn.png)

The lowest number of churn customer is in the low monthly charges group, the highest number of churn customer is in the high monthly charges group. The moderate monthly charges group has roughly equal number of churned and no churned customers. So, a new customer that chose the plan with high monthly charges should fall into company’s highest attention priority. Because we can see that the high monthly charge group is the biggest group thus brining the company most of its earnings, but it is also the group with highest risk of customers to churn which means the company is losing good chunk of its revenue.

### Demographic
Demographic charts are showing no dependency on gender between churn and no churn groups of customers. However, we can see that customers who do not have partners and no dependents have as twice as big probability to churn comparing to those who have partners and dependents. Another interesting fact is showing the chart dividing customers by seniority parameter. Even though the percentage of senior customers is relatively small only 16.3% a little bit less than a half of them are churned customers. So, company should pay closer attention to single customers with no kids or any other dependents and to senior customers. There must be something about these groups of customers that puts them into higher risk to leave the company.

![](https://github.com/RomanTop/telcocustomerchurn/blob/main/Pictures/Demographicpng_Page1.png)

### Services
Looking at the group of charts representing churned and no churned customers with regards to services we can see the following picture: 

![](https://github.com/RomanTop/telcocustomerchurn/blob/main/Pictures/Servicespng_Page1.png)

There is no dependency on whether customer has or does not phone service and multiple lines. The number of churned customers in those groups is roughly ¼ which is the overall churn rate we figured out earlier.

The charts showing groups of customers with regards to types of internet service is revealing the fact that the customers who have fiber optic internet service have way higher churn rate ~40% comparing to DSL internet service – 18% and no internet service – 7%. So, the customers with fiber optic internet are going to be another subgroup that should be in company’s attention focus. The second chart showing distribution of monthly charges with regards to type of internet revealing that fiber optic is the service that associates with high monthly charges only, while DSL internet covers broad range of charges from the lowest to mid-high charges. ‘No internet service’ group associates only with the lowest charges.

### Additional Services
The group of charts dividing customers depending on additional services they chose to have or not to:

![](https://github.com/RomanTop/telcocustomerchurn/blob/main/Pictures/Additional%20Servicespng_Page1.png)

It is clearly seen that customers who chose not to have additional services have a drastically higher churn rate comparing to those ones who have them - 40% vs 15-20%. Here is another group of customers for the company to work with. The situation itself might look counterintuitive at first glance. Customers with additional services apparently have higher monthly charges but we already figured out that the customers with high monthly charges have higher churn rate. Explanation could be that the difference in monthly charges between customers with additional services and without them is not that significant but customers without additional services still fall into high monthly charges group. Lack of additional quite useful services like tech support, online security etc. cause inconvenience and issues for customers and make them think that service they have from the company not worth money they pay.

The distribution of monthly charges of churned customers without additional services chart is showing that customers from this group are in each subgroup in terms of monthly charges we defined earlier – low, moderate and high:

![](https://github.com/RomanTop/telcocustomerchurn/blob/main/Pictures/MonthlyCharges_no_additional_services_distrib.png)

Most of this type of customers is in the high monthly charges group. Why customers who do not have additional services are still paying high monthly charges? Obviously there must be other parameters that effect monthly payments and not represented in our dataset. For example, speed of Internet. Choosing higher Internet speed and no additional services may not be that beneficial.
The only additional services that do not affect the churn rate are Streaming TV and Streaming movies. Regardless of them the churn rates both subgroups are roughly the same:

![](https://github.com/RomanTop/telcocustomerchurn/blob/main/Pictures/Streamingpng_Page1.png)

The other thing about all charts showing churn of customers with regards to additional services are customers with no internet service. Only 1.6% of all customers are churned customers who have no internet service. It cannot be compared to churn rates of any other subgroup of customers who have internet service. It leads to conclusion that the quality of internet service overall is not satisfying enough.

### Type of contract
The charts showing churned vs no churned customers depending on type of contract:

![](https://github.com/RomanTop/telcocustomerchurn/blob/main/Pictures/Contract_churn.png)

![](https://github.com/RomanTop/telcocustomerchurn/blob/main/Pictures/Contractpng_Page1.png)

We see that most of churned customers 23.5% (26.6% overall churn rate) have a month-to month type of contract. Moreover, more than a half (55%) of all customers have this type of contract. This is another especially important factor for the company to work with. It looks like one-year and two-year types of contracts keep customers from leaving whereas a month-to-month contract provides a convenient opportunity for almost all not satisfied customers to not prolong their contract for the next month and leave. However, it is highly unlikely that month-to-month type of contract by itself, the way it is designed, causes churn of customers. More important is to figure out what are the reasons behind it that force customers to use this easy opportunity to leave.

### Billing and Payment method
Another subgroup of customers that requires closer attention is those who receive paperless billing:

![](https://github.com/RomanTop/telcocustomerchurn/blob/main/Pictures/PaperlessBilling_churn.png)

The churn rate of this group is almost triple as big as customers receiving their bills in paper.

Let us look to the last parameter – payment method:

![](https://github.com/RomanTop/telcocustomerchurn/blob/main/Pictures/PaymentMethod_churn.png)

![](https://github.com/RomanTop/telcocustomerchurn/blob/main/Pictures/MonthlyCharges_PaymentMethod_churn.png)

‘Electronic check’ group has 4 times bigger churn rate comparing to other groups. The second chart is showing that electronic check is not associated with high monthly charges by itself since we can see it covers all range from the lowest to the highest charges. Nevertheless, we do see a ’bubble’ at high monthly charges area. That likely means that customers who chose electronic check method of payment also tend to have services associated with higher charges like Fiber optic internet service. Anyway, what the issues are with ‘Electronic check’ method of payment is a subject of thorough investigation.

### Senior citizens
Let us go back to demographic groups. Earlier it was figured out that Senior customers is a group with churn rate ~40% which is 1.5 times higher than the overall churn rate. Let us select senior customers only from the dataset and look at all parameters:

#### Tenure and monthly charges

![](https://github.com/RomanTop/telcocustomerchurn/blob/main/Pictures/Senior%20tenure%20and%20chargespng_Page1.png)

#### Services

![](https://github.com/RomanTop/telcocustomerchurn/blob/main/Pictures/Senior_InternetService.png)

![](https://github.com/RomanTop/telcocustomerchurn/blob/main/Pictures/Senior%20servicespng_Page1.png)

#### Additional Services

![](https://github.com/RomanTop/telcocustomerchurn/blob/main/Pictures/Senior%20Additional%20Servicespng_Page1.png)

#### Streaming Services
![](https://github.com/RomanTop/telcocustomerchurn/blob/main/Pictures/Senior%20Streaming%20Servicespng_Page1.png)

#### Type of Contract

![](https://github.com/RomanTop/telcocustomerchurn/blob/main/Pictures/Senior_Contract.png)

#### Billing and Payment method
![](https://github.com/RomanTop/telcocustomerchurn/blob/main/Pictures/Senior%20Billing%20and%20Payment%20methodpng_Page1.png)

We see all the same trends as we saw earlier regardless demographic groups but now we can see that some subgroups of senior customers like ‘Month-to-month contract’, ‘Electronic check’ and some others have churn rate over 50% which is twice higher than overall churn rate. It explains high churn rate in Senior customers demographic group in total.
