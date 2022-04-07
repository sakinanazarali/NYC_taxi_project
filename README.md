A project that analyses the tipping behaviour of passengers in NYC. The analysis is divided into the following parts: 

1) Data Cleaning (includes data for April-June 2019 and April-June 2020)
2) Establish the variables that significantly impact tipping behaviour using the Ordinary Least Squares (OLS) regression method, therefore, "best-fitting" the data. Select the model with the highest adjusted R2 and lowest AIC.
3) Test the same models from OLS into LOGIT. Finest model in OLS is not the finest one in LOGIT (makes variable selection difficult). 
4) Utilize stepwise regression to find the best model by feeding it with "kitchensink" variables. 
5) Create a model on LOGIT that uses variables that were pruned with stepwise regression. 
6) Use the 2019 trained LOGIT model to predict on the 2019 test dataset (80% trained data, 20% test data) - 49% accuracy
7) Create a CART model that uses the 2019 trained model to predict on the 2019 test dataset. - 72% accuracy
8) Create a CART model that uses the 2019 trained model to predict on the 2020 dataset. This is mainly to assess for the impact of COVID-19 on tipping behaviour - 67% accuracy
9) Create a CART model that uses the 2020 trained model to predict on the 2020 test dataset. This is mainly to assess for the splits between the branches in the 2019 CART model vs that of the 2020 CART model.
10) Validate CART models using a manual K-Fold Regression:
    - Test the 2019 model with a newly sampled 80/20 trained dataset 
    - Test the 2019 model with a newly sampled 70/30 trained dataset
    - Test the 2019 model without the defining variable (VendorID) to assess how much impact is felt with its absence
    - Test the 2019 model whilst making the defining variable (VendorID) the dependent variable to assess how much of the variance in independent variables it can capture

<img width="589" alt="Screenshot 2022-03-30 at 16 28 51" src="https://user-images.githubusercontent.com/98000420/162144184-d2395242-3d5c-4e9f-b251-0195299bde9c.png">
