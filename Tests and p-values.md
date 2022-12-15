
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


## 2 Samples independant 

```R
tobs <- (mean(x-y) - h0) / sqrt((sd(x)^2/length(x)) + (sd(y)^2/length(y)))

##df
v <- (sd(x)^2/length(x) + sd(y)^2/length(y))/ s