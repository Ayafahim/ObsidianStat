# Distributions

## $X^2-distribution$  
Uuafhængige normalfordelte stokastiske variable med middelværdi 0 og varians 1.

$X^2 = (n − 1)*S^2*σ^2$

## Binominal 

E[x] =  `n * p`  ;  v[x] = `n * p * (1-p`



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



