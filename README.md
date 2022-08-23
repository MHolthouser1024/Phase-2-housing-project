# Home Rennovation Recommendations for King County, WA
---
**Author:** Michael Holthouser

---

## Business Understanding
---
King County Realtors need some guidance on assistance clients with recommendations on which home renovations may increase the value of their home prior to listing their home for sale. 
![king_county_image.png](attachment:king_county_image.png)
- **Stakeholder:** King County Realtors
- **Business Problem:** King County Realtors need to provide their clients with guidance on to improve the value of their homes prior to listing. 
- **Business Question:** Which home renovations might increase the estimated value of their homes, and by what amount?

## Data Understanding
---
The data for this project comes from the King County House Sales dataset. The data includes all data of single-family home sales from 2014-2015. The data can be accessed in the ``kc_house_data.csv`` dataset found in the github repository of this project.  The column names and their descriptions can be found in ``column_names.md``, which are also accessible in the github repository. 

The original dataset contains 21,597 records with 20 different features. For this particular project, I have limited the features down to 9 features.  The features included are: 
- `price` - sales price
- `bedrooms` - Number of bedrooms
- `bathrooms` - Number of bathrooms
- `sqft_living` - Square footbage of living space in the home
- `sqft_lot` - Square footage of the lot
- `floors` - Number of floors (levels) in house
- `waterfront` - whether the house is on a waterfront
- `grade` - Overall grade of the house. Related to the construction and design of the house
- `yr_built` - Year when house was built

## Data Cleaning
---
To create an accurate model, the following steps were taking to prepare the data: 
- Dropping columns that were not pertinent to this project and to the business question (sqft_lot, 'yr_built')
- Filling in any missing data from the dataset (the only missing data was in the waterfront column)
- Changing any string data types to a numerical data type
- Addressed Outlier data point

## Modeling
---
With the Ordinary Least Squares method, we are using coefficients in the analysis to be able to see if there are relationships between the features and the sale price. 

Using coefficients is an effective method for this project, because we are able to see how each individual feature impacts the sale price of a home. 

## Recommendations
---
In the final model with all features excluding ``bathrooms``, ``yr_built``, and ``sqft_lot``, our model's performance based on the adjusted R-squared improved from 0.493 to 0.581. 

In the final model, all features included in the model have statistical significance relationship with price.  All p-values are less than 0.05. 

**Coefficient Interpretations:**
- For every bedroom added to a home, it decreases the price of the home by 2.3%
- For every square foot of living added to a home, it increases the price of a home by 0.02%
- For every floor added to a home, it increases the price of a home by 1.7%
- For every increase in condition to a home, it increases the price of a home by 10.4%
- For every increase in the grade of a home, it increases the price of a home by 19.3%

**Conclusions for King County Realtors:**
1. In order to maximize the price of a home, you should recommend to your clients that they should use great quality      products when rennovating their home to increase the grade of their home to highest possible level.   
2. If the seller is wanting to expand the size of their home, creating another floor is a great option to increase the    price of their home. For a 500,000 dollar home, adding one floor would increase the price by 8,500.
3. Improving the condition of your home to a minimum, average condition, will increase your home's value by 10%. 
---
Our model only explains 58 percent of the variation in sale price, so we must tread with caution with our predictions. Our final model does not hold true every assumption of linear regression, and violaties the rule of homoscedasticity. 

**Future Work:**
- Add more features to our model to see the affects on adjusted R-squared. 
