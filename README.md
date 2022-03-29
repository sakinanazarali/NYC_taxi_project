A project that analyses the tipping behaviour of passengers in NYC. The analysis is divided into the following parts: 

1) Data Cleaning (includes data for April-June 2019 and April-June 2020)
2) Establish the variables that significantly impact tipping behaviour using the Ordinary Least Squares (OLS) regression method, therefore, "best-fitting" the data
3) Create a model on LOGIT that uses variables that were pruned with OLS. Use the 2019 trained LOGIT model to predict on the 2019 test dataset (80% trained data, 20% test data)
4) Utilize stepwise regression to find the best model by feeding it with "kitchensink" variables. The model establishes the same variables established earlier, through OLS and LOGIT.
5) Create a CART model that uses the 2019 trained model to predict on the 2019 test dataset. 
6) Create a CART model that uses the 2019 trained model to predict on the 2020 dataset. This is mainly to assess for the impact of COVID-19 on tipping behaviour.
7) Create a CART model that uses the 2020 trained model to predict on the 2020 test dataset. This is mainly to assess for the splits between the branches in the 2019 CART model vs that of the 2020 CART model.
