# telco-customer-churn-ann

This notebook applies Artificial Neural Networks (ANN) to customer churn data of a telecommunication service provider.

## About the Data
The Telco customer churn data contains information about a fictional telco company that provided home phone and Internet services to 7043 customers in California in Q3. It indicates which customers have left, stayed, or signed up for their service. Multiple important demographics are included for each customer, as well as a Satisfaction Score, Churn Score

CustomerID: A unique ID that identifies each customer

Gender: The customer’s gender: Male, Female

Senior Citizen: Indicates if the customer is 65 or older: Yes, No

Dependents: Indicates if the customer lives with any dependents: Yes, No. Dependents could be children, parents, grandparents, etc.

Tenure in Months: Indicates the total amount of months that the customer has been with the company by the end of the quarter specified above.

Phone Service: Indicates if the customer subscribes to home phone service with the company: Yes, No

Multiple Lines: Indicates if the customer subscribes to multiple telephone lines with the company: Yes, No

Internet Service: Indicates if the customer subscribes to Internet service with the company: No, DSL, Fiber Optic, Cable.

Online Security: Indicates if the customer subscribes to an additional online security service provided by the company: Yes, No

Online Backup: Indicates if the customer subscribes to an additional online backup service provided by the company: Yes, No

Device Protection Plan: Indicates if the customer subscribes to an additional device protection plan for their Internet equipment provided by the company: Yes, No

Tech Support: Indicates if the customer subscribes to an additional technical support plan from the company with reduced wait times: Yes, No

Streaming TV: Indicates if the customer uses their Internet service to stream television programing from a third party provider: Yes, No. The company does not charge an additional fee for this service.

Streaming Movies: Indicates if the customer uses their Internet service to stream movies from a third party provider: Yes, No. The company does not charge an additional fee for this service.

Streaming Music: Indicates if the customer uses their Internet service to stream music from a third party provider: Yes, No. The company does not charge an additional fee for this service.

Contract: Indicates the customer’s current contract type: Month-to-Month, One Year, Two Year.

Paperless Billing: Indicates if the customer has chosen paperless billing: Yes, No

Payment Method: Indicates how the customer pays their bill: Bank Withdrawal, Credit Card, Mailed Check

Monthly Charge: Indicates the customer’s current total monthly charge for all their services from the company.

Total Charges: Indicates the customer’s total charges, calculated to the end of the quarter specified above.

Churn: Yes = the customer left the company this quarter. No = the customer remained with the company. Directly related to Churn Value.
Data was obtained from Kaggle: https://www.kaggle.com/datasets/blastchar/telco-customer-churn

## Data Cleaning
The data was cleaned and processed for modelling by removing irrelevant columns, removing rows with null data because the dataset is large to accomodate that, and converting object column to numeric.
![image](https://github.com/user-attachments/assets/30d1510d-6a93-48cb-806b-1020f22c2b50)

Further exploration of the data showed that customers that have been with the company longer were less likely to leave. 
![image](https://github.com/user-attachments/assets/86ec1a96-e2b3-43c1-9baf-a42494fdca46)

Also, customers that payed less monthly charges were less likely to leave.
![image](https://github.com/user-attachments/assets/d139f9c6-7d41-4241-8f62-fb0f46b3b68d)

The data was encoded and standardized to make it suitable for machine learning. An Artificial Neural Network was developed to ingest the data and for prediction. The evaluation of model showed that it was 75% accurate in predicting whether a client would leave or not.

Some imbalance was noticed in the data, there were more staying customers than leaving customers, this could lead to errors in the prediction.
To resolve this, 3 approaches were implemented
- Underfitting: reducing the same number of majority class (staying customers) to match minority class (leaving customers) to balance the class distribution.
- Overfitting:  increasing the same number of minority class to match majority class to balance the class distribution,
- SMOTE (Synthetic Minority Over-sampling Technique): generating synthetic samples for the minority class to balance the class distribution.

Underfitting and SMOTE led to a decrease in accuracy but created a balance in the classes for other metrics namely precision, recall, and f1-score. 
Undersampling and Oversampling improved the precision, recall, and f1-score of the model especially for predicting whether the customer left (1). The metrics reduced for whether the customer stayed (0).

The full notebook is available here:

