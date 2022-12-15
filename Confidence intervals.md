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

### Confidence interval for std. deviation

Her skal man lave for begge ender. 
Se eksempel: 

```R
## for 99% CI
## 0.5% på hver side derfor 99.5% på ende ende og 0.5% på anden
sqrt( (n-1)*sd(x)^2/qchisq(0.995, df = n-1) )
sqrt( (n-1)*sd(x)^2/qchisq(0.005, df = n-1) )
```

### Condfidence  interval for variance

```R
## for 90% 
## samme med to ender gøres li som i std. deviation
((n-1)*sd()^2)/chisq(0,950,df=n-1)

((n-1)*sd()^2)/chisq(0,050,df=n-1)
```

## 2 Sample

## CI for paired t-test (mean)
```R
##take diff of both sample means

t.test(diff)
```



### Confidence interval for difference in μ1 and μ2 (indipendent)

```R
mean(x-y) + c(-1,1)*qt(p=0.995,df)*sqrt(sd(x)^2/length(x)-sd(y)^2/length(y))

## or welch

t.test(x,y)
```

remember df:

![[Pasted image 20221215100058.png]]


# Opgave eksempler

## Which of the following choices yields an estimate for the median of X1/X2 and a 95% confidence interval for this median?

![[Pasted image 20221215103947.png]]

Man skal bare tage de kvartiler som passer fx: for 95% så er det 2.5% og 97.5%, da der er 2.5% på hver side.
For 90% havde det fx været 5% og 95%

