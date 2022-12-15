### Relationship between t-statistic and CI

Answer from an exam:
Method 7.22. The test statistic is greater than the given 0.95 quantile, so the null hypothesis of no difference between groups (no change across years) is rejected, and the change is concluded to be significant.

Så altså hvis test ikke ligger i intervallet givet så afvises nul-hypotesen


![[Pasted image 20221214143350.png]]


# One sample t-dist.

## Calculate t-value (tobs) and p-value

```R
##t-statistic

tobs <- (mean(x) - mu) / (sd(x) / sqrt(n))

### tobs with R
# 95% quantile

qt(quantile = 0.995,df = 24)

## p-value

2*(1-pt(abs(tobs),df))
## df = n-1

## or do t.test that calculates everything:

t.test(x, mu=7725)

##husk mu er den mu for nul-hypotesen (mu = 0 by default)
```

## Z-statistic

```R
zobs <- (mean(x) - mu) / (var(x) / sqrt(n))

## ~ N(0,1^2)
```

## 2 sample paired
### df

```R
tobs <- (mean(x-y) - h0) / sqrt((sd(x)^2/length(x)) + (sd(y)^2/length(y)))
```

![[Pasted image 20221215100459.png]]



## 2 Samples independant/welch test

```R
tobs <- (mean(x-y) - h0) / sqrt((sd(x)^2/length(x)) + (sd(y)^2/length(y)))
```

### df
![[Pasted image 20221215100058.png]]


# Opgaver

## What statement is right? (signifikant difference?)

![[Pasted image 20221215105118.png]]

![[Pasted image 20221215105136.png]]



