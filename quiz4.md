# Solutions to Quiz 3

## Question 1
A pharmaceutical company is interested in testing a potential blood pressure lowering medication. Their first examination considers only subjects that received the medication at baseline then two weeks later. The data are as follows (SBP in mmHg)

|Subject  |	Baseline  |Week 2 |
|:-------:|:---------:|:-----:|
|1	      |140	      |132    |
|2	      |138        |135    |
|3	      |150	      |151    |
|4	      |148	      |146    |
|5	      |135	      |130    |

Consider testing the hypothesis that there was a mean reduction in blood pressure? Give the P-value for the associated two sided T test.

### Solution to Question 1
```
> week1 <- c(140, 138, 150, 148, 135)
> week2 <- c(132, 135, 151, 146, 130)
> 
> t.test(week1, week2, alternative = "two.sided", paired = T)

	Paired t-test

data:  week1 and week2
t = 2.2616, df = 4, p-value = 0.08652
alternative hypothesis: true difference in means is not equal to 0
95 percent confidence interval:
 -0.7739122  7.5739122
sample estimates:
mean of the differences 
                    3.4 
  ```
