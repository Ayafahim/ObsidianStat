# One sample/paired

## Calculate t-value (tobs) and p-value

```R
##t-statistic

tobs <- (mean(x) - mu) / (sd(x) / sqrt(n))

## p-value

2*(1-pt(abs(tobs),df))
## df = n-1
```


