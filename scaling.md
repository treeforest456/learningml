# Scaling

## Standardization

* What is 
	- Standardization of datasets is a common requirement for many machine learning estimators implemented in scikit-learn; they might behave badly if the individual features do not more or less look like standard normally distributed data: Gaussian with zero mean and unit variance.


* why do standardization
	- For instance, many elements used in the objective function of a learning algorithm (such as the RBF kernel of Support Vector Machines or the l1 and l2 regularizers of linear models) assume that all features are centered around zero and have variance in the same order. If a feature has a variance that is orders of magnitude larger than others, it might dominate the objective function and make the estimator unable to learn from other features correctly as expected.

* Scaling features to a range
	- MinMaxScaler or MaxAbsScaler
	- The motivation to use this scaling include robustness to very small standard deviations of features and preserving zero entries in sparse data.

* Scaling **sparse** data
	- Centering sparse data would destroy the sparseness structure in the data, and thus rarely is a sensible thing to do. However, it can make sense to scale sparse inputs, especially if features are on different scales.
	- MaxAbsScaler and maxabs_scale were specifically designed for scaling sparse data, and are the recommended way to go about this. However, scale and StandardScaler can accept scipy.sparse matrices as input, as long as *with_mean=False* is explicitly passed to the constructor. Otherwise a ValueError will be raised as silently centering would break the sparsity and would often crash the execution by allocating excessive amounts of memory unintentionally.

* Scaling data with outliers
	- If your data contains many outliers, scaling using the mean and variance of the data is likely to not work very well. In these cases, you can use robust_scale and RobustScaler as drop-in replacements instead. They use more robust estimates for the center and range of your data.

* Scaling vs Whitening
	- It is sometimes not enough to center and scale the features independently, since a downstream model can further make some assumption on the linear independence of the features.
	- To address this issue you can use sklearn.decomposition.PCA with whiten=True to further remove the linear correlation across features.

## Non-linear transformation

* Mapping to a Uniform distribution

* Mapping to a Gaussian distribution


## Normalization

* Normalization is the process of scaling individual samples to have unit norm. This process can be useful if you plan to use a quadratic form such as the dot-product or any other kernel to quantify the similarity of any pair of samples.

* original data: 3, 4, 5
	- (9+16+25)^(1/2) = 7.07
	- 3/7.07, 4/7.07, 5/7.07

* often used on text classification, since one sentece could be like
	'how are you doing' --> [233, 456, 789, 432]

* 