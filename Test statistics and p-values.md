
### Relationship between t-statistic and CI

Answer from an exam:
Method 7.22. The test statistic is greater than the given 0.95 quantile, so the null hypothesis of no difference between groups (no change across years) is rejected, and the change is concluded to be significant.

Så altså hvis test ikke ligger i intervallet givet så afvises nul-hypotesen


![[Pasted image 20221214143350.png]]

When p-value is above sig. level h0 is accepted

# Test-statistics
```R
## one sample t-dist, for hypothesis
tobs <- (mean(x) - mu) / (sd(x) / sqrt(n))

### tobs with R
# 99% quantile

qt(quantile = 0.995,df = 24)

t.test(x, mu=7725)
##husk mu er den mu for nul-hypotesen (mu = 0 by default)

###Normal dist z-stat
##### ~ N(0,1^2)

#R
qnorm(quantile)

##uden R
zobs <- (mean(x) - mu) / (var(x) / sqrt(n))



##Chi-square test statistic
df = (r-1)*(c-1)
qchisq(quantile = 0.995,df)

## or do test
data <- matrix(c(11,27,15,14,40,30,5,23,35), ncol = 3, byrow =TRUE) 
chi <- chisq.test(training, correct = FALSE) 
chi

##F-dist (ANOVA)
##fobs = test statistic

## k = antal grupper, n = antal observationer i alt.

### fobs
qf(quantile,df1 = k-1 ,df2 = n-k)
## df1 = df treatment & df2 = df residuals

```

## P-values

```R
## p-value t-dist
### df = n-1

2*(1-pt(abs(tobs),df))

##chi-square
1-pchisq(10.985,df))


##f-dist (ANOVA)
1 - pf(fobs, k-1, n-k)

```


## 2 sample paired
### df = n-1 hvor n er observationer for en gruppe

```R
tobs <- (mean(x-y) - h0) / sqrt((sd(x)^2/length(x)) + (sd(y)^2/length(y)))
```




## 2 Samples independant/welch test

```R
tobs <- (mean(x-y) - h0) / sqrt((sd(x)^2/length(x)) + (sd(y)^2/length(y)))

##df
s1 <-
n1 <-
s2 <-
n2 <-
v <- (s1^2/n1 + s2^2/n2)^2 / ( (s1^2/n1)^2/n1-1 + (s2^2/n2)^2/n2-1 )
v
```

### df
![[Pasted image 20221215100058.png]]


# Opgaver

## What statement is right? (signifikant difference?)

![[Pasted image 20221215105118.png]]

![[Pasted image 20221215105136.png]]



![[Pasted image 20221216182043.png]]


![[Pasted image 20221216182407.png]]
