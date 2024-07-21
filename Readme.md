# Group 6 Project
## Problem Statement:
For this project, the team will use regression modeling to analyze house sales in a NorthWestern county.

### The Data:
This project uses the King County House Sales dataset, which can be found in kc_house_data.csv in the data folder in this repo. The description of the column names was also provided in column_names.md in the same folder.

### Business Problem:
The team was tasked with defining a stakeholder and business problem appropriate to this dataset.

## Proposed Solution:

### Business Understanding:

The group have used the following imagined scenario to develop the business case for this project: 
Group 6 is KingsCounty Realtors Ltd. A real estate agent dealing with properties in Kings County. The target audience of our modelling is household owners and potential buyers who are either looking to sell or buy a property in King County and would like to contract KingsCounty Realtors to support them with the service. 

This model and presentation seeks to review the following objectives:
1. Predicting the house prices 
2. Assessing the impact of house conditions and revonations on house grade
3. Understanding the impact of structural characteristics on house grade
4. Assessing neigbourhood influence on house prices

For the purpose of the project, the team used the data provided in kc_house_data.csv

The team followed the following process to achieve the above objectives and develop clear recommendations for the customer:
1. Data Understanding
2. Data Preparation
3. Modelling & Evaluation
4. Model limitations
4. Recommendations

Each section is shared below with the related code elements.
 
## Step 1: Data Understanding
To start the section, the team followed the following steps: 
1. Import the initial relevant libraries to support reading and interpretation of the data. 
2. Identify the contents of the dataset provided in order to deliberate on what possible uses the data could have in supporting the clients mentioned.
3. Convert the dataset into its numerical components and identified outliers and sum of null values in each column.
4. Carried out exploratory data analysis on the price. 
5. Review a correlation matrix of all the colums in the dataset. 
6. The team also created charts for the data to identify distribution, skewness of the data based on certain parameters.

The details for each are outlined in the code below.


## Step 2: Data Preparation
### a. Data Cleaning: 
For this process, the data was reviewed to identify the level of cleanliness of the data. 
A few problems were identified in the data:
1. The date was listed as an integer and not date time format. 
2. Some fields were listed as objects which would make it difficult to review and interpret data. 
3. There were a large number of null values for some of the columns; namely: xx, xx and xx 
4. Checking for and removing multicollinearity (correlated predictors)*****

### b. Feature engineering:
The team then reviewed the data to identify the columns that would go to the model. The first step taken was to normalise the data by scaling the data set for numericals. 
The second step was to drop some of the columns for the dataset. 

## Step 3: Modelling and Interpretation
In this section the team developed the following models to test out which one would give the outcomes that could address the customers issues. Each model highlights the objectives identified at the beginning. 
The following steps were followed in the modelling:
1. Create a linear regression model based on the objectives
2. Create and visualise the training model
3. Interpret the findings

Objective 1: Predicting House Prices

Purpose: To help buyers understand the factors that most influence house prices in Kings County, thereby making informed decisions on which properties to consider.

## Interpretation  of findings

The linear regression model developed to predict house prices in Kings County shows a high level of explanatory power with an R-squared value of 0.700. This indicates that 70% of the variability in house prices can be explained by the 18 selected features. The model is statistically significant, with a very high F-statistic (2798) and a p-value of 0.00, signifying that the overall model is robust and the predictors are meaningful in explaining house prices. Additionally, the adjusted R-squared value remains at 0.700, reinforcing the model's strong fit.

Several key features significantly influence house prices, as indicated by their p-values and coefficients. For instance, sqft_living has a positive coefficient (102.832) and a p-value of 0.000, implying that an increase in the square footage of living space is associated with higher house prices. Similarly, waterfront (coefficient: 618,100) and grade (coefficient: 96,910) also have substantial positive impacts on house prices, highlighting that homes with waterfront views and higher grades are priced significantly higher. On the other hand, some features like sqft_basement and longitude have negative coefficients, indicating that larger basements and certain locations (eastward longitude) might negatively 

## Model 2

Objective 2: Assessing the Impact of House Condition and Renovation on House Grade

Purpose: To inform homeowners about the significance of maintaining and renovating their homes in order to improve their grade, and to help buyers evaluate the quality of potential purchases based on these factors

## Interpretation of findings

The linear regression model has an R-squared value of 0.705, indicating that 70.5% of the variability in house grades can be explained by the selected features. The model is statistically significant, as evidenced by the high F-statistic (5741) and a p-value of 0.00, demonstrating that the predictors collectively provide a good fit for the data.


sqft_living and sqft_above positively influence house grades, suggesting that increasing the living space and above-ground square footage can lead to higher grades.
The number of bathrooms has a significant positive impact, indicating that additional bathrooms enhance the property’s grade.
Interestingly, the number of bedrooms has a negative coefficient, which could imply that larger homes with more bedrooms may not always equate to better grades if the quality or functionality of space is compromised.
The year built positively impacts the grade, showing that newer homes tend to have higher grades.
The price variable (coefficient: 1.059e-06) is also significant, underscoring that higher-priced homes generally receive better grades.

Objective 3: Understanding the Impact of Structural Characteristics on House Grade

