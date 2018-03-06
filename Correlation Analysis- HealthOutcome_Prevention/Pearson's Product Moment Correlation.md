### Description 

The Pearson product-moment correlation coefficient is a measure of the strength of the linear relationship between two variables.
The Pearson correlation coefficient, r, can take a range of values from +1 to -1. A value of 0 indicates that there is no 
association between the two variables. A value greater than 0 indicates a positive association; that is, as the value of one 
variable increases, so does the value of the other variable.


### Create a corelation between Health Outcomes and Prevention measures
cor_HealthOutcome_Prevention <- cor.test(mergedHealthOutcome_Prevention$Population_Health_Outcomes, 
                                         mergedHealthOutcome_Prevention$Population_Prevention_Category, 
                                         method = "pearson")

#### Print correlation
cor_HealthOutcome_Prevention

#### Pearson's product-moment correlation

#### data:  mergedHealthOutcome_Prevention$Population_Health_Outcomes and mergedHealthOutcome_Prevention$Population_Prevention_Category
 t = 48.663, df = 3, p-value = 1.911e-05
alternative hypothesis: true correlation is not equal to 0
95 percent confidence interval:
0.9899304 0.9999604

#### sample estimates:
cor 
0.9993672 
