

## Comparing several groups
HUSK!
```R
df = (row-1)*(column -1)
```


## Calculate expected number in cell under null-hypothesis

![[Pasted image 20221215123228.png]]

Eksempel med tabel fra eksempel med elever:

Assuming independence between year and discipline, the expected number of newly enrolled students in TechNat in the year 2017 is estimated to be:

![[Pasted image 20221215123446.png]]

```R
c_total <- 22+15
g_Total <-18+11+22+9+38+ 36+ 15+ 12
r_total <-18+11+22+9

c_total * r_total/g_Total
```

## Estimation of single proportions

![[Pasted image 20221215122306.png]]

Hvor p0 = sum af hele kolonne.

### Eksempel

Based on the numbers for 2017, one wants to test the hypothesis that the proportion of students newly enrolled in a technical or natural science bachelor education (TechNat) is 32.0%. The relevant test statistic for this hypothesis, which is assumed to be well approximated by a standard normal distribution, is?
![[Pasted image 20221215122523.png]]

Her er p0 = 30193 da vi skal kigge på alle elever startet i 2017.
Hvor x = alle dem der startede i technat det år
```R
(10339 - 0.32 * 30193) / sqrt(30193 * 0.32 * 0.68)

## mere genereltt

(x-n*p0)/sqrt(n * po * (1-po))

```


## 1  proportion confidence

![[Pasted image 20221215112656.png]]

Hvor 
n = sum of all
x = sum of all in category

```R
x <-
n <-
phat <- x/n
phat1 <- 1-phat

phat + c(-1,1) * qnorm(0.975) * sqrt((phat*phat1)/n)

```


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

```R
x1 <-
n1 <-
x2 <-
n2 <-

phat <- (x1+x2)/(n1+n2)
phat1 <-x1/n1
phat2 <-x2/n2

zobs <- (phat1-phat2)/sqrt(phat*(1-phat)*(1/n1+1/2))


```



![[Pasted image 20221215112444.png]]

```R
x1 <-
n1 <-
x2 <-
n2 <-

prop.test(c(x1,x2), c(n1,n2), correct = FALSE)

```






# Test for no change in distribution

Do a chi-square test

```R
data <- matrix(c(data for alle colums), ncol) 
chisq.test(data)
## se p-værdi og samlign med signifikans-level
```

# What is estimated proportion
OBS. Husk alt med hat er estimates uden hat er population

opg eks

![[Pasted image 20221215113332.png]]

Estimates er uafhængie af år så derfor tages for alle år.
formel: phat=x/n

# Estimated Standard Error (sigmahat)

```R
## Først udregn estimated proportion hvis ik du har (phat)
phat <- x/n
sqrt((phat*(1-phat))/n)

### Eksempel
## In China x1 = 1920 answered yes out of n1 = 2000 people being asked, and in Denmark x2 = 1801 answered yes out of n2 = 2024 people being asked.
# What is the estimate of the standard error of the estimated proportion who answered yes in Denmark?

phat <- 1801/2024
sqrt((phat*(1-phat))/2024)

#[1] 0.006959748

```


# Estimate Sample Size for a proportion

![[Pasted image 20221215124849.png]]

Where ME = half of the expected width of CI
fx:

How many days does the experiment need to run in order to obtain a 95% confidence interval for the proportion of components to be discarded, which has an expected width of 5 percentage points?
$ME = 0.05/2 = 0.025$

# Difference of two proportions estimator phat1 − phat2 and confidence interval for the difference

![[Pasted image 20221216154123.png]]


```R
  x1 <-23
  n1 <-90
  x2 <-35
  n2 <-40
phat1 <-x1/n1
phat2 <-x2/n2

sigmahat <- sqrt( (phat1*(1-phat1))/n1 + (phat2*(1-phat2))/n2 )

(phat1-phat2) + c(1,-1) * qnorm(0.995) * sigmahat

```
