
Yi = β0 + β1xi + εi

Yi = dependant variable, random
β0 = intercept estimate (R output)
β1 = x estimate (slope) (R)
xi = explanetory variable. Given number
εi = deviation (errors). random N(0,sigma^2)

Husk hvis beta1 (altså hældningen) = 0 så er der ingen relation mellem de to variabler altså no association

### Make model if you have the data

ex from exam:

```R
# Manganese concentrations 
x <- c(0, 0, 2, 2, 4, 4, 6, 6, 8, 8, 10, 10) 
# ICP-AES values 
y <- c(114, 14, 870, 1141, 2087, 2212, 3353, 2633, 3970, 4299, 4950, 5207)

##do the linear model
lm(y ~ x)

## 
## Call:
## lm(formula = y ~ x) 
## 
## Coefficients: 
## (Intercept)       x 
##    49.19       504.33



## Get all info (summary) with p-values and stuff
fit <- lm(y ~ x) 
summary(fit)
```

### Researchers would like to know the uncertainty in ICP-AES value for a new observation with manganese concentration 5 ppb. What is the 95% prediction interval for this concentration?

```R
fit <- lm(y ~ x) 
predict(fit, newdata=data.frame(x=5), interval="prediction", level=0.95) 
## fit           lwr       upr 
## 1 2570.833  2087.363  3054.303

#lwr quantile, upr quantile
```

## Prediction of the mean #prediction


![[Pasted image 20221216190700.png]]

![[Pasted image 20221216190738.png]]


## How to estimate β0 & β1 and inteperet R output

![[Pasted image 20221214084240.png]]

Intercept - std. error = sigma_βi
t-values = tobs
Pr = p-value (if stars means there is difference and h0 isnt accepted)
#std residual standard error: XXX (sigma (variance of the error)) on XXX (df) degress of freedom
#std multiple R squared: XXX (correlation coefficent) the explained variance in the data, 
so it explains more/less than XX% of the observed variation in data. In this example it explains more than 95%.

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

# Calculated correlation
![[Pasted image 20221216102335.png]]
What is the calculated correlation between the energy demand and the GDP?

```R

### $coef$[2] = b1 så hvis ik du har data kig på estimate for b1
sd(gdp) / sd(energy) * lm(energy ~ gdp)$coef[2]


## har du datasæt så 
cor(energy, gdp)

```
