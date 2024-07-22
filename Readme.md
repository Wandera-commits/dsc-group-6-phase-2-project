# Group 6 Project
## Problem Statement:
To leverage regression modeling to provide actionable insights for homeowners and potential buyers in Kings County, enabling them to make informed decisions that maximize their investment returns and property value.

### The Data:
This project uses the King County House Sales dataset, which can be found in kc_house_data.csv in the data folder in this repo. The description of the column names was also provided in column_names.md in the same folder.

## Proposed Solution:

### Business Understanding:

The Kings County Sales Data served as the foundation for our analysis, allowing the team to formulate clear and actionable recommendations for stakeholders. As a real estate agent specializing in properties in Kings County, our primary audience includes house sellers and potential buyers. These individuals are looking to either sell or purchase a property in King County and seek professional advice to guide their transactions. By leveraging this data, we aim to provide insights and strategies that will help our clients make informed decisions, ensuring successful and satisfactory real estate experiences. 

For this project, we developed models to address the following business challenges:

1. Predicting house prices
2. Assessing the impact of house conditions and renovations on house grade
3. Understanding the impact of structural characteristics on house grade
4. Evaluating neighborhood influence on house prices

The Project was divided into a systematic process that involved:

- Data Understanding: Familiarizing ourselves with the dataset to identify key variables and trends.

- Data Preparation: Cleaning and transforming the data to ensure accuracy and reliability.

- Modeling & Evaluation: Building and assessing models to achieve our objectives.

- Recommendations: Providing actionable insights based on our findings.

Each section is detailed below, along with the related code elements.

 
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


### For Potential Buyers:

1. Focus on Key Features for Better Investments

- Living Space: Prioritize properties with larger living spaces (sqft_living), as this significantly impacts house prices. A larger living area often translates to higher value and greater comfort.
- House Grade: Pay attention to the grade of the house. Higher-grade homes typically offer better quality and long-term value.
- Waterfront Views: If within budget, consider properties with waterfront views, as these can substantially increase the property's value and appeal.

2. Consider Location and Neighborhood Characteristics

- Geographic Location: Properties located at higher latitudes and lower longitudes tend to be more valued. Focus on these geographic characteristics when choosing a location.
- Neighboring Property Sizes: Evaluate the average living space (sqft_living15) and lot size (sqft_lot15) of neighboring properties. Areas with larger average sizes tend to appreciate more in value, providing better investment potential.

### For Homeowners

1. Enhance key features to maximize returns, and consider strategic renovations and maintenance


- Living Space Improvements: Consider expanding or improving the living space of your home. This can significantly boost its market value and make it more attractive to potential buyers.
- Maintain High House Grades: Regular maintenance and improvements to the home's grade can lead to higher returns. Focus on quality enhancements that boost the overall grade of your property.



By following these recommendations, potential buyers can make informed decisions to maximize their investments, while homeowners can enhance their properties to achieve higher returns when selling.



