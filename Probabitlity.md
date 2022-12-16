# Distributions

## $X^2-distribution$  
Uuafhængige normalfordelte stokastiske variable med middelværdi 0 og varians 1.

$X^2 = (n − 1)*S^2*σ^2$


## R kommando forskelle

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

# Different probability commands for over or under value:

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








## Poisson opg

![[Pasted image 20221215114608.png]]






## Exp opg

![[Pasted image 20221215114722.png]]

## Normal opg (What is the probability that a randomly selected piece from pile 1 weighs more than 25 kg?)
![[Pasted image 20221215120851.png]]
