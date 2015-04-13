# Question 1
What is the variance of the distribution of the average an IID draw of n observations from a population with mean μ and variance σ2.

## Solution to Question 1
```
((σ)^2)/n
```


# Question 2
Suppose that diastolic blood pressures (DBPs) for men aged 35-44 are normally distributed with a mean of 80 (mm Hg) and a standard deviation of 10. About what is the probability that a random 35-44 year old has a DBP less than 70?

## Solution to Question 2
```
> pnorm(70, mean = 80, sd = 10)
[1] 0.1586553
```

# Question 3
Brain volume for adult women is normally distributed with a mean of about 1,100 cc for women with a standard deviation of 75 cc. What brain volume represents the 95th percentile?

## Solution to Question 3
```
> qnorm(0.95, mean = 1100, sd = 75)
[1] 1223.364
```

# Question 4
Refer to the previous question. Brain volume for adult women is about 1,100 cc for women with a standard deviation of 75 cc. Consider the sample mean of 100 random adult women from this population. What is the 95th percentile of the distribution of that sample mean?

## Solution to Question 3
```
