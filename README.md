# How many calories are in your dish?


# Introduction

Welcome to my recipes and ratings analysis. This homework analyzes a **Recipe Dataset** that contains information regarding various recipes, their ingredients, ratings, and preparation times. Using certain features of recipes, we can predict the number of calories for a recipe. This question is valuable for chefs, food enthusiasts, and those interested in understanding nutritional aspects behind foods. This dataset contains 83782 rows and 3 rows relevant to my analysis. These rows include total fat (total fat in grams in a recipe), sugar (grams of sugar in a recipe), and minutes (number of minutes it takes for a recipe).

# Data Cleaning and Exploratory Data Analysis
The dataset contained a nutrition column, which looked like a list of numbers. However, these values were actually strings that looked like integers. First, I decided to change the values in the lists to integers, so I could work with them. Then I split the nutrition column into separate columns, corresponding to the categorical feature that each value represented. That is how I ended up gathering the total fat and sugar colunmns for my analysis. Doing this cleaned up my data and made it easier to process each value. Then, I imputed missing values in the num calories column with the mean of the column. I chsoe the mean because once I manually looked through the data, the mean seemed to be more accurate to the values already presented.  **Add head of dataset, univariate plot, multivariate plot, merged table, data before and after imputing**

