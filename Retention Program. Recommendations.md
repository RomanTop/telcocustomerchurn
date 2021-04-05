# Retention Program. Recommendations. 
## Introduction
The goal of the project is not only to build a predictive model to identify customers who are likely to churn but also develop a retention program for them.

Although the dataset contains 20 variables describing each customer there is still some information that is not given but can be helpful to develop specific focused retain program. For example, we do not know how many plans exist and what are monthly charges for each of them, what technologies are used for fiber optic Internet service – PON, FTTH, FTTN, etc. Depending on these factors approaches to retain customers may vary. However, it is still possible to provide fairly detailed recommendations to some of company’s departments based on which focused retention programs can be developed.

Recommendations themselves are based on the insights revealed during Exploratory Data Analysis. The correlation plot is a good summarising illustration of what factors (variables) are associated with churn customers:

![](https://github.com/RomanTop/telcocustomerchurn/blob/main/Pictures/Correlation_churn.png)

Variables that are above X axis are subjects to work with during developing retention programs.

## Technical factors. Fiber optic Internet service.
Exploratory analysis disclosed that there are many customers who found fiber optic internet service not satisfying:

![](https://github.com/RomanTop/telcocustomerchurn/blob/main/Pictures/InternetService_churn.png)

Since fiber optic provides the fastest internet connection among other technologies it is clearly showing that the company has technical issues with its fiber optic lines. There are three key factors that can be reasons for customers to be unhappy with this service:
1.	Speed
2.	Service interruptions 
3.	Down time
### Recommendations for the Technical Department:
1.	Check if the speed of internet connection for each customer corresponds with the one specified on their contract. If it does not, then conduct investigation to find out reasons. Possible steps to apply:
1.1.	Check headend active equipment settings. Consider upgrading equipment if needed.
1.2.	Check the signal light levels at a customer’s side. If they below the threshold, test the line to get OTDR (Optical time domain reflectometer) trace to find out insertion loss (IL) along the line. Consider re-splicing fibre at the splice points along the line, where IL is above 0.3 dBm.
1.3.	Get a report about over-congested fibre enclosures along the line where micro bends cause high IL. Consider fixing micro bends of affected fibres or even upgrading enclosure itself if possible.
1.4.	Clean all optical connectors at the headend and a customer side.
2.	Get a report about average number of nonintentional service interruptions (outages) per month.
2.1.	Identify the cause of each outage whether it is at the headend or on the line in the field.
2.2.	Most of outages happen in the field in over-congested fiber enclosures where fibers can get tangled thus create micro bend and break. If fibers in an enclosure cannot be reorganized or an enclosure itself cannot be upgraded, consider putting an enclosure under strict limited access (embargo) to fiber technicians during building new fiber connections or maintenance.
2.3.	Make sure that all maintenance works that entail service interruption are conducted during ‘maintenance window’ only which is 2am-6am and with 2 days notice to all affected customers.
3.	Consider building a backup fiber line for all back-bone routes where possible in order to avoid service interruptions when it is an outage on a primary rout.
4.	When all previous steps are implemented properly it should solve most of the issues with speed, service interruptions and down time. However, still consider having 24/7 on call crew on rotation basis to minimize down time when an outage happens.

## Additional Services.
Additional services are Online Security, Online Backup, Device Protection, Tech Support. Customers who do not have these services are more likely to leave the company. The possible reason is that lack of additional services causes too much of inconvenience to the customers, so they decide to leave.

![](https://github.com/RomanTop/telcocustomerchurn/blob/main/Pictures/Additional%20Servicespng_Page1.png)

### Recommendations for the Sales/Marketing Departments:
1.	While signing a contract with a new customer emphasize benefits of additional services how helpful and useful they can be. Especially explain clearly benefits of Tech Support for senior customers who are not usually familiar with indoor telecommunication and network equipment like a modem and a Wi-Fi router. Sometimes guiding them how to reboot those devices can solve the problem.
2.	Consider revising price-formation for the plans with no additional services. Two opposite approaches can be implemented:
2.1.	If possible consider making monthly charges lower so they are not in high charges group anymore and thus look more reasonable for customers.
2.2.	Combine all additional services in one package and calculate prices for the plans with this package. Make monthly charges for the plans with no additional services lower but in the way that plans with additional services look beneficial and worth paying some extra money. Thus, gently forcing new customers to make choice towards plans with additional services.
3.	New customers who still choose plans with no additional services should be contacted by the company’s representative within first 3 months and receive the offer with the additional services package and clear explanations about its advantage. 
4.	Consider contacting current customers with no additional services and offer them to add those services to their plans providing explicit explanations about acquired benefits.

## Type of contract.
Exploratory Data Analysis showed a big churn rate among customers who have month-to-month type of contract. The possible reason is that this type of contract is the first opportunity for all unsatisfied with company’s services customers to leave the company by simply not prolonging the contract and it is most likely not related to its design or provisions.

![](https://github.com/RomanTop/telcocustomerchurn/blob/main/Pictures/Contract_churn.png)

### Recommendations for the Sales/Marketing Departments:
1.	Consider revising one-year and two-years types of contracts in the way looking them more attractive to the customers. For instance, lowering monthly charges for the same plans comparing to the month-to-month contract and as a result making one- and two-years contracts more beneficial.
2.	Consider developing six-months contract as an intermediate type with implementing of the same idea as in the previous step. 
3.	Those new customers who still choose month-to-month contract should be contacted by the company’s representative within first 3 months and receive the offer to switch to other types of contract with clear explanations of their benefits.

## Paperless Billing.
As it was revealed during Exploratory Analysis paperless billing is associated with high customer churn rate. The possible reason may relate to the way customers receive their invoices. For instance, emails with an invoice get to Spam folder, so customers are not aware about due date and as a result, those of them who do not have an automatic payment set up get penalized for a late payment.

![](https://github.com/RomanTop/telcocustomerchurn/blob/main/Pictures/PaperlessBilling_churn.png)

### Recommendations for the IT Department:
1.	Make sure that billing emails optimized for all common email services like google, yahoo, hotmail etc. and do not get identified as spam. Remind customers to add company’s domain to trusted sources to avoid getting received emails to Spam folder.
2.	Consider having an online account for each customer which provides them possibility to download, collect and archive their statements if it is still not the case.

### Recommendations for the Sales Department:
1.	Dealing with new customers always ask about their preferences regarding type of billing. Especially do not propose paperless billing by default to senior people since most of them do not have much familiarity how to use emails and online accounts. For those senior customers who choose paperless billing make sure they know how it works and provide clear explanations if needed.
2.	Consider contacting current customers who have paperless billing and asking them if they are having any difficulties with their bills. For those of them who are confused and unhappy offer switching to paper bills. 

## Electronic check.
This type of payment is another factor related to churn customers.

![](https://github.com/RomanTop/telcocustomerchurn/blob/main/Pictures/PaymentMethod_churn.png)

Even though electronic check provides some advantages to customers it is still associates with high fraudulent potential and processing errors.
### Recommendations to Accountant department:
1.	Ask for a report from the servicing bank about any fraud activities with customers electronic checks detected. If there were any how they were investigated and what means were applied to make transactions more secure.
2.	Ask for a report from the servicing bank about any processing errors like incorrect withdrawal, double withdrawal etc. and how fast they were detected and reimbursed to the customers.
3.	Based on these two reports make a conclusion if frauds and processing errors are main reasons for customers to be unhappy with electronic check type of payment.
### Recommendations for the Sales Department:
1.	For all types of plans and contracts consider specifying automatic bank transfer or automatic credit card charging as a default type of payment. It will provide more secure and fast transaction and prevent customers being penalized for late payments. 
2.	Still let new customers know about other possible types of payments but switch to them only if customers ask for it.
3.	Consider contacting current customers who pay their bills by electronic check and asking them to switch to any of other possible options.

## Conclusion.
Some of the recommendations above have a preventive nature and affect not only certain groups of customers but company’s operation itself. This is a result of the revealed fact that the company has technical issues with some of its important services like fiber optic lines, paperless billing and electronic check. Preventive measures by themselves should reduce the number of not satisfied customers and subsequently decrease the churn rate. Only after troubleshooting all technical issues and making sure that all services work properly recommendations for the Sales and Marketing department can be implemented.

In order to minimize spending company’s resources and maximize efficiency of retain programs all recommendations to Sales and Marketing Departments that entail contacting customers and making offers should be done with the priority to those customers who were identified by the model as potentially churn customers.

At the same time an approximate cost of implementing retain program to a single customer should be calculated. It would help management to assess trade-off between two opposite intentions:
*	To implement retain programs to a bigger number of customers trying to cover all False Negative customers – those who were identified by the model as no churn, but they will actually leave the company.
*	To save company’s resources by implementing retain programs only to those customers who are really going to leave the company, which is never known 100%.

Understanding this factor and knowing company’s limitations like number of employees who will be involved in conducting retain programs, the allocated budget for implementation of the retain programs, especially for resolving the technical issues as the most expensive but the most important ones, will help the company to reach its goal to reduce the churn rate to an acceptable level.
