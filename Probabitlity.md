
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


