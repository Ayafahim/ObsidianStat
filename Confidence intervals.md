[[Tests and p-values]]  🌘


## Normal dist. one sample

### Calculate percentiles
```R
1-signifikans/2
## fx. for 99% interval er sig = 0.01
1-0.01/2
```

Allerede udregnet populære quantiles:
- 99% -> 0.995
- 95% -> 0.975
- 90% ->  0.95

## Confidence interval for the mean

```R
## ex for 99%
mean()+ c(-1,1)*qt(p=0.995,df=n-1)*sd()/sqrt(n)
```

## Confidence interval for std. deviation

Her skal man lave for begge ender. 
Se eksempel: 

```R
## for 99% CI
## 0.5% på hver side derfor 99.5% på ende ende og 0.5% på anden
sqrt( (n-1)*sd()^2/qchisq(0.995, df = n-1) )
sqrt( (n-1)*sd()^2/qchisq(0.005, df = n-1) )
```

## Condfidence  interval for variance

```R
## for 90% 
## samme med to ender gøres li som i std. deviation
((n-1)*sd()^2)/chisq(0,950,df=n-1)

((n-1)*sd()^2)/chisq(0,050,df=n-1)
```

