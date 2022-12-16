Se [[Distributions]] for formler osv

## Bootstrapping
parametric bootstrap = simulate multiple samples from the assumed distribution
Non-parametric bootstrap: simulate multiple samples directly from the data

### Example of what is non-paramatric bootstrapping #bootstrap
![[Pasted image 20221216180252.png]]

The differences in the answers are: 
• replace: must be TRUE 
• quantiles calculated: they must be 2.5% and 97.5% to have the right significance level with 95% percent in between

# Distributions examples

# Possion
![[Pasted image 20221216113425.png]]






## R kommando forskelle #probability

```R
#disse er for bogstaver p og q bar udskift norm med hvad end passer

### if u want probability of something
pnorm()
## Hvis du har fået en sandsynelighed men skal kende værdien for noget med den.
qnorm()
## eks
##There is a 20% probability of a randomly selected piece of rock from pile 2 being heavier than?

##siden der er 20% hevier skal vi finde mindste værdien/resterende 80% så for 1-0.2 = 0.8
qnorm(0.8, mean = 50, sd = 10)
## [1] 58.41621
### altså der er 20% sandsynlighed for at vælge en sten tungere 58.41621kg

```

# Different probability commands for over or under value: #

```R
#These are examples, switch out the command with rigth distribution

## P(X <= 5)
pbinom(5,10,0.6)

## P(X < 5)
pbinom(4,10,0.6)

## P(X > 4)
1 - pbinom(4,10,0.6)

## P(X = 5)
pbinom(5,10,0.6) - pbinom(4,10,0.6)

```

## Normal distributed population:

### Has mean XX & std. deviation XX, what is prob for random draw of observation under 90?

Let X ∼ N(mean, std ). Then, we may find P(X < 90) = P(X ≤ 90) as:

```R
pnorm(90, mean = 100, sd = 15)

## [1] 0.2524925
```


## If a random sample of n = 10 independent observations is drawn from the population, what is the probability that the sample mean is below 90?

![[Pasted image 20221214101927.png]]

```R
pnorm(90, mean = 100, sd = sqrt(22.5)) 

## [1] 0.017507
```


# Probability that the sample mean is greater?

![[Pasted image 20221216092438.png]]

Theorem 3.3

R-kode
```R
#Her er 5 & 2 den mean og sd vi har fået. Divider sd med sqrt(sample mean)
## og self 1-pnorm fordi det skal være højere.
1-pnorm(4.5, mean=5, sd=2/sqrt(25))
```



# Propagation of error #mangler

# The non-linear approximative error propagation rule

![[Pasted image 20221216093015.png]]

### Eksempel på brug:
![[Pasted image 20221216093242.png]]

OBS. fordi det er std. deviation skal den i kvadratrod. Husk også at sørge for sigmai og xi er samme.
![[Pasted image 20221216093634.png]]

Her skal hvert led sættes ind i formlen: 
![[Pasted image 20221216093742.png]]

Sæt ind i formel:
$9x^4*σ_1^2+25*σ_2^2$
![[Pasted image 20221216094014.png]]



# Poisson opg

![[Pasted image 20221215114608.png]]






## Exp opg

![[Pasted image 20221215114722.png]]

## Normal opg (What is the probability that a randomly selected piece from pile 1 weighs more than 25 kg?)
![[Pasted image 20221215120851.png]]

# You buy 100 R1 resistors - which can be assumed to be independent of each other. What is the probability that none of these has a resistance below 3 ohms?
![[Pasted image 20221216171755.png]]
![[Pasted image 20221216171826.png]]

# Calculate an estimate of sd of the total XX for a model

## Example 1:
Assume that R1 ∼ N(4, 0.2) and R2 ∼ N(2, 0.2).

```R
k <- 1000000 
## de to variabler i modellen
R1 <- rnorm(k, mean=4, sd=sqrt(0.2)) 
R2 <- rnorm(k, mean=2, sd=sqrt(0.2)) 

##Husk at skrive modellen som du har fået
R <- 1 / (1/R1 + 1/R2) 

#udregn sd baseret på simuleringer af modellen
sd(R)
```

## Example 2:
![[Pasted image 20221216111104.png]]

```R
##Siden std normal dist. N ~ 
k <- 1000000 
x1 <- rnorm(k,0,1) 
x2 <- rnorm(k,0,1)

### formel for Y
sd(exp(x1) + x2^4 + x1*x2) 
## [1] 10.05853