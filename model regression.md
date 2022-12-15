
Yi = β0 + β1xi + εi

Yi = dependant variable, random
β0 = intercept estimate (R output)
β1 = x estimate (slope) (R)
xi = explanetory variable. Given number
εi = deviation (errors). random N(0,sigma^2)

Husk hvis beta1 (altså hældningen) = 0 så er der ingen relation mellem de to variabler altså no association

### How to estimate β0 & β1 and inteperet R output

![[Pasted image 20221214084240.png]]

Intercept - std. error = sigma_βi
t-values = tobs
Pr = p-value (if stars means there is difference and h0 isnt accepted)
residual standard error: XXX (sigma) on XXX (df) degress of freedom
multiple R squared: XXX (correlation coefficent)
df = n-2


## Find intercept t-value

tobs = intercept estimate/ intercept std. error
eks:
tobs = $β0/ σ_β0 = 3.2433/0.5483 = 5.915.$



## Confidence intervals

```R
###confidence interval for the mean###
##1-signifikans/2
##fx. for 99% interval er sig = 0.01
1-0.01/2
### 99%

b0 + c(-1,1)*qt(p=0.995,df=n-2)*std.error_b0
## or
b1 + c(-1,1)*qt(p=0.995,df=n-2)*std.error_b1

```

## Prediction intervals

![[Pasted image 20221215120053.png]]

```R
## 90% 
beta0 + beta1 * xnew c(-1,1)*qt(p=0.95,df=n-2)*sigma*sqrt(1+(1/n)+(xnew-mean())^2/Sxx)

##where

Sxx <- (n-1)*var(beta1)
```

## Homogeneity i plots

![[Pasted image 20221215125925.png]]

Jo mere box agtige of ligeligt fordelt jo mere homogents så model1 nej men model2 ja.