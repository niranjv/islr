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

# Transpose data set to center observations, not covariates
us.scaled <- scale(t(USArrests))

# Euclidean distance between states
eud <- dist(t(us.scaled))

# Correlation distance between states
cord <- as.dist(1-cor(us.scaled))

# Plot shows strong non-linear relationship between the 2 sets of values
plot(eud, cord, main="USArrests: distance between scaled observations", xlab="Euclidean distance", ylab="Correlation distance")
lines(lowess(eud, cord), lwd=2, col='red')
abline(lm(cord~eud), col='blue', lwd=2)
legend("bottomright", legend=c("linear model", "lowess"), col=c("blue", "red"), lwd=2)
```

![](ch10-ex_files/figure-markdown_github-ascii_identifiers/Ex7-1.png)

``` r
# Correlation between the 2 distances is also very high
cor(eud, cord)
```

    ## [1] 0.9449967

------------------------------------------------------------------------

### Exercise 8

``` r
us.scaled <- scale(USArrests)

# PVE from output of prcomp
pc <- prcomp(us.scaled, center=TRUE, scale=TRUE)
pve1 <- summary(pc)$importance[2,]

# PVE from Eq. 10.8
x <- us.scaled %*% pc$rotation
component_var <- apply(x^2, 2, sum)
total_var <- sum(apply(us.scaled^2, 2, sum))
pve2 <- component_var/total_var

# Both sets of values are equal up to roundoff error
pve1-pve2 < 10^-5
```

    ##  PC1  PC2  PC3  PC4 
    ## TRUE TRUE TRUE TRUE

------------------------------------------------------------------------

### Exercise 9

------------------------------------------------------------------------

### Exercise 10

------------------------------------------------------------------------

### Exercise 11
