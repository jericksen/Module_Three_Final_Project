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

### Cost Benefit: Financial Implications

Before moving on with further model iterations, we'll take a step back and assess the financial implications for our logistic regression predictions with respect to the use case at Amazon Inc. Each model prediction will have an impact on Amazon's revenue. Let's break down the financial impact of these predictions:

- *True Negative:* **Cost** = ~125 dollars
    - Amazon will lose out on 125 dollars of revenue if a shopper does not make a purchase and is not offered the 10 percent discount.
- *False Positive:* **Cost** = ~137.5 dollars
    - Amazon will lose ~112.5 dollars in lost revenue if our model predicts a shopper will transact, but instead they do not. In this case, the model will instruct the website not to offer a 10 percent discount, thus lost opportunity to entice revenue from a potential sale is: 125 - discount of 12.5 = -112.5 dollars
    - Further, we'll factor in an additional revenue penalty that accounts for the portion of first time shoppers that do not transact. In this scenario, first time shoppers will not experience the seamless experience of shopping at Amazon and will be less likely to be repeat shoppers. This additional revenue penalty will equal 25 dollars in lost potential future revenue.
- *False Negative:* **Benefit** = ~112.5 dollars
    - Amazon will earn ~112.5 dollars in revenue if the model predicts a shopper will not transact, thus a 10 percent discount is offered, and the shopper makes the purchase: 125 - 12.5 percent discount = 112.5 dollars. 
- *True Positive:* **Benefit** = 200 dollars
     - Amazon will earn 125 dollars in revenue if our model correctly predicts a shoppers propensity to transact, thus no offer is made.
     - Further, additional revenue has been added to account for repeat shoppers. Visitors who experience shopping at Amazon are inclined to be repeat shoppers. Thus, additional revenue benefit of 75 dollars has been factored in.
     
*Key Assumptions:*
- *Figures are based on one shopping session*
- *Avg. shopping session purchase = ~125 dollars*
- *Avg. discount to entice shoppers to transact = ~10 percent*


**Target Metric: Precision**
- Based upon the financial impact analysis above, it's important going forward to build a model that limits Type I errors. Thus, we want a model that reflects high precision which limits the costs associated with false positive predictions. 

With these figures in mind, let's assign the appropriate cost/benefit revenue figures for each of the predictions our ensuing model iterations will produce:

All of the models above perform decently well with respect to their precision scores. Notably, this is an improvement of roughly 15-18 percent above our baseline model. 

### Final Model

**Cost/Benefit:**

- Model 3 returned the 2nd best revenue benefit of all four iterations. 

**Precision**

- Model 3 also returned the 2nd best precision score with the 2nd least number of Type I errors. 

**Conclusion:** 

- Based on the consistency of model 3 in terms of performance, we'll choose this model for implementation within Amazon's website. The other 3 models performed well in one area or another, but none were as consistant as Model 3. 

## Cost Benefit Analysis Result <a id='costbenefitanalysis'></a>
With a net benefit of ~26.71 dollars per average shopping session, the implementation of Model 3 would yield a total revenue benefit of 320,520 dollars over the next 12,000 shopping sessions.

## Conclusion <a id='conclusion'></a>
We've optimized the parameters and data to limit Type I errors and thus increasing the precision of our model and net revenue benefit.

**Question:** Given our analysis and logistic regression classifier, would the implementation of a classifier be advantageous with respect to revenue optimization? 

**Answer:** Yes. With the implementation of our model, Amazon can expect to see 320,520 dollars of additional revenue per the next 12,000 shopping sessions.

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
    
