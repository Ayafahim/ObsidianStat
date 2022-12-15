
## Eks af power test

![[Pasted image 20221215125613.png]]

```R
## Husk at delta skal konverteres hvis den ik er samme enhed som desired mean

##delta = forskel
power.t.test(power = 0.9, delta = 0.05, sd = 0.11, sig.level = 0.01, type = "one.sample") 
## 
## One-sample t test power calculation 
## 
##     n = 75.36328 
##     delta = 0.05 
##     sd = 0.11 
##     sig.level = 0.01 
##     power = 0.9 
##     alternative = two.sided
```
