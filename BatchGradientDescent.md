#ML #error #mean 
In Batch Gradient Descent (here onward BGD), all the training data is taken into consideration to take a single step.
We take the average of the gradients of all the training examples and use that mean gradient to update the parameters. All that just to make one step of descent in one epoch.
This approach is stable and predictable, but can be slow and require a lot of resources when facing large datasets, because you need to process the entire dataset before updating the parameters.

#### Advantages
One of the main advantages of BGD is that it converges to the optimal solution in a stable and consisten way. This is very useful for convex optimization problems where the error surface (given by the error function) is smooth and the convergence is steady.
All this reduces the risk of fluctuations an instability when computing the coefficient estimates for our model.
#### Drawbacks
The main disadvantage of BGD is the high computational cost for large datasets. It's obvious that processing the whole data set each time that we want to take a step is not a practical nor efficient process, even if doing so leads to more precise predictions.
This high computational cost limits the practicality of BGD in the real world, and the trade off between computational efficiency and precision becomes an important subject.

#### Implementation (Linear Regression)
For the implementation example, we'll see the case for [[MultipleLinearRegression|linear regression]]. Suppose that we have $n$ training observations, each one consisting of $p$ predictors.
Recall that our cost function for linear regression is the [[AssessingModelAccuracy|MSE]] given by 
$$
	J(\theta)=\frac{1}{n}\sum_{i=1}^{n}(y_{i}-\hat{y}_{i})^{2},
$$
where $\hat{y}_{i}=\theta x_{i}$, for $\theta$ our $1\times p+1$ coefficients vector, and $x_{i}$ our $p+1\times 1$ vector corresponding to the $i$-th observation. (The +1 comes from the slope term or bias).
