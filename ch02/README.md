## Chapter 2 - Statistical Learning


### Bayes error rate:
* In classification, test error rate is minimized when instance is assigned to most likely class, given its covariates. I.e,. instance with covariate vector `x_0` will be assigned to class `j` for which:

`Pr(Y = j | X = x_0)`

is maximum

* This classifier is called `Bayes Classifier` and gives the lowest possible test error rate (`Bayes error rate`)
* Overall Bayes error rate is:

`1 - E(max_j Pr(Y=j | X) )`

where E is over all possible values for X

* Cannot use Bayes classifier in practice because we don't know `P(Y|X)`
* So estimate P(Y|X) and classify instance with highest `estimated P(Y|X)`, e.g., `KNN`

**Ref:**
* ISLR, Section 2.2 (Bayes classifier)


### K Nearest Neighbors

* Given `K > 0` and instance `x_0`, identify `K` points in training data closest to `x_0`
* Calculate conditional probability `P(Y = j | X = x_0)` for each class as number of points in K that fall in class `j`.
* Then apply Bayes classifier and assign instance `x_0` to class with largest conditional probability
* Choice of `K` has large impact on nature of classifier obtained. Small `K` => high variance, low bias; large `K` => low variance, high bias

**Ref:**
* ISLR, Section 2.2 (Bayes classifier)
