# Mitsubishi-Project-Environmental-risk-factors-on-ALS-for-drug-development
（Demo slides to be updated）


## Project Background (to be updated): 
One pathway of drug development for treatment of ALS depends on the ethnobotanical identification of flora with either toxic or therapeutic activity.

## Project Goal：
We will perform case-control studies of exposures to individual pollutants as risk factors for ALS using Geographical Information System (GIS) methodologies. Following the previous research, we expect to identify the potential synergistic effects of individual environmental pollutants for new drug development for the treatment of ALS.

## Work flow:

### Random Assignment and Random split:
1. Find the year that splits the data to roughly 2:1. Obtain the "old_ALS" data and "recent_ALS" data. (with actual ratio of 65%:35%)
2. In the control group (No ALS), randomly assign 65% to the "train" set and 35% to the "test" set. 
3. Bind in the experimental group (the ALS patients):  old_ALS to the "train" set, and the recent_ALS to the "test" set.

### Data Cleaning: Clean the data in two ways to generate continuous-variable version and categorical-variable version for different preliminary analysis:
1. In the training set, eliminate the columns that have more than 80% NA's.
approach 1: use the smallest non-NA value then divide it by 2
approach 2: categorize the values to be NA = 0, lower than the median of the non-NA's = 1, higher than the median of the non-NA's = 2

### Analytical Approach:
1. Glinternet: to explore the main effect and interaction effect of pollutants on ALS;
2. Logistic regression: used to filter and validate the pairs from the glinternet model;
3. FDR: to obtain the adjusted p-values by computing the basic false discovery rate given the p-values from the logistic regression model.
4.CreateTableOne: do some descriptive analysis on the final result of the target pairs, to see how the individual pollutant measure is distributed in the train and test set.
