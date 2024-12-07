# How many calories are in your dish?


# Introduction

Welcome to my recipes and ratings analysis. This homework analyzes a **Recipe Dataset** that contains information regarding various recipes, their ingredients, ratings, and preparation times. Using certain features of recipes, we can predict the number of calories for a recipe. This question is valuable for chefs, food enthusiasts, and those interested in understanding nutritional aspects behind foods. This dataset contains 83782 rows and 3 rows relevant to my analysis. These rows include total fat (total fat in grams in a recipe), sugar (grams of sugar in a recipe), and minutes (number of minutes it takes for a recipe).

# Data Cleaning and Exploratory Data Analysis
The dataset contained a nutrition column, which looked like a list of numbers. However, these values were actually strings that looked like integers. First, I decided to change the values in the lists to integers, so I could work with them. Then I split the nutrition column into separate columns, corresponding to the categorical feature that each value represented. That is how I ended up gathering the total fat and sugar colunmns for my analysis. Doing this cleaned up my data and made it easier to process each value. Then, I imputed missing values in the num calories column with the mean of the column. I chsoe the mean because once I manually looked through the data, the mean seemed to be more accurate to the values already presented.

<iframe
  src="plots/recipes_head.html"
  width="800"
  height="600"
  frameborder="0"
></iframe>

 **Add head of dataset, univariate plot, multivariate plot, merged table, data before and after imputing**

# Framing a Prediction Problem 
**Prediction Problem - Given the total grams of fat, total grams of sugar, and preparation time in minutes of a recipe, predict the number of calories in that recipe.**
This is a regression problem, since we are predicting a numeric output. The response variable is number of calories, and I chose this metric because from the data given, it is possible to make accurate predictions. I am using MSE (mean squared error) and R-squared (coefficient of determination) for my metrics. Since this is a regression problem, it is difficult to use metrics such as AUROC, and MSE and R-squared are viable metrics for regression problems.

# Baseline Model
For the baseline model, I started out by using only total grams of fat and number of minutes to predict number of calories. Both features are quantitative. Using them, I trained a simple Linear Regression model and outputted the models MSE and R-squared. I found that the MSE was 73359.16 and the R-squared value was 0.7908. While the MSE is quite high, the R-squared value shows a somewhat strong relationship between total grams of fat and sugar and the number of calories. I would not say this model is necessarily good or bad. I would say it is decent, but improvement can definitely be made.

# Final Model
After I completed my baseline model, I conducted some analysis. I drew a feature correlation heatmap, showing the correlation between each feature. According to the heatmap, each feature had a correlation of 1 with itself. I noticed that total grams of fat had a high correlation with number of calories but so did total grams of sugar. They were almost the same correlation. This also intuitively makes sense because we know dishes with more sugar tend to have more calories. Because of this correlation, I decided to include total grams of sugar as another feature in my model. I also decided to use the PolynomialFeatures() function from sklearn.preprocessing. This create polynomial mappings between features, allowing the model to capture more complex relationships in the data and form a more accurate model. I kept using Linear Regression since it was suitable for the problem I was trying to predict. From this, the MSE of my model significantly decreased to 37895.54 and the R-squared value significantly increased to 0.8919. This demonstrates that the changes I added to the model undoubtedly improved the performance of it.  
