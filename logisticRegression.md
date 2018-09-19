## Logistic Regression

Links:
http://scikit-learn.org/stable/modules/linear_model.html#logistic-regression


Logistic regression is also known in the literature as logit regression,
**maximum-entropy classification (MaxEnt)** or the **log-linear classifier**.

In this model, the probabilities describing the possible outcomes of a single
trial are modeled using a logistic function.

The implementation in sklearn can fit **binary**, **One-vs-Rest**, or
**multinomial logistic regression** with optional **L2** or **L1** 
regularization.

As an optimization problem, binary class L2 penalized logistic regression minimizes the following cost function:
![L2 reg](http://scikit-learn.org/stable/_images/math/760c999ccbc78b72d2a91186ba55ce37f0d2cf37.png)


