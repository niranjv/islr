## Chapter 10 - Unsupervised Learning

### Objectives

* Visualization of high dimensional data
* Discover structure / sub-groups


### Properties

* Strong subjective element
* Often performed during *EDA*


### PCA

* Summarize high dimensional data with a smaller number of representative variables (i.e., principal components) that explain most of the variability in the data set
* PC directions are the directions in which the data set is most variable
* PCA = process by which PCs are computed & the use of these PCs
* Does not involve response `Y`, if available
* Each PC is a linear combination of all `p` features in the data set

**Computing PCs:**

?


** PC Regression: **

* Regress on the PCs instead of the full data set, i.e., on the `n x M` matrix, where `M << p` are the first `M` PC score vectors instead of the `n x p` data matrix
* Advantage is less noisy results since signal is usually concentrated in the first few PCs


**Ref:**

* ISLR, Section 10.2 (PCA)
