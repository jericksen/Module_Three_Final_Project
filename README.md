# Module Three Final Project

For: Amazon Inc.

By: Jonathan E Ericksen, JE Consulting

## Background
> Amazon, with it's busy agenda and lackluster talent inside their data science teams, has decided to contract externally with JE Consulting to help develop a classification model. The intent for this model is to predict a shoppers propensity to make a purchase during a shopping session using real time user analytics. Amazon intends to use this model to determine when to offer last minute discounts on products within their in an attempt to entice shoppers who are not exhibiting characteristics of purchasing products to reverse course and make a purchase. 

## Objective:
> The objective for JE Consultants is to fit the best model possible with the provided data. The resulting model will in turn be nested in the backend of Amazon's ecommerce site and used to make decisions on whether or not to trigger pre-constructed promotions for differing products. Should the model determine a current shopper is showing no propensity of making a purchase, Amazon will trigger a promotional offering to entice a transaction.

> Further, Amazon Inc. has asked JE Consulting to produce a cost/benefit analysis with adjustable monetary parameters which calculates the net effect of the resulting models prediction on the provided training set.

## Question:
> Is the implementation of a machine learning classifier which predicts a shoppers propensity to transact during a shopping session advantageous with respect to revenue maximization? 

## Methodology:

> This project loosely follows the industry standard OSEMiN process. The 5 stages in OSEMiN are outlined in the table of contents below with each stage highlighted within the ensuing notebook.

## Table of Contents:<a id='top'></a>
> #### [Obtain](#obtain): 
- Sourcing the data
- Importing data

> #### [Explore](#explore): 
- Data preprocessing, cleaning & wrangling
- Predictive feature visuals
- Data set balance analysis

> #### [Condition](#condition):
- Addressing collinearity
- Feature scaling
- Target and feature separation

> #### [Model](#model):
- Initial Model
- Initial Model Interpretation & Notes
- Data Rebalancing
- Feature engineering
- Hyperparameter tuning
- Initial Cost Benefit analysis
- Model iterations
- Final model

> *(non- OSEMiN additions)*
- **[Cost Benefit Analysis](#costbenefitanalysis)**
- **[Conclusions](#conclusion)**
    - Answer to our business question
- **[Recommendations](#recommendation)**
- **[Future Work](#futurework)**

## Recommendations <a id='recommendation'></a>

[Back to top](#top)

In order to satisfy our quest to boost conversion rates of online shoppers, we need to ensure the business assumptions within the cost/benefit analysis accurately reflect reality. Thus, further business analysis should be done to 

Further, much work is needed to flush out the implementation of our model with Amazon's software developers. Careful consideration is needed with respect to user experience as discount offers are provided to shoppers in an effort to entice transactions. Visitors must not feel spied upon when offers are given to entice a purchase. Implementing a respectful experience is a key component to fulfilling the conversion and revenue objectives.

## Future Work <a id='futurework'></a>

[Back to top](#top)

Recommendations for future work: 

- Extract further user data from shopping sessions to further improve our model's overall predictive power. Additional suggesed dimensions:
    - Visitor location based on IP address
    - Visitor zipcodes
    - Visitor purchase history, i.e., has this user made purchases in the past X number of days, weeks, months
    - Visitor login history
    - Visitor age
    
- Iterate through various thresholds by which our model bases it's classifications. Further improvements can be made to optimize our cost/benefit to the business by tweaking our thresholds.

- Run other classification algorithms and compare the results to our existing model. Decision Trees, Random Forests, and Support Vector Machines are a few other classifiers to conider testing. 
    
