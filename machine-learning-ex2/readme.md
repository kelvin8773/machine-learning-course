# Machine Learning (Week Three) Notes

### Classification Problem

Example:
- Email: Spam/Not Spam ?
- Online Transacations: Fraudulent(Yes/No)?

Can't use Liniear regression method

### logistic function

probability that y=1, given X, parameterized by theta.

hθ(x)=P(y=1|x;θ)=1−P(y=0|x;θ)
P(y=0|x;θ)+P(y=1|x;θ)=1

### Decision Boundary

### [Cost Function](https://www.coursera.org/learn/machine-learning/supplement/bgEt4/cost-function)

#### [Simplified Cost Function and Gradient Descent](https://www.coursera.org/learn/machine-learning/supplement/0hpMl/simplified-cost-function-and-gradient-descent)

J = 1/m * Sum(Cost)

Cost = -y * log(h(x)) - (1-y) * log(1 -h(x))

minimize J --> get theta 

#### [Advanced Optimiztion](https://www.coursera.org/learn/machine-learning/supplement/cmjIc/advanced-optimization)

Optimization algorithm
- gradient descent
- Conjugate gradient
- BFGS
- L-BFGS

Advantages:
* No need to manually pick alpha.
* Often faster than gradient descent.

Disadvantages:
- More complex.

Cost Function
```Octave
function [jVal, gradient] = costFunction(theta)
  jVal = [...code to compute J(theta)...];
  gradient = [...code to compute derivative of J(theta)...];
end
```
optimization Function
```Octave
options = optimset('GradObj', 'on', 'MaxIter', 100);
initialTheta = zeros(2,1);
   [optTheta, functionVal, exitFlag] = fminunc(@costFunction, initialTheta, options);
```

### [Multiclass Classification: One Vs. All](https://www.coursera.org/learn/machine-learning/supplement/HuE6M/multiclass-classification-one-vs-all)

>Train a logistic regression classifier hθ(x) for each class￼to predict the probability that y = i.
>To make a prediction on a new x, pick the class ￼that maximizes hθ(x).

### [The Problem of Overfitting](https://www.coursera.org/learn/machine-learning/supplement/VTe37/the-problem-of-overfitting)

*Overfitting* - too many features to find the right solution.

*** solution ***
1. Reduce number of features.
- manually select which features to keep
- Model selection algorithm
2. Regularization
- keep all the features, but reduce the magnitude/values of parameters.
- Work well when we have a lot of features.


#### [Regulization and Cost Function](https://www.coursera.org/learn/machine-learning/supplement/1tJlY/cost-function)

[Regularized Linear Regression](https://www.coursera.org/learn/machine-learning/supplement/pKAsc/regularized-linear-regression)


[Regularized Logistic Regression](https://www.coursera.org/learn/machine-learning/supplement/v51eg/regularized-logistic-regression)


## Assignment

Same as last week's assigment, most of the work is figure out how to conver the formula into *Octave/Matlab* code.

1. Warmup Exercise: Sigmoid Function -

```
g = 1 ./ (1 + e.^ (-1 * z));
```

2. Cost function and gradient

```
J = (1/m) * (-y' * log(sigmoid(X * theta)) - (1 - y)' * log(1-sigmoid(X * theta)));

grad = (1/m) * X'* (sigmoid(X*theta) - y);

```

3. Cost function and gradient with regulation
```

J = (1/m) * (-y' * log(h) - (1 - y)' * log(1-h) + (lambda/2) * reg_theta' * reg_theta);

grad = (1/m) * ( X' * (h - y) + lambda * reg_theta);
```

4. Final (ungraded excise - Change the lamda)
```
lambda = 0
Train Accuracy: 86.440678
Expected accuracy (with lambda = 1): 83.1 (approx)
```
"When lamba=0, Accuracy = 86" 
![lambda = 0](https://github.com/kelvinDevOp/machine-learning-course/blob/master/machine-learning-ex2/b_lamda0.png "lambda=0")

```
lambda =  1
Train Accuracy: 83.050847
Expected accuracy (with lambda = 1): 83.1 (approx)
```
"When lamba=1, Accuracy = 83" 
![lambda = 1](https://github.com/kelvinDevOp/machine-learning-course/blob/master/machine-learning-ex2/b_lamda1.png "lambda=1")

```
lambda =  10
Train Accuracy: 74.576271
Expected accuracy (with lambda = 1): 83.1 (approx)
```
"When lamba=10, Accuracy = 74" 
![lambda = 10](https://github.com/kelvinDevOp/machine-learning-course/blob/master/machine-learning-ex2/b_lamda10.png "lambda=10")

```
llambda =  100
Train Accuracy: 61.016949
Expected accuracy (with lambda = 1): 83.1 (approx)
```
"When lamba=100, Accuracy = 61" 
![lambda = 100](https://github.com/kelvinDevOp/machine-learning-course/blob/master/machine-learning-ex2/b_lamda100.png "lambda=100")


