ISLR, Chapter 10
================

-   [Exercise 1](#exercise-1)
-   [Exercise 2](#exercise-2)
-   [Exercise 3](#exercise-3)
-   [Exercise 4](#exercise-4)
-   [Exercise 5](#exercise-5)
-   [Exercise 6](#exercise-6)
-   [Exercise 7](#exercise-7)
-   [Exercise 8](#exercise-8)
-   [Exercise 9](#exercise-9)
-   [Exercise 10](#exercise-10)
-   [Exercise 11](#exercise-11)

### Exercise 1

------------------------------------------------------------------------

### Exercise 2

------------------------------------------------------------------------

### Exercise 3

------------------------------------------------------------------------

### Exercise 4

------------------------------------------------------------------------

### Exercise 5

------------------------------------------------------------------------

### Exercise 6

------------------------------------------------------------------------

### Exercise 7

``` r
data(USArrests)

# Center observations, not covariates
us.scaled <- scale(t(USArrests))

# Euclidean distance
eud <- dist(t(us.scaled))

# Correlation distance
cord <- as.dist(1-cor(us.scaled))

# Plot shows strong non-linear relationship between the 2 sets of values
plot(eud, cord, main="USArrests: distance between scaled observations", xlab="Euclidean distance", ylab="Correlation distance")
lines(lowess(eud, cord), lwd=2, col='red')
abline(lm(cord~eud), col='blue', lwd=2)
legend("bottomright", legend=c("linear model", "lowess"), col=c("blue", "red"), lwd=2)
```

![](ch10-ex_files/figure-markdown_github-ascii_identifiers/Ex7-1.png)

``` r
# Their correlation is also very high
cor(eud, cord)
```

    ## [1] 0.9449967

------------------------------------------------------------------------

### Exercise 8

------------------------------------------------------------------------

### Exercise 9

------------------------------------------------------------------------

### Exercise 10

------------------------------------------------------------------------

### Exercise 11
