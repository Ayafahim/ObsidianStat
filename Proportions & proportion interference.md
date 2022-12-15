
## Estimation of single proportions

![[Pasted image 20221215122306.png]]

Hvor p0 = sum af hele kolonne.




## 2 sample proportion hypothesis test

![[Pasted image 20221215112656.png]]

Hvor 
n = sum of all
x = sum of all in category

# Example:
![[Pasted image 20221215105856.png]]

## Give a 99% confidence interval for the total proportion of drunk driving accidents in 2010, where you use the relevant normal distribution approximation.
![[Pasted image 20221215105935.png]]

Husk
```R
##z-quantile for 99%
qnorm(0.995)
```

![[Pasted image 20221215112423.png]]


![[Pasted image 20221215105332.png]]


![[Pasted image 20221215112444.png]]


# Test for no change in distribution

Do a chi-square test

```R
data <- matrix(c(data for alle colums), ncol) 
chisq.test(data)
## se p-værdi o samlign med signifikans-level
```

# What is estimated proportion
OBS. Husk alt med hat er estimates uden hat er population

opg eks

![[Pasted image 20221215113332.png]]

Estimates er uafhængie af år så derfor tages for alle år.
formel: phat=x/n