Purpose: To help buyers and sellers understand how various structural characteristics of a house influence its overall grade, thereby assisting in property valuation and improvement decisions.
The linear regression model has an R-squared value of 0.658, indicating that 65.8% of the variability in house grades can be explained by the selected structural features. The model is statistically significant, with a high F-statistic (4147) and a p-value of 0.00, demonstrating that the predictors collectively provide a good fit for the data

The number of floors has the highest positive impact on house grades. Homes with more floors generally receive higher grades.
The square footage of living space also positively impacts house grades, highlighting the importance of ample and functional living areas.
More bathrooms positively influence house grades.
Interestingly, the number of bedrooms has a negative impact, suggesting that simply having more bedrooms does not necessarily lead to a higher grade.
The negative coefficient for waterfront properties indicates that not all waterfront homes are valued equally, potentially due to maintenance challenges or specific location factors.Newer homes tend to receive higher grades, indicating the value placed on modern construction and design standards.

Objective 4: Assessing Neighborhood Influence on House Prices

Purpose: To guide potential buyers on the significance of the neighborhood characteristics in the valuation of properties, thus influencing their choice of location.

The linear regression model has an R-squared value of 0.546, meaning that 54.6% of the variability in house prices can be explained by the selected neighborhood features. The model is statistically significant, with a high F-statistic (4325) and a p-value of 0.00, indicating a good fit for the data.

Higher latitudes are associated with higher house prices. This may be due to the desirable locations or specific characteristics of areas at higher latitudes within Kings County. Lower longitudes negatively impact house prices, suggesting that properties in areas with higher longitudes are less valued.
Larger average living spaces in a neighborhood significantly increase house prices. This highlights the importance of the neighborhood's overall residential quality.
Larger average lot sizes in a neighborhood also contribute to higher house prices, although the effect is less pronounced compared to living space.
The grade of a house is a strong predictor of its price. Higher grades lead to substantially higher prices, underscoring the importance of quality construction and finishes.


## Step 4: Model limitations
The following limitations were identified for the models generated:

1. Despite the model's robustness, there are some concerns about multicollinearity, as suggested by the large condition number. Multicollinearity can lead to inflated standard errors, making it harder to determine the true effect of individual predictors. 

2. While the model is robust, the non-normal distribution of residuals suggests potential outliers or non-linear relationships. Real estate professionals should use the model's predictions as one of several tools, combining them with qualitative insights and local market knowledge. Additionally, regular updates and recalibrations of the model are recommended to maintain its accuracy and relevance in changing market conditions


## Step 5: Recommendations
The following recommendations were proposed from the data:

1. Emphasize Key Features to Buyers and Sellers:

Given the strong influence of certain features on house prices, real estate agents should focus on these key aspects when advising clients. Emphasizing the importance of living space (sqft_living), house grade, and waterfront views can help buyers prioritize properties with these attributes, as they significantly increase house prices. Sellers can also benefit from understanding that investing in these areas can lead to higher returns.

2. Use Model Insights for Strategic Investments:

Real estate investors can leverage the model's insights to make strategic investments. Understanding that features like sqft_living, grade, and waterfront significantly increase prices, investors can prioritize properties with these attributes for higher returns. Additionally, considering renovations or improvements that enhance these features can be a strategic move to maximize property value.

3. Emphasize the Importance of Maintenance and Renovation:

The model shows that maintaining and renovating homes significantly impacts their grades. Features such as the year built (coefficient: 0.009) and year renovated (though not statistically significant in this model) are crucial. Homeowners should prioritize regular maintenance and consider timely renovations to improve or maintain their home’s grade, thereby increasing its market value and appeal.

4. Address Potential Negative Influences:

The analysis indicates that some structural characteristics might negatively affect house grades. For instance,  in model 3, the number of bedrooms (coefficient: -0.1458) and waterfront properties (coefficient: -0.2446) surprisingly have negative coefficients. This suggests that simply adding more bedrooms without considering overall space quality or certain waterfront properties might not always lead to higher grades. Buyers should carefully evaluate these aspects in relation to the overall property condition and other features.

5. Highlight the Importance of Location:

The regression analysis indicates that neighborhood characteristics significantly influence house prices. Factors like latitude (coefficient: 612,900) and longitude (coefficient: -426,900) show strong relationships with property prices. This suggests that properties located in certain areas (higher latitudes and lower longitudes) are valued more highly. Homebuyers should carefully consider the geographic location when evaluating properties, as it plays a crucial role in the overall value.

6. Emphasize the Impact of Nearby Property Sizes:

The square footage of living space (sqft_living15, coefficient: 151.75) and lot size (sqft_lot15, coefficient: 0.42) of neighboring properties also have a significant impact on house prices. Properties in neighborhoods with larger average living spaces and lot sizes tend to be more expensive. Buyers should assess the average property sizes in a neighborhood to gauge potential price appreciation, while sellers can leverage this information to set competitive prices.

7. Utilize Grade as a Key Selling Point:

The grade of a house (coefficient: 144,500) is a crucial determinant of its price. Higher-grade homes command significantly higher prices, indicating that buyers are willing to pay a premium for quality. Sellers should focus on maintaining or improving the grade of their homes to maximize their market value. Buyers should consider the grade as an indicator of overall quality and long-term value when making purchasing decisions.

