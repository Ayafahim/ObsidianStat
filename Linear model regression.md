
Yi = β0 + β1xi + εi

Yi = dependant variable, random
β0 = intercept estimate (R output)
β1 = x estimate (slope) (R)
xi = explanetory variable. Given number
εi = deviation (errors). random N(0,sigma^2)

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
tobs = βˆ0/ σˆβ0 = 3.2433/0.5483 = 5.915.


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

