# One sample sample size formula
![[Pasted image 20221216185744.png]]


```R
## The formula 
zb <- qnorm(0.9) 
za <- qnorm(1-0.05/2) 
delta <- -0.05 
sigma <- 3.5 
(sigma * (zb+za)/delta)^2

```


## Eks af power test (one sample)

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

## Power test (two sample/pooled variance)

f, in a new experiment, it is wanted to obtain a strength of 80% to be able to detect one difference of 4 kg between the two groups of on a confidence level of 99%, and the weighted variance is used as a guess of the population’s variance, how many pigs should at least be included in this experiment?

Pooled variance = $5.0^2$

1. Udregn pooled variance hvis ik du har: [[Pooled stuff]]
```R
power.t.test(delta=4, sd=5.0, sig.level=0.01, power=0.8)$n 
## [1] 38.19

## $n viser kun n værdi.

###HUSK ikke færdig, da svar er kun for en gruppe vi har to grupper her så 39*2 = 78 som er svar.

## Fra facit: which rounded up means that there must be 39 pigs in each group and thus in total there must be 78 pigs included in the experiment.
```

# Opg med konklusion
![[Pasted image 20221216192712.png]]