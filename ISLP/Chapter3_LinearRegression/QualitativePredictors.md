Until now, when working both with [[SimpleLinearRegression|simple regression]] and [[MultipleLinearRegression|multiple regression]], all the predictors were quantitative. But what if a predictor is qualitative?
Let's for example suppose that we want to investigate the differences between people who own a house and people that don't, when it comes to credit card balance.

#### 1. Predictors with only one level
If a qualitative predictor (also called a *factor*) only has two possible values (*levels*), then we create what is called a ***dummy variable*** that takes two possible numerical values, for example 
$$
	x_{i}=\begin{cases}
	1,\quad\text{if the i-th observation belongs to one of the two levels (owns a house)} \\
	0, \quad\text{if the i-th observation doesn't belong to said level (does not own a house)},
	\end{cases}
$$
and we use this variable for our model, such that we end with: 
$$
	y_{i}=\beta_{0}+\beta_{1}x_{i}+\epsilon_{i}=\begin{cases}
	\beta_{0}+\beta_{1}+\epsilon_{i},\quad\text{if i-th person owns a house} \\
	\beta_{0}+\epsilon_{i},\quad\text{if they don't own a house}.
	\end{cases}
$$
The values that a dummy variable can take are arbitrary, and only change the way the model is interpreted, in particular when interpreting the coefficients.

#### 2. Predictors with more than two levels
If instead we have more than two levels, one dummy variable does not suffice. We can use multiple dummy variables, one for each level. For example, let's imagine we have three levels; south, west and east, then our dummy variables can look like this 
$$
	x_{i 1}=\begin{cases}
	1,\quad\text{if south} \\
	0,\quad\text{if not south}
	\end{cases}, \quad x_{i 2}=\begin{cases}
	1,\quad\text{if west} \\
	0,\quad\text{if not west},
	\end{cases}
$$
and thus our model would look something like this 
$$
	y_{i}=\beta_{0}+\beta_{1}x_{i 1}+\beta_{2}x_{i 2}+\epsilon_{i}=\begin{cases}
	\beta_{0}+\beta_{1}+\epsilon_{i},\quad\text{if south} \\
	\beta_{0}+\beta_{2}+\epsilon_{i},\quad\text{if west} \\
	\beta_{0}+\epsilon_{i},\quad\text{if east}.
	\end{cases}
$$
Note that for $n$ levels there's $n-1$ dummy variables, and the level without a dummy variable is called a baseline.

#statistics #ISLP #ML #regression 