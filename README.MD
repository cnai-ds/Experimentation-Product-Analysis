# Experimentation
This is the repository to demonstrate the analysis approach for experimentation, including A/B testing, A/A testing, and quasi-experimental testing for data driven product decision making. <br><br>

If you would like to know more about it, wave me somehow ! <br>

## Essential step of Experimentation:
### 1. Sanity check and data quality check
Core step of experimentation as there can be technical issues during the experiments or test design defects. <br>
If the data is not correct, then further analysis would not have value.
- Check the latency of the new features and if the data are recorded into database, and the definition of the data is consistent across all the tables
- Check buckets that you designed with javascript are equal both in control and treatment. This include sub-buckets like geography, device, environment, marketing channel, or any user-segment 
- Check if the invariant metrics (user-defined) are equal both in control and treatment
- Check extreme outliers, missing values, data type, # of unique values
<br>

### 2. EDA
Before jumping into statistical tests, visualize the KPIs first to have the sense of the result ! <br>
It is important when we present the result to stakeholders and also to detect the faulty statistical test results.
- Check mean and medium, group by subgroups
- Plot boxplot, distribution, bar chart
<br>

### 3. Explanatory modeling
This step can be skipped if you are testing for conventional and one-directional KPIs, such as CVR, CTR, or OR, and no causality is found.
<br>

### 4. Statistical tests
There are 2 type of statistical tests, Frequentist and Bayesian, and many companies uses 3rd party tools to run the test and the preference between these 2 can vary among companies. c
However, I would recommend to test by 2 methods whenever possible to cross validate, especially when the delta is small or if the result is against the business sense, as both methodoloy have pitfalls. <br>
- Frequentist: risk to commit type I & II errors
- Bayesian: risk to choose wrong prior
<br>

### 5. Causal inference
If you detect so-called co-founders, we have analyse differently. <br>
There are several methodologies to approach causality problems:
- Propensity score matching
- Propensity score stratification
- Difference in difference test
- Synthetic conttrol
