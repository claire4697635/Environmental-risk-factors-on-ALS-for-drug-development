# Mitsubishi-Project-Environmental-risk-factors-on-ALS-for-drug-development



## Project Background (to be updated): 
ALS, or Amyotrophic lateral sclerosis, is a nervous system disease in which a person’s brain loses connections with the muscles. It is hard to be diagnosed til avg. 9 month later, with the avg. life expectancy to be 2-5 years. Currently, 4 drugs have been developed to treat ALS. Although, none of them can cure ALS. The existing drug developed by Mitsubishi can only slow down the process of developing ALS by 25%-30%. It cost roughly $2B to develop a new drug.

Therefore, researchers and scientists are seeking a different pathway to improve the performance of the drug. Study has shown that classes of environmental toxins increase the likelihood of ALS, especially in regard to pesticides. However, people are likely exposed to multiple chemicals. It is too soon for the scientists to know which individual chemicals, or mixtures of chemicals, lead to motor neuron damage. On the other hand, Some of environmental toxicants have synergistic effects

One pathway of drug development for treatment of ALS depends on the ethnobotanical identification of flora with either toxic or therapeutic activity.

## Project Goal：
TO improve the drug performance and safe budget efficiently, we performed the case-control study of exposures to individual pollutants as risk factors for ALS and find environmental pollutants that are risk factors for the development of ALS. By doing pairwise interaction analysis, we expect to search through (485 choose 2) pairs of toxicants and identify the individual environmental pollutants with synergistic effects for new drug development for the treatment of ALS.


I worked on developing the model tested on the old patients data to predict the future cohort’s disease outcome.


## Work flow:

### Random Assignment and Random split:
(control group: ALS group = 2:1)
1. Find the year that splits the data to roughly 2:1. Obtain the "old_ALS" data and "recent_ALS" data. (with actual ratio of 0.65:0.35)
2. In the control group (No ALS), randomly split the data to the "train" set and "test" set with a ratio of 0.65:0.35. 
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
