An *input variable* $X$ is basically a set of data that we can analyse. Also called *predictors*, independent variables, features, or just variables.
An *output variable* $Y$ is a set of "results" that we assume are dependent on our predictors. Also called *response* or dependent variable.

### Why estimate $f$?
Given the response $Y$ and a set of $p$ different predictors $X=\{X_{1}, X_{2}, \dots, X_{p}\}$, we assume that there's a relationship between $Y$ and $X$, which can be written as 
$$
	Y = f(x) + \epsilon.
$$
Here, $f$ is a fixed unknown function and $\epsilon$ is a random error term, which is independent from $X$ and has mean zero. 
Thus, what we want to do is estimate a function $\hat{f}\approx f$, usually for one of the following two reasons: [[Prediction]] or [[Inference]].
Prediction is when we want to approximate a value for a specific $y\in Y$ given certain predictors $x\in X$. On the other hand, inference is when we want to understand the relation between $X$ and $Y$.
Modeling can be conducted towards one or both prediction and inference.

### How to estimate $f$?
Let's say we have a set of $n$ different data points called our *training data*, used to teach our model how to estimate $f$. Let $x_{ij}$ be the $i$-th observation for the $i$-th predictor, $i=1,\dots,n$, $j=1,\dots ,p$. And let $y_{i}$ be the response for the $i$-th observation. Then our training set looks like this: 
$$
	\{(x_{1},y_{1}),(x_{2},y_{2}),\dots(x_{n},y_{n})\}\quad\text{where}\quad x_{i}=\begin{bmatrix}
	x_{i 1} \\
	. \\
	. \\
	. \\
	x_{i p}
	\end{bmatrix}.
$$
We want to find $\hat{f}$ such that $Y\approx \hat{f}(X)$ for any pair $(X,Y)$. Most statistical learning methods can be categorized as either [[ParametricMethods|parametric]] or [[NonParametricMethods|non-parametric]] methods.
In parametric methods, we assume $f$ to have a specific form, and we build from there, where as in the non-parametric methods, we make no assumptions about the true form of $f$. Both approaches have different advantages and disadvantages, which leads us to the next topic.

### Accuracy vs Interpretability
A "*flexible*" method is one that can reproduce many shapes to estimate $f$, and an "*interpretable*" method is one that is better for inference, mostly because it is easier to understand.
If a particular method is very flexible, it increases the risk of overfitting the data, and sometimes it is better to use a less flexible, but more interpretable method.
The next graph shows how some methods are more flexible but gain interpretability, and vice-versa:
![[Pasted image 20260809183555.png]]
(Deep learning would be somewhere in the bottom right corner of the graph).

### Supervised vs Unsupervised Learning
This are the main types of "*learning*" that are covered in the ISLP book, although there's other types of learning more modern such as reinforcement learning. The main types are:
- Supervised learning: when for each observation of the predictor, there is an associated response.
- Unsupervised learning: we have the predictor observations, but we do not have the responses.
- Semi-supervised learning: we know the response for only some of the predictors.

### Regression vs Classification
Variables can be either *quantitative* or *qualitative*, and although the type of variables of the predictor are less important, whether the response is qualitative or qualitative is an important topic.
- *Regression*: problems that have a quantitative response.
- *Classification*: problems with a qualitative response.
Some methods target one or the other, and there's some methods that work for both cases.


#ISLP #statistics 


