## Logistic Regression

Links:
* http://scikit-learn.org/stable/modules/linear_model.html#logistic-regression

* https://stats.idre.ucla.edu/other/mult-pkg/faq/general/faq-how-do-i-interpret-odds-ratios-in-logistic-regression/

* 


Logistic regression is also known in the literature as logit regression,
**maximum-entropy classification (MaxEnt)** or the **log-linear classifier**.

In this model, the probabilities describing the possible outcomes of a single
trial are modeled using a logistic function.

The implementation in sklearn can fit **binary**, **One-vs-Rest**, or
**multinomial logistic regression** with optional **L2** or **L1** 
regularization.

As an optimization problem, binary class L2 penalized logistic regression minimizes the following cost function:
![L2 reg](http://scikit-learn.org/stable/_images/math/760c999ccbc78b72d2a91186ba55ce37f0d2cf37.png)


Similarly, L1 regularized logistic regression solves the following optimization problem

![L1 reg](http://scikit-learn.org/stable/_images/math/6a0bcf21baaeb0c2b879ab74fe333c0aab0d6ae6.png)

The solvers implemented in this class are *liblinear*, *newton-cg*, *lbfgs*, *sag*, *saga*

The solver “liblinear” uses a coordinate descent (CD) algorithm, and relies on the excellent C++ LIBLINEAR library, which is shipped with scikit-learn. However, the CD algorithm implemented in liblinear cannot learn a true multinomial (multiclass) model; instead, the optimization problem is decomposed in a “one-vs-rest” fashion so separate binary classifiers are trained for all classes. This happens under the hood, so LogisticRegression instances using this solver behave as multiclass classifiers. For L1 penalization sklearn.svm.l1_min_c allows to calculate the lower bound for C in order to get a non “null” (all feature weights to zero) model.

The “lbfgs”, “sag” and “newton-cg” solvers only support L2 penalization and are found to converge faster for some high dimensional data. Setting multi_class to “multinomial” with these solvers learns a true multinomial logistic regression model [5], which means that its probability estimates should be better calibrated than the default “one-vs-rest” setting.

The “sag” solver uses a Stochastic Average Gradient descent [6]. It is faster than other solvers for large datasets, when both the number of samples and the number of features are large.

The “saga” solver [7] is a variant of “sag” that also supports the non-smooth penalty=”l1” option. This is therefore the solver of choice for sparse multinomial logistic regression.

Case	Solver
L1 penalty	“liblinear” or “saga”
Multinomial loss	“lbfgs”, “sag”, “saga” or “newton-cg”
Very Large dataset (n_samples)	“sag” or “saga”


|          case          |          solver        |
|:----------------------:|:----------------------:|
|        L1 penalty      |     liblinear, saga    |
|    multinomial loss    |lbfgs, sag, saga, newton-cg|
|  very large dataset(n_samples)  |    sag, saga      |


