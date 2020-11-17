### Project 1: Standardized Test Analysis

### Problem Statement:

In this analysis, I set out to answer the question **"Is there a meaningful relationship between standarized test performance and family financial background?"**

While standarized tests like SAT and ACT strive to enable colleges to objectively evaluate their applicants' competency in areas such as math, reading, and writing, which are critical skills required for success in higher education, it is important to note that these standarized test scores should and need to be viewed and weighted through proper social and cultural perspectives. 

One of the considerations is the intricate and complex relationship that may exist between test scores and contextual factors such as family background, ethnicity, race, and etc. For instance, intuitively speaking, it isn't a big of a stretch to infer that students who come from wealthier backgrounds may perform better on standarized tests than students that come from families with low income. As you can imagine, it is probably more likely for students that come from wealthier backgrounds to have access to better education system support and resources that students who come from poorer background may not have the luxury of leveraging for their academic success.

This analysis is an attempt at trying to answer this complex question through the lens of data and seek to find any statistical importance and relevance.

### Data Dictionary

|Feature|Type|Dataset|Description|
|---|---|---|---|
|**state**|object|final_datal|U.S State (including District of Columbia)|
|**sat_part**|float|final_data|SAT Participation Rate by State|
|**sat_total**|int|final_data|Average SAT Total Score by State|
|**act_part**|float|final_data|ACT Participation Rate by State|
|**act_comp**|float|final_data|Average ACT Composite Score by State|
|**med_income**|float|final_data|U.S. Median Household Income by State (3-Year Moving Average Between (2017-2019)|

### Brief Summary:
In order to perform this analysis, I examined the historical SAT/ACT State Average Scores and Participation Rates between 2017-2019. Using the median household income data provided by the [United States Census Bureau(Table H-8B)](https://www.census.gov/data/tables/time-series/demo/income-poverty/historical-income-households.html), I was able to measure correlation between SAT/ACT performance and median household income by state.

1. **Based on observations made in this analysis, there is a moderately positive correlation between SAT/ACT scores and household median income**.

2. There is a negative correlation between SAT/ACT state average scores and their respective participation rates. This can create a lot of noise due to the fact that states with low SAT/ACT participation rates have very high average test scores. Conseqeuntly, it is important to implement some sort of controlling parameter to account for this "low participation, high score" effect. In this analysis, my controlling parameter was participation rate >=0.50.

3. Based on SAT and ACT participation distributions, states have strong preference between SAT and ACT. While many states fall under the < 0.5 SAT participation rate cluster, converse is true for ACT in that many states fall above the > .90 scale. The significance of this bimodal-like behavior is that setting the parameter participation rate >=0.5 cuts more "deeply" into SAT pool than ACT when analyzing correlation in respect to median income. Therefore, in this analysis, correlation that we see between ACT and median income is a slightly better statistical data to lean on.

### Takeaways/Recommendations:
Based on observations made in this analysis, there is a moderately positive correlation between SAT/ACT scores and household median income. While correlation does not signify causation, it does not exclude out the possiblity that there may be some underlying dynamic force at play that we as socially responsible data scientists should pause and look further into. This is certainly true when we consider the magnitude of what this potentially could mean for many students who come from low income backgrounds. From experience, we know that there is no perfect system. If we look deep enough, hard enough, carefully enough, we can always find and measure the flaws embedded deeply within our systems, own biases, conscience, and attitudes. I believe the same principle should be applied here as well. It could potentially change the way we evaluate and assess students' true potential in the future.

Here are some major takeaways:

As socially responsible data scientists, there are a number of other considerations that we should weigh and examine further.

1. Decluster the "low participation, high score" effect by obtaining and analyzing more granular set of data. Instead of using a statewide average which can be heavily influnenced by participation rate, use the actual raw data.
2. Incorporate a more fitting median income dataset. While the data provided by the US Census Bureau may serve as a good representation of the true population, perhaps it may be more appropriate to work with subset of that data that may be more relevant such as household median income for families with kids.
3. Correlation is not causation. Continue to search and find meaningful relationships, keep testing against measurable variables, and leverage new resources and findings to better fine-tune the regression model.