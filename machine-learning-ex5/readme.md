# [Week 6 - Advice for Applying Machine Learning (Exercise 5)](https://www.coursera.org/learn/machine-learning/home/week/6)


## Main Topics

- Improving learning algorithm
- Machine Learning System Design

#### Evaluating a learning Algorithm

Machine Learning diagnostic

[Evaluating a hypothesis](https://www.coursera.org/learn/machine-learning/supplement/aFpD3/evaluating-a-hypothesis)

The new procedure using these two sets is then:

1. Learn \ThetaΘ and minimize Jtrain(Θ) using the training set
2. Compute the test set error Jtest(Θ)


[Model Selection and Traing/Validation/Test Sets](https://www.coursera.org/learn/machine-learning/supplement/XHQqO/model-selection-and-train-validation-test-sets)

Separate Dataset to 3 parts:
1. Training set (60%)
2. Cross validation set (20%)
3. test set (20%)

We can now calculate three separate error values for the three different sets using the following method:

1. Optimize the parameters in Θ using the training set for each polynomial degree.
2. Find the polynomial degree d with the least error using the cross validation set.
3. Estimate the generalization error using the test set with J test(Θ (d)), (d = theta from polynomial with lower error);

This way, the degree of the polynomial d has not been trained using the test set.


#### [Diagnosing Bias vs. Variance](https://www.coursera.org/learn/machine-learning/supplement/81vp0/diagnosing-bias-vs-variance)

*High bias (underfitting)*: both J train(Θ) and J CV(Θ) will be high. Also, J CV(Θ)≈J train(Θ).

*High variance (overfitting)*: J train(Θ) will be low and J CV(Θ) will be much greater than J train(Θ).

#### [Regularization and Bias/Variance](https://www.coursera.org/learn/machine-learning/supplement/JPJJj/regularization-and-bias-variance)


#### [Deciding What to Do Next Revisited](https://www.coursera.org/learn/machine-learning/supplement/llc5g/deciding-what-to-do-next-revisited)

**Our decision process can be broken down as follows:**

* Getting more training examples: Fixes high variance
* Trying smaller sets of features: Fixes high variance
* Adding features: Fixes high bias
* Adding polynomial features: Fixes high bias
* Decreasing λ: Fixes high bias
* Increasing λ: Fixes high variance.

##### Model Complexity Effects:

- Lower-order polynomials (low model complexity) have high bias and low variance. In this case, the model fits poorly consistently.
- Higher-order polynomials (high model complexity) fit the training data extremely well and the test data extremely poorly. These have low bias on the training data, but very high variance.
- In reality, we would want to choose a model somewhere in between, that can generalize well but also fits the data reasonably well.


















