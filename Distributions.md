
## Binominal

E[x] =  `n * p`  ;  v[x] = `n * p * (1-p)`

## Poisson

## $X^2$-distribution  
Uuafhængige normalfordelte stokastiske variable med middelværdi 0 og varians 1.

$X^2 = (n − 1)*S^2*σ^2$

$X_a$ ; a = mean

```R
df <- (r − 1)(c − 1)
## r = row, c = column
```

## Exponiential

![[Pasted image 20221216094153.png]]
![[Pasted image 20221216094131.png]]
#### Example : estimate the rate
her husk at omdanne til rigtige enhed:
```R
## Vi har fået
mean(x1) 
## [1] 2.76 
mean(x2) 
## [1] 0.897
```

Da lamda = mu så ville man tænke svar 1 men husk at omregne til enhed hvis det er spurgt om.
![[Pasted image 20221216094640.png]]



## Uniform Distribution

Formula
```R
mu <- 1/2*(alpha+beta)

var <- 1/12*(beta-alpha)^2

## where interval fx [0;1] 
## 0 = alpha & 1 = beta
```

Ex of problem:
A random variable X follows a uniform distribution on the interval [0; 1]. The expected value and the variance of (X + 2) · 4 is?

The transformed variable is uniformly distributed on [8, 12] so by Eq. 2-52 and 2-53 the answer is: $µ = 1/2*(12 − 8) = 10$ and $σ^2 = 1/12*(12 − 8)*2 = 16 12 = 4 3$

![[Pasted image 20221216185255.png]]

The probability is always 1 with an uniform distrubution. The probability is the same. 
## Normal Distribution

### Standard Normal Distribution/ z-dist.

Standard normal distrubtion always have mean 0 and sd = variance = 1

![[Pasted image 20221216110058.png]]


## Hypergeometrisk 
A distrubution is hypergeometrisk when there is no " laying back" (tilbagelægning) fx, when you draw random cards.
![[Pasted image 20221216191408.png]]

![[Pasted image 20221216192733.png]]

```R
dhyper(x = SomeValue, m = SomeValue, n = SomeValue, k = SomeValue)
## x = Number of draws without replacement
## m = Number of success left
## n = Number of failures left
## k = Number of draws from the urn  
```

## Log dist.

```R
## hvis man vil se hvordan den ser ud til graf opg
x <- rlnorm(100) 
qqnorm(x) 
qqline(x)

```

