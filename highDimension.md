# Dimensionality

* Let’s say we have n samples (a.k.a. data points, instances) and p features (a.k.a. attributes, independent variables, explanatory variables). So many people are holding the imprecise opinion that high dimensional data is simply a data set with a very large p.

Then, please tell me whether p=1000 means high dimensional data. In modern machine, 1000 features is not a big deal, but I believe it sounds pretty high dimension to many people.

In fact, “high dimension” has a very rigorous meaning: it means a data set whenever p>n, no matter what p is or n is. Because in statistics, you will never have deterministic answer when p>n unless you introduce your own assumption.

For example, if you have 3 data points, and 5 features each, it’s a high dimensional data. On the other hand, even if you have 500k features, once you have 1M samples, it’s still low dimensional.

Try to come up with some dummy examples then you should be able to figure out that the 2nd case is a much less challenging problem than the 1st case.


* ISLR page 203
	- Prediction Accuracy: Provided that the true relationship between the response and the predictors is approximately linear, the least squares estimates will have low bias. If n >> p—that is, if n, the number of observations, is much larger than p, the number of variables—then the least squares estimates tend to also have low variance, and hence will perform well on test observations. However, if n is not much larger than p, then there can be a lot of variability in the least squares fit, resulting in overfitting and consequently poor predictions on future observations not used in model training. And if p>n, then there is no longer a unique least squares coefficient estimate: the variance is infinite so the method cannot be used at all. By constraining or shrinking the estimated coefficients, we can often substantially reduce the variance at the cost of a negligible increase in bias. This can lead to substantial improvements in the accuracy with which we can predict the response for observations not used in model training.

	- https://medium.com/@jennifer.zzz/more-features-than-data-points-in-linear-regression-5bcabba6883e
	- This is a very good medium reference

