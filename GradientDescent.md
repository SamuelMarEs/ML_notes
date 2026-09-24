#ML #error 
Gradient descent is a core machine learning algorithm used to minimize the [[AssessingModelAccuracy|cost function]] of a model. It helps adjust the model's parameters iteratively to reduce errors and improve the model's performance. 

There's three primary types of gradient descent:
1. [[BatchGradientDescent|Batch Gradient Descent]] (BGD): uses the entire dataset to compute the gradient and update the parameters of the model.
2. [[StochasticGradientDescent|Stochastic Gradient Descent]] (SGD): uses a single random data point per iteration, making updates noisier but faster.
3. [[Mini-BatchGradientDescent|Mini-Batch Gradient Descent]]: It's like a midpoint in between BGD and SGD, using small batches of data per update.

#### The Hill Metaphor
Let's imagine that we are standing on a hill, we want to reach the lowest valley, but the weather is foggy, and the night is dark and full of terrors, so we don't know which way to go.
However, we can see and feel a small area around us. So, hat we do, is that we find the steepest downward slope, and take a small step in that direction, rinse and repeat.
This way, eventually we'll find a valley, although there's the possibility that it wasn't the lowest one.

#### The Gradient
Let $f:\mathbb{R}^{n}\to \mathbb{R}$ be a function who's partial derivatives $\frac{\partial f}{\partial x_{1}}, \frac{\partial f}{\partial x_{2}}, \dots, \frac{\partial f}{\partial x_{n}}$ exist. The ***gradient*** of $f$ is the vector of its partial derivatives, that is 
$$
	\nabla f=\left( \frac{\partial f}{\partial x_{1}}, \frac{\partial f}{\partial x_{2}},\dots, \frac{\partial f}{\partial x_{n}} \right).
$$
(The notation $\nabla$ is called nabla).
The gradient of a function at a certain point always points in the direction of steepest ascent "upwards". So, gradient descent computes the gradient at a certain point, and moves in the opposite direction (negative gradient).

#### Epochs and Learning rate
An ***epoch*** is one step. The number of epochs is the number of steps that we are taking in order to try and reach the bottom of the valley. In our algorithm, each epoch is one iteration of the algorithm.
One the other hand, the ***learning rate*** indicates how much can each epoch change the parameters. It's the size of each step. If the steps we take are very big, then we run the risk of overshooting the bottom, while if the steps are very small, then we can take a very long time to reach it. 

#### The math
Let $J(\theta)$ be our cost/loss function given a set of parameters $\theta$. Let's say we have a training data set of $n$ observations. In most cases, this loss function is the [[AssessingModelAccuracy|mean squared error]], given by 
$$
	J(\theta)=\frac{1}{n}\sum_{i=1}^{n}(y_i-\hat{f_{\theta}}(x_i)),
$$
where $\hat{f}_{\theta}(x_{i})$ is the predicted value for observation $x_{i}$ given the parameters $\theta$, and $y_{i}$ is the actual known value for said observation.

Given this loss function, the standard formula for gradient descent is 
$$
	\theta_{k+1}=\theta_{k}-\alpha \nabla J(\theta_{k}),
$$
where 
- $\theta_{k}$ is the current position vector of the parameters (weights and biases) at iteration $k$,
- $\theta_{k+1}$ is the updated position/parameters for the next iteration,
- $\alpha$ is the learning rate (a small positive scalar), and lastly
- $\nabla J(\theta_{k})$ is the gradient of our cost function $J$ evaluated at the current parameters $\theta_{k}.$
Note that the minus sign on the gradient ensures that we are moving downwards and not upwards.

#### The algorithm
The way the algorithm works can be summarized in the following four steps:
1. **Initialize:** We begin by initializing the parameters at a random guess $\theta_{0}$.
   
2. **Calculate Gradient:** We compute the derivative $\nabla J$ of the cost function to determine the "slope" and the direction of increase.
   
3. **Update:** Subtract a portion of the gradient (determined by the learning rate $\alpha$) from out current position/parameters.
   
4. **Repeat:** We iterate the process until the values converge near the minimum error.

