A project that attempts to answer the following question: "What variables impact tipping behaviour in NYC Taxi Trips, and, how was it changed since COVID-19?" 

**Initial Hypotheses:**

1) Drop offs or pick ups to/from posh areas of NYC would have higher tips amounts
2) COVID-19 would negatively impact tip amounts
3) Longer trips, both in terms of distance and time would receive higher tip amounts
4) Weekend trips will earn higher tips per trip than weekday trips

**The analysis is divided into the following parts:**

1) Data Cleaning (includes data for April-June 2019 and April-June 2020)
2) Establish the variables that significantly impact tipping behaviour using the Ordinary Least Squares (OLS) regression method, therefore, "best-fitting" the data. Select the model with the highest adjusted R2 and lowest AIC.
3) Test the same models from OLS into LOGIT. Finest model in OLS is not the finest one in LOGIT (makes variable selection difficult). 
4) Utilize stepwise regression to find the best model by feeding it with "kitchensink" variables. 
5) Create a model on LOGIT that uses variables that were pruned with stepwise regression. 
6) Use the 2019 trained LOGIT model to predict on the 2019 test dataset (80% trained data, 20% test data) - 49% accuracy
7) Create a CART model that uses the 2019 trained model to predict on the 2019 test dataset. - 72% accuracy
8) Create a CART model that uses the 2019 trained model to predict on the 2020 dataset. This is mainly to assess for the impact of COVID-19 on tipping behaviour - 67% accuracy
9) Create a CART model that uses the 2020 trained model to predict on the 2020 test dataset. This is mainly to assess for the splits between the branches in the 2019 CART model vs that of the 2020 CART model.
10) Validate CART models using a manual K-Fold Validation:
    - Test the 2019 model with a newly sampled 80/20 trained dataset 
    - Test the 2019 model with a newly sampled 70/30 trained dataset
    - Test the 2019 model without the defining variable (VendorID) to assess how much impact is felt with its absence
    - Test the 2019 model whilst making the defining variable (VendorID) the dependent variable to assess how much of the variance in independent variables it can capture

<img width="415" alt="Screenshot 2022-04-07 at 00 29 44" src="https://user-images.githubusercontent.com/98000420/162144461-af0e7ec2-74f0-4a77-abad-99f840fcc40e.png">
<img width="563" alt="Screenshot 2022-04-07 at 00 29 52" src="https://user-images.githubusercontent.com/98000420/162144481-9e18c258-a80d-4cc8-8b32-0c0baf685f0c.png">

**Findings:**

1) VendorID: the most differentiating variable for high tip/low trip tips
2) Taxi drivers earn higher tips between 8PM and 12AM
3) COVID-19 increased tipping amounts per trip (on average)
4) Pick up and drop off locations did not have a significant impact on tip variances 
5) Total amount (charged to customers) were more significant in impacting tip amounts than the impact that trip distances or trip times had on tip amounts
6) The day of the week did not have a signficant impact on tipping behaviour
7) Acknowledging that other factors (such as conversation quality, luxury factors) were not accounted for in the data
