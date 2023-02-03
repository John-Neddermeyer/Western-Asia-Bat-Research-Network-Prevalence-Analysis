# Western-Asia-Bat-Research-Network-Prevalence-Analysis
Coronavirus prevalence statistical analysis and figures

This analyis modeled coronavirus prevalence in bat species captured across western asia. Individual infection status was determined 
using PCR with degenerate primers designed to target coroanvirus RNA-dependent RNA polymerase. Coronavirus taxonomic classification
was not included in this analyses. Only presence or absence of coronavirus infection. Data were modeled using logistic regression
with a logit link function.

Note: This analysis is not yet complete and any results are subject to change.

## Modeling Approach

Exploratory figures were generated to visualize relationships between predictor variables and response variable
(presence or absence of infection). Correlation matrices were used to assess correlations between predictor variables. Step-wise model 
selection using both AIC and BIC, and three different regularization regression methods, LASSO, Ridge and Elastic-net, were used to 
model coronavirus infection prevalence. The chosen alpha value for Elastic-net was determined using 50 rounds of cross-validation 
across alpha values ranging from 0 to 1. The top performing model was identified using 50 rounds of 2-fold cross-validation. Receiver operator curves
were generated for each fold in each round, and an Area Under the Curve (AUC) calculated. The model with the greatest AUC values was
identified as the top performing model. Paired Wilcoxon tests were used to determine if a statistically significant difference between model AUC
distributions was present.

## Identifying Predictor Significance

Significant predictors in the top performing model were identified using 1,000 rounds of bootstrap replication. For each round a bootstrapped replicate
was generated and used as input for model coefficient estimation. Coefficients for each replicate were extracted and stored resulting in a distribution 
of coefficients for each predictor. A mean and 95% BCa Confidence Interval was generated for each predictor distribution. If the 95% CI contained
zero on the logit scale the predictor was determined not to be a significant determinant of coronavirus prevalence.
