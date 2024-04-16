# Used Car Price
This is a practical use-case application for developing Linear Regression model skills.  

## What drives the price of a car?

**Context**

The provided dataset contains information on 426K cars to ensure speed of processing. The goal is to understand what factors make a car more or less expensive. As a result of the analysis, we should provide clear recommendations to your client -- a used car dealership -- as to what consumers value in a used car

**Code**

- Refer to [prompt_II.ipynb](https://github.com/tombharath/used-car-price-ml-ai-bk/blob/main/prompt_II.ipynb) jupyter notebook for the code.
- The code uses Plotly express libraries. As GitHub doesn't display plotly chart correctly. The renderer is used to show it as a picture.
- You can change the fig.show("png") to fig.show() in the jupyter notebook python code to have the hover functionality while running it.

**Business Understanding**

- The used car dealership is interested in recommendations of what customers value in a used car.
- The goal is to identify what features impact the car price from the given Dataset of information on 426K cars.
- To identify the features we select the regression model to predict the price and which features have the highest coefficient for the price prediction.

**Data Understanding**

- Describe the data description
- Check the summary of the data to understand the categorical and numeric features in the data set
![Screenshot 2024-04-15 at 9 10 03 PM](https://github.com/tombharath/used-car-price-ml-ai-bk/assets/37302704/19b76d29-ccfb-4008-9345-503dbb66a786)

**Data Preparation**

- The VIN and ID column can be dropped as it is not going to have an impact on the Price.
- Identify and remove the duplicates
- Impute the missing field values.
- Dropped the missing value for price as the model needs to learn the price

**Data Preprocessing**
- Identify the Categorical fields either ordinal or nominal
- Converting Ordinal Categorical Column condition, cylinders, and title_status to Numeric using  Ordinal Encoder
- Converting the rest of the nominal Categorical Column to Numeric Using Mean Encoder
- Removed the price outliers.
- Convert the high numerical values like price to a logarithmic scale

![Screenshot 2024-04-15 at 9 21 22 PM](https://github.com/tombharath/used-car-price-ml-ai-bk/assets/37302704/86f9b2a7-1140-4120-86c6-af0a1d720847)

- Correlation of heat map against each feature

![Screenshot 2024-04-15 at 9 22 42 PM](https://github.com/tombharath/used-car-price-ml-ai-bk/assets/37302704/cc83b954-90bd-4928-b548-10614f8419cf)

**Modelling**

- Used LinearRegression, Ridge and Lasso Modeling
- Used Regularization technique over the Feature Selection to consider all the features.
- GridsearchCV to find the optimal hyperparameters
- Used Mean Square error to check for the best model. Since the data is normalized and scaled and it is the same price prediction against different models MSE is used over R2.

**Evaluation**

- Based on the Modeling analysis all the model has almost the same Mean Squared Error.

![Screenshot 2024-04-15 at 9 28 13 PM](https://github.com/tombharath/used-car-price-ml-ai-bk/assets/37302704/e42d976a-1de1-4a52-950d-d8e3de325d03)

  
- For the Evaluation purpose I am choosing Ridge and LinearRegression
- Calculate the co-efficient of the features for each of the models
- Compare the Permutation importance of those two models to identify the features that impact the car price
- Coefficient and Permutation Importance of Ridge Regression
  
![Screenshot 2024-04-15 at 9 29 05 PM](https://github.com/tombharath/used-car-price-ml-ai-bk/assets/37302704/e2265f9b-e6c6-429e-93aa-1eb0ef9c6b22)

- Permutation Importance and feature accuracy of Ridge model
  
![Screenshot 2024-04-15 at 9 30 09 PM](https://github.com/tombharath/used-car-price-ml-ai-bk/assets/37302704/fa973260-8a73-444b-851a-1ea242423f24)

- Coefficient and Permutation Importance of Linear Regression
  
![Screenshot 2024-04-15 at 9 30 44 PM](https://github.com/tombharath/used-car-price-ml-ai-bk/assets/37302704/6c5aceaf-16ad-413d-9eeb-0a4158bd50e9)
  
- Permutation Importance and feature accuracy  of Linear Regression
  
![Screenshot 2024-04-15 at 9 31 39 PM](https://github.com/tombharath/used-car-price-ml-ai-bk/assets/37302704/73f07e43-349e-495b-8e98-ce6fb9801f18)

 ## Observations Summary

 - The goal is to identify what features impact the car price based on the past Dataset of information on 426K cars.
 - We have evaluated three different Models and chosen the two best models to identify the top 4 features that affect the car price
 - Based on Model Findings the top four features that impact the price of the cars are
    - model
    - year
    - odometer 
    - condition
  
  **Price**
  
The Price range of the cars sold after removing the outlier shows that more cars are sold between 1k and 40K

![Screenshot 2024-04-15 at 9 36 37 PM](https://github.com/tombharath/used-car-price-ml-ai-bk/assets/37302704/0913517a-55dd-4582-9824-30020654a8f4)

  **Model of the Car**
  
The Top Models which have sold over 2000 vehicles shows F-150 is the top-selling model followed by the below models
- unknown
- silverado 1500
- 1500
- silverado
- camry
- accord
- civic
- escape

![Screenshot 2024-04-15 at 9 37 56 PM](https://github.com/tombharath/used-car-price-ml-ai-bk/assets/37302704/c0509fca-7a3f-4ea3-a6e1-3d4a11e477c8)

  **Make Year**
  
The Mean price based on year and model shows that the cars made after 2000 have high mean selling price
- The upward curve in the price for the Silverado 1500 and escape model shows the higher sold prices for the make year after 2000

![Screenshot 2024-04-15 at 9 40 15 PM](https://github.com/tombharath/used-car-price-ml-ai-bk/assets/37302704/6f2ad6cc-587d-4151-84e9-711d2a506452)

 **Odometer**
 
The Mean price range is higher for the lower miles of the car

 ![Screenshot 2024-04-15 at 9 40 48 PM](https://github.com/tombharath/used-car-price-ml-ai-bk/assets/37302704/89a0addc-4488-4aea-9415-e09e56a3368b)

 **Condition**
 
 The condition and mean price comparison show the price is higher for the new and new-like conditions.

 ![Screenshot 2024-04-15 at 9 41 40 PM](https://github.com/tombharath/used-car-price-ml-ai-bk/assets/37302704/a9eb0f7f-a729-47b1-8533-426a0803706c)

## Recommendation and Next Steps
Collect more data to test and deploy the model to make the price range target for selling.

