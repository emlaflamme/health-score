# health-risk-score

## Methodology:
*Methodology adapted from the CDC 500 Cities Project: Zhang X. et al. Multilevel Regression and Poststratification for Small-Area Estimation of Population Health Outcomes: A Case Study of Chronic Obstructive Pulmonary Disease Prevalence Using the Behavioral Risk Factor Surveillance System. Am J Epidem. 2014; 179 (8)*

### Data Source:
Chicago Department of Public Health, Healthy Chicago Survey 2014-2016 (pooled) n = 7649
Representative of Chicago's adult popultion (aged 18+)
Combined three years (2014-2016) of HCS survey data to obtain prevalence estimates of smoking 
Respondents with missing smoking status, age, sex or race/ethnicity were excluded from analysis 

### Rescaling weights:
To account for unequal probability sampling of respondents in the Healthy Chicago Survey, each record is associated with a weighting factor (sums to the total adult population of Chicago). Because PROC GLIMMIX WEIGHT statement treats its weight variable as a frequency weight, we rescaled the probability weights to sum to the sample size for Chicago (7649) 

Sum pooled_trimmed_weight14_16 = 2079053.76

RWi = [ pooled_trimmed_weight14_16 / 2079053.76] * 7649

∑RWi = 7538 (because of weight trimming). Mean = 0.997. Range = 0.08 - 4.26

### Missing values:
Community areas with a total sample less than 25 were excluded from analysis:
Oakland (n=13)
Burnside (n=13)
Fuller Park (n=14)
Armour Square (n=14)
O'Hare (n=21)
Riverdale (n=23)

Missing qk1 = 13

After exclusions, n=7538

### Model variables:
Individual:	age (18-29, 30-44, 45-64, 65+)
		gender (male, female)
		race/ethnicity (NH asian/PI, NH black, hispanic, NH other, NH white)
Community area:	community area poverty (% living below poverty level; range: 2.6% - 45.7%) mean = 22.3%

Individual-level age-by-race-by-sex estimated prevalence 

Note: Interactions have not been identified yet
