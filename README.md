#### **Cahaya Tambunan**

# **Travel Insurance Claim Prediction**
## A. Business Understanding
### Context
Travel insurance is a product typically purchased by customers prior to a trip to cover potential risks like cancellations, medical emergencies, or other incidents that may arise during travel. Unlike other types of insurance, travel insurance is usually a one-time purchase and does not require ongoing monthly payments. This creates a unique challenge for the insurance company, as the financial impact of claims can be significant, and the company has limited opportunities to recover costs through future payments. A company engaged in travel insurance wants to predict which policyholders will submit an insurance claim for travel coverage. Policyholder data includes information such as destination, travel insurance products, and historical data regarding claims. The ability to predict claim submissions can help the company better manage risk, allocate resources efficiently, and improve overall profitability.

Target:

0 : No claim submitted

1 : Claim submitted
### Problem Statement
The primary problem faced by the travel insurance company is accurately predicting which customers are likely to file claims. Misclassifying customers can lead to either increased operational costs (in the case of false positives) or substantial financial losses (in the case of false negatives). The company needs a robust model to minimize incorrect predictions, as both false positives and false negatives can have serious financial consequences.
### Goals
The company seeks to predict the likelihood of a customer filing a claim after purchasing a travel insurance policy. This would help them allocate resources efficiently, adjust premiums based on risk factors, and develop strategies to reduce claim submissions.

Additionally, the company wants to understand what factors drive customers to submit claims, allowing them to refine their offerings and provide better customer service while managing risk.
### Analytic Approach:
We will analyze the data to identify patterns that distinguish customers who submit claims from those who do not. Then, we will build a classification model to predict the likelihood of a policyholder submitting a claim, allowing the company to focus on high-risk customers for better risk management.
### Metric Evaluation:

We will focus on the following errors:

* Type 1 Error (False Positive):

    Predicting a customer will submit a claim when they will not.
    - Consequence: Losing profit, since the customer won't buy the one-time purchase insurance.

* Type 2 Error (False Negative):

    Predicting a customer will not submit a claim when they will.
    - Consequence: Unprepared for claim submissions, leading to financial strain.

The main metric for evaluation will be F1-Score as it balances both precision and recall, ensuring that the model minimizes both false positives and false negatives while capturing true risks efficiently.

## B. Data Understanding
The dataset contains information about policyholders from a third-party travel insurance service company based in Singapore. 
Online Access: https://www.kaggle.com/datasets/mhdzahier/travel-insurance.
Here's Dataset's attribute informaton:

| Attribute               | Data Type         | Description                                           |
|-------------------------|-------------------|-------------------------------------------------------|
| Agency                  | Text              | The agency offering the insurance policy              |
| Agency Type             | Text              | Type of agency (e.g., Airlines, Travel Agency)        |
| Distribution Channel    | Text              | The method used for distributing the policy (Online)  |
| Product Name            | Text              | The name of the insurance product                     |
| Gender                  | Text              | Gender of the customer (M = Male, F = Female)         |
| Duration                | Integer           | Duration of the policy in days                        |
| Destination             | Text              | The destination where the policyholder is traveling   |
| Net Sales               | Float             | Total sales amount for the policy                     |
| Commision (in value)    | Float             | The commission earned for the policy sale             |
| Age                     | Integer           | Age of the policyholder                               |
| Claim                   | Text              | Whether a claim was made (Yes/No)                     |


## G. Conclusion and Recomendation
print('Classification Report Best_Model: \n')
print(classification_report(y_test, y_pred_after))
There is no available source that specifies the exact cost incurred by a company for each claim made by policyholders, making it difficult to accurately illustrate potential financial losses. However, based on information found in (link), policyholders indirectly pay a certain percentage of their ticket price as insurance. This implies that policyholders only pay the premium when they travel, rather than having a mandatory monthly fee.

As a result, when the company fails to predict claims correctly, two types of errors can occur:

### Type 1 Error (False Positive):
- **Condition**: The model predicts that a claim will happen, but in reality, it will not.
- **Impact**: The company may offer higher-priced coverage or even decline to offer coverage in an attempt to avoid potential claim costs. This can lead to the policyholder deciding not to purchase the insurance, causing the company to lose potential profit.
  
### Type 2 Error (False Negative):
- **Condition**: The model predicts that no claim will occur, but a claim does happen.
- **Impact**: The company is unprepared with the necessary resources to handle the claim. This can result in significant financial losses, as the company is caught off guard and must cover unexpected claim costs.

### Conclusion:
The most suitable metric for evaluating the model in this context is the **F1 Score**, which balances **precision** and **recall**. This ensures that both **Type 1** and **Type 2 errors** are minimized, as it combines the need for accuracy in identifying true claims (precision) and the ability to capture all possible claims (recall).
* by Machine Learning, we got an F1 score of 0.96 for both classes, this model is highly balanced and suitable for scenarios where both claim predictions and non-claim predictions are important, such as in travel insurance, where missing a claim or predicting too many false claims could have significant financial impacts.
* 
### Recommendation: 
* Enrich the dataset by collecting more contextual and behavioral information about policyholders.
* Specify costs and coverage more detail. This will make it easier to take targeted actions to optimize the claim prediction model and reduce financial losses.
