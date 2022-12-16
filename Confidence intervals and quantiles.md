[[Test statistics and p-values]]  🌘

### Hvis mean for nulhypotese fx h0 = 0 ikke ligger i CI så er den afvist. og der må være signifikant forskel!!


# Critical level i.e $X^2$- distribution

```R
(df <- (r-1)*(c-1)) 

##this is for sig. level = 0.01
qchisq(0.99, df) 

## [1] 9.21034
```


## Quantiles
![[Pasted image 20221215113931.png]]


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

### Confidence interval for the mean

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
![[Pasted image 20221215193522.png]]
```R
## for 90% 
## samme med to ender gøres li som i std. deviation
((n-1)*sd()^2)/qchisq(0.950,df=n-1)

((n-1)*sd()^2)/qchisq(0.050,df=n-1)
```

## 2 Sample

## CI for paired t-test (mean)
```R
##take diff of both sample means

t.test(diff)
```
----

### Confidence interval for difference in μ1 and μ2 (indipendent)
![[Pasted image 20221215123959.png]]

```R
mean(x-y) + c(-1,1)*qt(p=0.995,df)*sqrt(sd(x)^2/length(x)-sd(y)^2/length(y))

## or welch

t.test(x,y)
```

HVIS, du fx ik har et at ledene fx det i kvadratrod, så isoler for at finde. 
Eksempel:

 95 percent confidence interval: [1.4316 ; 3.2592]

![[Pasted image 20221215124134.png]]

![[Pasted image 20221215124213.png]]


------


## Parametric bootstrap CI

![[Pasted image 20221215121920.png]]

En R-kommando kan bruges hvis der er kørt en simulation og vi har koden:

```R
##Givet kode
set.seed(7643) 
k <- 10000 R1 <- rnorm(k, mean = 2, sd = 0.2) 
R2 <- rnorm(k, mean = 3, sd = 0.5) 
R <- 1/(1/R1 + 1/R2)

## Tilføj kommando og find CI for fx 95%
quantile(R, c(0.025,0.975))
##   2.5%       97.5% 
## 0.9647361  1.4016874
```


Eks:
Using the results above and the book’s definition of percentiles (“type = 2” in R), which of the following is a 95% bootstrap confidence interval for the population mean?

![[Pasted image 20221215114147.png]]





remember df:

![[Pasted image 20221215100058.png]]


# Opgave eksempler

## Which of the following choices yields an estimate for the median of X1/X2 and a 95% confidence interval for this median?

![[Pasted image 20221215103947.png]]

Man skal bare tage de kvartiler som passer fx: for 95% så er det 2.5% og 97.5%, da der er 2.5% på hver side.
For 90% havde det fx været 5% og 95%

