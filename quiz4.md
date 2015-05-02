# Solutions to Quiz 3

## Question 1
A pharmaceutical company is interested in testing a potential blood pressure lowering medication. Their first examination considers only subjects that received the medication at baseline then two weeks later. The data are as follows (SBP in mmHg)

|Subject  |Baseline  |Week 2 |
|:-------:|:--------:|:-----:|
|1	  |140	     |132    |
|2        |138       |135    |
|3        |150	     |151    |
|4	  |148	     |146    |
|5	  |135	     |130    |

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


## Question 2
A sample of 9 men yielded a sample average brain volume of 1,100cc and a standard deviation of 30cc. What is the complete set of values of μ0 that a test of H0:μ=μ0 would fail to reject the null hypothesis in a two sided 5% Students t-test?

### Solution to Question 2
```
> n <- 9 
> m0 <- 1100
> sd <- 30
> 
> m0 + c(-1, 1) * qt(.975, n - 1) * sd / sqrt(n)
[1] 1076.94 1123.06
```


## Question 3
Researchers conducted a blind taste test of Coke versus Pepsi. Each of four people was asked which of two blinded drinks given in random order that they preferred. The data was such that 3 of the 4 people chose Coke. Assuming that this sample is representative, report a P-value for a test of the hypothesis that Coke is preferred to Pepsi using a one sided exact test.

### Solution to Question 3
```
binom.test(3, 4, alt= "greater")$p.value
```


## Question 4
Infection rates at a hospital above 1 infection per 100 person days at risk are believed to be too high and are used as a benchmark. A hospital that had previously been above the benchmark recently had 10 infections over the last 1,787 person days at risk. About what is the one sided P-value for the relevant test of whether the hospital is *below* the standard?

### Solution to Question 4
```
poisson.test(x = 10, T = 1787, r = 1/100, alternative = "less")$p.value
```


## Question 5
Suppose that 18 obese subjects were randomized, 9 each, to a new diet pill and a placebo. Subjects’ body mass indices (BMIs) were measured at a baseline and again after having received the treatment or placebo for four weeks. The average difference from follow-up to the baseline (followup - baseline) was −3 kg/m2 for the treated group and 1 kg/m2 for the placebo group. The corresponding standard deviations of the differences was 1.5 kg/m2 for the treatment group and 1.8 kg/m2 for the placebo group. Does the change in BMI appear to differ between the treated and placebo groups? Assuming normality of the underlying data and a common population variance, give a pvalue for a two sided t test.

### Solution to Question 5
```
> se <- sqrt((1.5^2 * 8 + 1.8^2 * 8) / 16 * (1/9 + 1/9)) 
> z <- (-3 + 1) / se
> pnorm(z) * 2
[1] 0.01044502
```


## Question 6
Brain volumes for 9 men yielded a 90% confidence interval of 1,077 cc to 1,123 cc. Would you reject in a two sided 5% hypothesis test of H0:μ=1,078?

### Solution to Question 6
```
