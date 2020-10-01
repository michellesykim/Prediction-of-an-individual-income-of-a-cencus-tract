# Prediction-of-an-individual-income-of-a-cencus-tract
This repository talks about the individual income regression model based on the incarceration rate and household income in Washington, DC.

# Background Information
From my first mini project, I explored the relationship between parent income and the incarceration rate in Baltimore, MD and Washington, DC. And from the analysis, it is true that lower income parents (children financial circumstance) lead to a higher incarceration rate of their children in both areas. Now, I would like to explore how the high incarceration rate and the low household income (also represents children financial circumstance along with parent income) together would affect the children’s future individual income specifically in Washington, DC (Baltimore, MD had a small number of data), and see if I can possibly predict the individual income based on the two variables. Like cycle of poverty, if it is true that one ends up earning a lower income after jail, one would have a higher possibility of raising their future children under low household income, then this would again lead to a higher chance for their future children to be incarcerated, and the cycle would never end. Thus, it is a very important analysis to see how the economic status (household income) and the incarceraion rate would affect the individual income. 

# Business Question
How would the incarceration rate and household income (childhood financial background)affect individual income?

# Data Question
Can we predict one's individual income in Washington, DC based on one's incarceration rate and household income?

# Original Data
[Individual income in Washington, DC] https://github.com/michellesykim/Prediction-of-an-individual-income-of-a-cencus-tract/blob/master/DC-indiv%20income.csv

[Incarceration rate in Washington, DC] https://github.com/michellesykim/Prediction-of-an-individual-income-of-a-cencus-tract/commit/33f4ad7eccd3a02c1db6ff70b029b2f6175a131f

[Household income in Washington, DC] https://github.com/michellesykim/Prediction-of-an-individual-income-of-a-cencus-tract/blob/master/DC-Household%20income.csv

# Analysis Data
[Regression model analysis of individual income in Washington, DC] https://github.com/michellesykim/Prediction-of-an-individual-income-in-Washington-DC/commit/3f58245204afd0a1afe533d02278361b14480813
Attached file contains the original data of individual income, household income, and incarceration rate in Washington, DC. It also includes the regression model analysis of individual income based on the incarceration rate and household income.

# Key Findings

![alt text](https://github.com/michellesykim/Prediction-of-an-individual-income-of-a-cencus-tract/blob/master/Screen%20Shot%202020-09-30%20at%209.35.50%20PM.png)


R^2 value tells us how well the linear regression line predicts the outcome data. Here, the R^2 value is approximately 0.94, which means 94% of the individual income data in Washington, DC can be explained by the incarceration rate and household income.

Next, standard error measures the spread of the data around the linear regression line. Here, the standard error value is about 1716.58, which means approximately 68% of the predictions for individual income are accurate within one standard error ($1,716.58) and 95% of the individual income prediction is accurate within two standard errors ($3,433.16).

![alt text](https://github.com/michellesykim/Prediction-of-an-individual-income-of-a-cencus-tract/blob/master/Screen%20Shot%202020-09-30%20at%209.55.24%20PM.png)

Coefficients give the best fitting estimate of the multiple regression line. Here, the the multiple regression line is **Individual income = 12,507.04 - 22,326.22*Incarceration rate + 0.467*Household income.** If incarceration rate increases by 0.001, the individual income will decrease by $223.3 (negative correlation). Also, when there is an increase of $1,000 in household income, the individual income would increase by $467 (positive correlation). And the coefficient of the intercept (12,507.04) is theoretically the expected mean value of individual income when all the dependent variables are zero. Thus, in total, if the incarceration rate increased by 0.001% and the household income increased by $1000, this will result an individual income of $12,750.74.

Next, P-value is the probability that the null hypothesis is true. Here, both incarceration rate and household income have a p-values lower than 0.05. Thus, both independent variables are significant in predicting the individual income, especially, household income has a lower p-value so it is more significant in predicting the outcome.

Additionally, significance F value indicates the probability that none of the independent variables matter. Thus, here, F value of 1.1777E-109 means there’s almost no case where household income and incarceration rate are not important for predicting the individual income.

# Simple regression line and Correlation
![alt text](https://github.com/michellesykim/Prediction-of-an-individual-income-of-a-cencus-tract/blob/master/Screen%20Shot%202020-09-30%20at%2010.00.06%20PM.png)
![alt text](https://github.com/michellesykim/Prediction-of-an-individual-income-in-Washington-DC/blob/master/Screen%20Shot%202020-10-01%20at%2011.54.02%20AM.png)

As you can see from the simple regression model graphs, household income and individual income have a high R^2 value which means individual income is well explained by the household income. Also, you can see they are postiviely correlated and the data points are very close to the least squares regression line. On the other hand, incarceration rate and individual income has a relatively lower R^2 value than household income, and this means lower amount of the outcome can be explained by the incarceration rate. From the graph, you can see that they have negative correlation and data points are relatively spread out compared to the household income. This also can be explained by correlation which shows the strength of the linear relationship. Here, the correlation between the individual income and the household income is 0.97, which shows a strong positive linear relationship. Also, the correlation between the individual income and incarceration rate is -0.76 which shows a negative linear relationship between the two variables. And looking at the absolute values of the two correlations, individual income has a stronger linear relationship with household income. 

# Summary
R^2 square value being 0.94 and both p-values of incarceration rate and household income being less than 0.05 indicate that both incarceration rate and household income are good predictors of the individual income in Washington, DC and that both dependent variables do affect the individual income. Then in what way do they affect? Based on the coefficients value of the multiple regression line, **Individual income = 12,507.04 - 22,326.22*Incarceration rate + 0.467*Household income**, we can see that incarceraiton rate and individual income are negatively related and the household income and individual income are positively related. This not only shows that we can actually predict the individual income, but also supports my assumption that low household income and high incarceration rate will lower the individual income. Between the two independent variables, household income has a more significant impact on the outcome due to its high correlation with the dependent variable, its lower p-value, and its high R^2 value for simple regression line and this shows the importance of the childhood's financial circumstance since it can actually affect children individua income when they grow up. This result is important to me since it shows that there is a never ending cycle going on among low individual income, low household income, and high incarceration rate. For instance, parents with low income has a higher chance for their children to be incarcerated (result from project 1) -> Those children, after jail, are likely to have a low individual income -> When those children become parents, there is a high possibility of being parents with low income or part of the low household income -> Then, this will again lead their future children to be incarcerated with a high posiibility. For additional information, it would be helpful to know why low household income and high incarceration rate actually leads to a low individual income. Here, I quantified the realtionship among those variables, but it woud be helpful if I can know the real reason behind the outcome. Is it because they did not have enough financial resource to educate their children? Or is it because of pervasive discrimination of people out of jail in the community? Idenfifying these causes and providing solutions would help reducing or increasing the coefficients of the multiple regression line and come up with a better prediction. Knowing that there is a cycle going on between socioeconomic status and incarceration rate would allow us to identify diffrent kinds of social issues going on in our community, especially in Washington, DC. And if we are able to find effective solutions, the multiple regression line could have a totally different coefficients in the future! 




