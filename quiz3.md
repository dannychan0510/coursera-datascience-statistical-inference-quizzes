# Solutions to Quiz 3

## Question 1
In a population of interest, a sample of 9 men yielded a sample average brain volume of 1,100cc and a standard deviation of 30cc. What is a 95% Student's T confidence interval for the mean brain volume in this new population?

### Solution to Question 1
```
> 1100 + c(-1, 1) * qt(0.975, 9 - 1) * 30
[1] 1030.82 1169.18
```
