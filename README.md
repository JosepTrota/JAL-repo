# JAL-repo

### Repository for the mid bootcamp project (classification)

## Data Exploration

Exploring the DataFrame, we had to deal with some null values that had been removed because of the small proportion compared to the total (practically no difference whether we include them or not). Besides, we encountered two outliers in the column 'household size' that had also been removed for the same reason. Further conclusions (or details) in 3.2.5 from the [notebook](https://github.com/JosepTrota/JAL-repo/blob/main/Code/Case%20Studio%20Bank%20Final.ipynb).

Based on what we have seen in the columns from a general perspective, on the one side, some patterns follow a uniform tendency when we talk about the majority ('income level', 'nº bank accounts open', among others). On the other side, other variables such as 'reward' or 'average_balance' follow a different pattern depending on whether the client accepts or not the offer. More information is in the column analysis report (in this SQL report [file](https://github.com/JosepTrota/JAL-repo/blob/main/MySql/Profiles%20and%20patterns.pdf)).

However, there is no correlation between the variables except for the balance quarters and average balance.

![image](https://user-images.githubusercontent.com/96822258/154541671-856745dd-941b-4c9d-9702-1797873e5155.png | width=100)


## Feature engineering (profiling, dropping…)
In the histogram for average balance three distinct “normal bells” can be seen, so we decided to split them onto groups as seen in the area chart. That had a part into the profiling, which combined values of the new groups, credit rating and income level in order to identify people who had high to low values on each of them.
-	There is a large chunk of the data (almost 1/5) that has a different value in each one of the profiling variables (one high, one medium, one low). Thus the creation of the non profilable class.
-	Variables dropped (random forest insights)



## Models and their insights
We have used 3 different models to evaluate our case study: Regression Logistic, Knn, Random Forest<BR>
- **Original Data:** In the first place we have analyzed the original database, applying the three aforementioned models to it. We have used different scalers and samples to try to improve our predictions, we have also used improvement techniques such as looking for the best value of K for the Knn model or looking for the best features for the Random Forest model.<BR>
  - Our best result has been applying the Logistic Regression model, and afterwards applying SMOTE oversampler.
- **Profiled Data:** After doing feature engineering, we have created a new database that we have used to do a second analysis. Here we have applied all available scaling methods, sampling methods and enhancement techniques to our model to find the best prediction.
  - In this case, our best result has been applying the random forest model with SMOTE oversampling.
  
## Final insights

### Conclusions
  
- The target variable is highly imbalanced; therefore, it affected our results.

- After applying the three predictive models, we concluded to make feature engineering to create a new (and shorter) Data Frame based on the profiles extracted from some important variables and the ones which are more related to the target variable.

- The best model prediction is the random forest combined with the SMOTE oversampler implemented on our profile Data Frame because it returns more 'yes' values than the rest of the models in both datasets.

### Recommendations
  
- The bank could be more interested in rewarding the clients who do not accept the offer with an alternative reward instead of a credit card to achieve more benefits.

### Proposals

- Include a Date-Time variable.
- Replace the mailing system with email.



  
  
  
  
  
