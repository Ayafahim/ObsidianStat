
![[Pasted image 20221214143350.png]]


# One sample/paired t-test

## Calculate t-value (tobs) and p-value

```R
##t-statistic

tobs <- (mean(x) - mu) / (sd(x) / sqrt(n))

## p-value

2*(1-pt(abs(tobs),df))
## df = n-1

## or do t.test that calculates everything:

t.test(x, mu=7725)

##husk mu er den mu for nul-hypotesen (mu = 0 by default)
```

