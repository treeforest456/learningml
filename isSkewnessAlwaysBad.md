## is skewness always bad?

* source 
https://stats.stackexchange.com/questions/299154/the-benefit-of-unskewing-skewed-data

	- First, ordinary least squares regression makes no assumptions about the dependent variable being normally distributed; it make assumptions about the errors being normal and the errors are estimated by the residuals. However, when the dependent variable is as skewed as yours is, the residuals usually will be too.
	- Third, I think data should be transformed for substantive reasons, not statistical ones. Here, and for price data more generally, it often makes sense to take the log. Two reasons are that 1) People often think about prices in multiplicative terms rather than additive ones - the difference between $2,000,000 and $2,001,000 is really small. The difference between $2,000 and $2,100 is much bigger. 2) When you take logs, you can't get a negative predicted price

* There's no good or bad for skewness. It might violate some of the assumptions of a test.

* soruce:
http://oak.ucc.nau.edu/rh232/courses/eps625/handouts/data%20transformation%20handout.pdf

	- Most people find it difficult to accept the idea of transforming data. Tukey (1977) probably had the  right  idea  when  he  called  data  transformation  calculations  “reexpressions”  rather than “transformations.” A researcher is merely reexpressing what the data have to say in other terms. 
	- You should not get the impression that data transformation should be applied routinely to all your data. As a rule of thumb, 'if it's not broken, don't fix it'.

* from wikipedia https://en.wikipedia.org/wiki/Data_transformation_(statistics)
	- Transforms are usually applied so that the data appear to more closely meet the assumptions of a statistical inference procedure that is to be applied, or to improve the interpretability or appearance of graphs

* source https://stats.stackexchange.com/questions/267078/why-is-skewed-data-not-preferred-for-modelling
	- When removing skewness, transformations are attempting to make the dataset follow the Gaussian distribution. The reason is simply that if the dataset can be transformed to be statistically close enough to a Gaussian dataset, then the largest set of tools possible are available to them to use. Tests such as the ANOVA, t-test, F-test, and many others depend on the data having constant variance (σ2) or follow a Gaussian distribution.
	- In decision trees I'll first point one thing: there's no point on transforming skewed explanatory variables, monotonic functions won't change a thing; this can be usefull on linear models, but's not on decision trees. This said, CART models use analysis of variance to perform spits, and variance is very sensible to outliers and skewed data, this is the reason why transforming your response variable can considerably improve your model accuracy.


* not finishing reading
	- https://stats.stackexchange.com/questions/107610/what-is-the-reason-the-log-transformation-is-used-with-right-skewed-distribution
	- https://becominghuman.ai/how-to-deal-with-skewed-dataset-in-machine-learning-afd2928011cc
	- https://www.google.com/search?client=ubuntu&hs=fjq&channel=fs&q=how+skewness+effect+machine+learning+models&spell=1&sa=X&ved=0ahUKEwi38o2V1P7ZAhVCh1QKHcbPDgMQBQgmKAA&biw=1855&bih=959
	- https://www.quora.com/What-are-assumptions-for-classification-algorithms
	- http://www.fusioninvesting.com/2010/09/what-is-skew-and-why-is-it-important/
	- http://www.styleadvisor.com/resources/statfacts/skewness
	- http://fmwww.bc.edu/repec/bocode/t/transint.html
	
