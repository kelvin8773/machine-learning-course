# Machine Learning (Week Three) Notes

## Classification Problem

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

## [Multiclass Classification: One Vs. All](https://www.coursera.org/learn/machine-learning/supplement/HuE6M/multiclass-classification-one-vs-all)

>Train a logistic regression classifier hθ(x) for each class￼to predict the probability that y = i.
>To make a prediction on a new x, pick the class ￼that maximizes hθ(x).









