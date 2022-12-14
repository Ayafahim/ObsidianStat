
## R interpertation 
![[Pasted image 20221214081622.png]]

MSE = Mean sq :: Residuals

## Post hoc hypthesis test


![[Pasted image 20221214080205.png]]


```r
tobs <- (meani-meanj)/sqrt(MSE*(1/ni+1/nj))

##Example
tobs <- (127-135)/sqrt(74.97*(1/20+1/20)) = -2.291
```



## Bonferroni corrected LSD

![[Pasted image 20221214082024.png]]

```R
LSD <- t1-a/2*sqrt(2*MSE/m)
## m = n pr. gruppe

t1-a/antal grupper/2 
## step by step
## 3 antal grupper

0.05/3 = 0.017
1-0.017/2 = 0.9916667
df = 60(n) - 3
tstat <- qt(0.9916667,57) = 2.466689

2.466689*sqrt(2*74.97/20) = 6.753955 = 6.8
```

Så der er signifikant forskel hvis der er over 6.8 ml forskel mellem gennemsint pr gruppe:

So we can use that to determine which of the three waiters will be tested significantly different in two-sample post hoc comparisons. We have information about the average for each waiter: 
x¯A = 127 mL ; x¯B = 135 mL ;  x¯C = 136 mL from which we can see that A is significantly different from B and C, since their differences are higher than 7 mL, and that there is no significant difference between B and C.
