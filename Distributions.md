
## Binominal

E[x] =  `n * p`  ;  v[x] = `n * p * (1-p)`

## Poisson

![[Pasted image 20221216191753.png]]
![[Pasted image 20221216191904.png]]



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

![[Pasted image 20221216210728.png]]


## Normal Distribution

### Standard Normal Distribution/ z-dist.

Standard normal distrubtion always have mean 0 and sd = variance = 1
#std 

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
![[Pasted image 20221216193243.png]]


![[Pasted image 20221216193313.png]]
```R 
## Calculate mean 
alpha <- 1 
beta <- 0.7
## 
xseq <- seq(0.1, 10, by=0.1) plot(xseq, dlnorm(xseq, meanlog=alpha, sdlog=beta), type = "l") ## 
exp(alpha+beta^2/2)
```

```R
## Calculate the  variance
alpha<-
beta<-
sigma2<- exp^(2*alpha+beta)*(exp^(beta^2)-1)
```

```R
## hvis man vil se hvordan den ser ud til graf opg
x <- rlnorm(100) 
qqnorm(x) 
qqline(x)

```

The answer is A. In B, the sample has more small values as well as more large values. The sample in C has fewer small values and fewer large values. The sample in D seems to be normal distributed
![[Pasted image 20221216194044.png]]
