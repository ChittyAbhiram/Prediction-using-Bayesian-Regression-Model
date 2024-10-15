# Prediction-of-movies-using-Bayesian-Regression-Model

#### **Introduction**
This report analyzes a dataset of movies released between 1970 and 2016, sourced from Rotten Tomatoes and IMDB. The goal is to explore relationships between audience scores and various movie features, such as genre, runtime, and critic scores, and to build predictive models for audience scores using multiple statistical methods. The dataset contains 651 movies with 32 variables, including movie type, release year, IMDB ratings, critic scores, and audience opinions.

#### **Data Manipulation**
We created new categorical variables to assist in the analysis:
- **Feature Film**: Whether the movie is a feature film.
- **Drama**: Whether the movie belongs to the drama genre.
- **MPAA Rating R**: Whether the movie is rated R.
- **Oscar Season**: Whether the movie was released in November, October, or December.
- **Summer Season**: Whether the movie was released in May, June, July, or August.

A new dataframe, `movies2`, was created containing important variables, such as audience score, runtime, IMDB rating, critic score, and several awards-related indicators.

#### **Exploratory Data Analysis**
Using boxplots, we explored how audience scores varied with new categorical variables. For example, we examined if R-rated movies or films released during Oscar or summer seasons had different audience scores. Additionally, correlation analysis revealed that audience scores are strongly correlated with critics' scores and IMDB ratings, with correlations of 0.70 and 0.86, respectively. Scatter plots with regression lines further confirmed the positive relationships.

#### **Modeling**
Three approaches were used to build predictive models for audience scores:

1. **AIC Model**: A stepwise regression model was built using the Akaike Information Criterion (AIC) to select important features. The final model included variables such as runtime, IMDB rating, critic score, and awards-related indicators.
   
2. **BIC Model**: A similar stepwise model was built using the Bayesian Information Criterion (BIC), which led to a simpler model including runtime, IMDB rating, and critic score.

3. **Bayesian Averaging**: A Bayesian Adaptive Sampling (BAS) model identified the most likely variables to be included in the best model. It confirmed that IMDB rating, runtime, and critics' scores were the most important features for predicting audience scores.

#### **Model Diagnostics**
Model diagnostics involved checking the normality of residuals and the spread of residuals versus fitted values. The residuals for both AIC and BIC models were normally distributed, and although there was slight skewness, the data mostly adhered to the assumptions required for linear modeling.

#### **Prediction**
The models were tested by predicting the audience score for the 2016 movie *Doctor Strange*, which was not in the dataset. The BIC model predicted a score of 80.49, while the AIC model predicted a similar score of 80.41, close to the actual score of 80. This confirmed the models' predictive accuracy.

#### **Conclusion**
The analysis found strong correlations between audience scores and both critic scores and IMDB ratings. Both AIC and BIC models were effective at predicting audience scores, with the BIC model being marginally more efficient. Bayesian modeling confirmed that the most important predictors were IMDB ratings, critic scores, and runtime. These models provide valuable insights into the factors influencing movie success as perceived by audiences.
