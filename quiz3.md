# Solutions to Quiz 3

## Question 1
In a population of interest, a sample of 9 men yielded a sample average brain volume of 1,100cc and a standard deviation of 30cc. What is a 95% Student's T confidence interval for the mean brain volume in this new population?

### Solution to Question 1
```
> xbar <- 1100
> sd <- 30
> n <- 9
> xbar + c(-1, 1) * qt(0.975, n-1) * (sd / sqrt(n))
[1] 1076.94 1123.06
```

## Question 2
A diet pill is given to 9 subjects over six weeks. The average difference in weight (follow up - baseline) is -2 pounds. What would the standard deviation of the difference in weight have to be for the upper endpoint of the 95% T confidence interval to touch 0?

### Solution to Question 2
```
> xbar <- -2
> n <- 9
> xbar * sqrt(n) / qt(0.975, n-1)
[1] -2.601903
```

## Question 3
In an effort to improve running performance, 5 runners were either given a protein supplement or placebo. Then, after a suitable washout period, they were given the opposite treatment. Their mile times were recorded under both the treatment and placebo, yielding 10 measurements with 2 per subject. The researchers intend to use a T test and interval to investigate the treatment. Should they use a paired or independent group T test and interval?

### Solution to Question 3
```
A paired interval
```


## Question 4
In a study of emergency room waiting times, investigators consider a new and the standard triage systems. To test the systems, administrators selected 20 nights and randomly assigned the new triage system to be used on 10 nights and the standard system on the remaining 10 nights. They calculated the nightly median waiting time (MWT) to see a physician. The average MWT for the new system was 3 hours with a variance of 0.60 while the average MWT for the old system was 5 hours with a variance of 0.68. Consider the 95% confidence interval estimate for the differences of the mean MWT associated with the new system. Assume a constant variance. What is the interval? Subtract in this order (New System - Old System).


### Solution to Question 4
```
> xbar_old <- 5
> var_old <- 0.68
> n_old <- 10
> 
> xbar_new <- 3
> var_new <- 0.6
> n_new <- 10
> 
> pooled_var <- (((n_old - 1)*var_old) + ((n_new - 1)*var_new)) / (n_old + n_new - 2)
> 
> (xbar_new - xbar_old) + c(-1, 1) * qt(0.975, n_old + n_new - 2) * sqrt(pooled_var) * sqrt((1 / n_old) + (1 / n_new))
[1] -2.751649 -1.248351
```


## Question 5
Suppose that you create a 95% T confidence interval. You then create a 90% interval using the same data. What can be said about the 90% interval with respect to the 95% interval?

### Solution to Question 5
```
