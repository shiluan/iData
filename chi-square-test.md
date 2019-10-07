##chi-square test

With observations about two categorical variables determine if they are independent.

example: people's holiday preference: men, beach 

```
var1: gener = {men|women}
var2: preference = {beach, cruise}
observations = {men:{beach:209, cruise:280},women:{beach:225, cruise: 248}}
The question: is gener independent to preference?
```
To answer the question we use a Chi-square test.

```
chi-sqr = sum((O-E)^2/E), 
where E = {row_total * col_total / overall_total} 
```
```
total_observation = 209+280+225+248 = 962
total_observation_men = 209+280 = 489
total_observation_women = 225+248 = 473
total_observation_cruise = 280+248 = 528
total_observation_beach = 209+225 = 434
```
Expected (E) = {men:{beach:489*434/962, cruise:489*528/962}, women:{beach:473*434/962, cruise:473*528/962}}
 = {men:{beach:220.61, cruise:268.39}, women:{beach:213.39, cruise:259.61}}

chi-sqr = (209-220.61)^2/220.61 + (280-268.39)^2/268.39 + (225-213.39)^2/213.39 + (248-259.61)^2/259.61 = 0.61 + 0.50 + 0.63 + 0.52 = 2.26
 
degree of freedom (DF) = (rows - 1)*(cols - 1) = (2-1)*(2-1) = 1

p-value = 0.132754 (online calculator: https://www.socscistatistics.com/pvalues/chidistribution.aspx)

Since p-value > 0.05, we can't conclude that gender affects preference. i.e. gender and preference are independent. In other words, men and women probably do not have a different preference.


Reference:
https://www.mathsisfun.com/data/chi-square-test.html
