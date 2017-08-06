ISLR, Chapter 3
================

### Exercise 1

-   **Intercept** - Are there any sales in the absence of all advertising (Yes)
-   **TV** - Does TV advertising have an impact on sales (Yes; 46 additional units sold for every $1000 spent on TV ads)
-   **radio** - Does radio advertising have an impact on sales (Yes; 189 additional units sold for every $1000 spent on radio ads)
-   **newspaper** - Does newspaper advertising have an impact on sales (No; p-value = 0.86)

### Exercise 2

Difference between KNN classification vs. KNN regression:

**KNN classification** - Used to predict the class of a point from its covariates. From the labelled training set, take the `K` points that are nearest to the new point in covariate space. The class of the new point is the class that is most common in the `K` points.

**KNN regression** - Used to predict the response of a point from its covariates. From the labelled training set, select the `K` nearest neighbors in covariate space. The response of the point to predict is the average of the response of these `K` points.

### Exercise 3

Linear model:

`Salary = 50 + 20*GPA + 0.07*IQ + 35*Gender + 0.01*GPA:IQ - 10*GPA:Gender`

`Gender: Male = 0, Female = 1`

*a:* `F = 35 - 10*GPA`

`M = 0`

`M - F = 0 - (35 - 10*GPA) = 10*GPA - 35`

Males earn more than females on average only the fixed GPA is &gt; 3.5

*b:* Salary of female with IQ=110, GPA=4 is

``` r
50 + 20*4 + 0.07*110 + 35*1 + 0.01*4*110 - 10*4*1 
```

    ## [1] 137.1

*c:* Support for interaction effect is provided by its associated p-value. If p-value is low, then there is evidence for an interaction effect. Also, since scale of IQ is much larger than that of the other covariates(1-100+ vs 1-4 & 0-1), the coefficient for interaction will be small.
