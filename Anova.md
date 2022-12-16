![[Pasted image 20221215132749.png]]


# Do ANOVA test if given data

```R
## Data given
y <- c(1.89, 2.35, 1.68, 2.11, 3.15, 2.16, 2.40, 2.59, 1.54, 2.02, 2.01, 2.11)
## group the observations, rep(groupname,observations in group)
grp<-c(rep("a",4),rep("b",4),rep("c",4))
## anova
anova(lm(y~grp))

```

## R interpertation 

![[Pasted image 20221214081622.png]]

![[Pasted image 20221215101906.png]]

## F-statistic
![[Pasted image 20221215102910.png]]

![[Pasted image 20221215133040.png]]
So MSE = Sigmahat

```R
fobs <- (SS(Tr)/(k-1))/(SSE/(n-1))

## hvis du har MS(tr) og MSE
fobs <- (MS/MSE)

```

## P-value 

#### Test statistic

![[Pasted image 20221215132854.png]]


```R 
1 - pf(fobs, k-1, n-k)

##fobs = test statistic

## k = antal grupper, n = antal observationer i alt.

### fobs
qf(quantile,df1 = k-1 ,df2 = n-k)
## df1 = df treatment & df2 = df residuals

```

## Post hoc hypthesis test


![[Pasted image 20221214080205.png]]


```r

MSE <- SSE/(n-k)
## hvor k er antal nivauer/grupper
## n er antal obeservationer
tobs <- (mean(i)-mean(j))/sqrt(MSE*(1/ni+1/nj))

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

Så der er signifikant forskel hvis der er over 6.8 ml forskel mellem gennemsnit pr gruppe:

So we can use that to determine which of the three waiters will be tested significantly different in two-sample post hoc comparisons. We have information about the average for each waiter: 
x¯A = 127 mL ; x¯B = 135 mL ;  x¯C = 136 mL from which we can see that A is significantly different from B and C, since their differences are higher than 7 mL, and that there is no significant difference between B and C.

