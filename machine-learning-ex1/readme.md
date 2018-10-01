

# Assignment One (Week Two) Notes 

## Single Gradient Descent

There are some initialized values in this assignment - 

In file "ex1.m"
```
iterations = 1500;
alpha = 0.01;
```
And there some assumptions:
- alpha = 0.01 is not too small or too big, and it is on the right direction. 
- iterations = 1500 is good enough to find the global minimum. (the for loop just loop throught every theta and return back the last one, it assume the last one is the smallest one? )

However, when I tried to update iterations to *3500*,  it can find smaller theta, return different predictions.

- For "iterations = 1500":
```
Running Gradient Descent ...
Theta found by gradient descent:
-3.630291
1.166362
Expected theta values (approx)
 -3.6303
  1.1664

For population = 35,000, we predict a profit of 4519.767868
For population = 70,000, we predict a profit of 45342.450129
```

- For "iterations = 3500":
```
Theta found by gradient descent:
-3.888588
1.192311
Expected theta values (approx)
 -3.6303
  1.1664

For population = 35,000, we predict a profit of 2845.008261
For population = 70,000, we predict a profit of 44575.893735
```
The result are not really close, maybe that is the weakness of Gradient Descent, I guess.

## Gradient Descent for Multiple Variables

- Multiple Variables Gradient Descent and single variables Gradient Descent is very similar, the only step required for the calculation is `[X mu sigma] = featureNormalize(X);`, and returned *mu* (mean of learning sample), *sigma* (standard dev of learning sample).

- To caculate the given `X_test= [1650, 3]`, mu & sigma need to be use.

```
test_X = [1 ([1650 3] - mu) ./sigma];
```

### different learning rates
I tried the different learning rates with different iterations. 

Results show below:

"When iterations = 50, alpha = [0.003 0.01 0.03 0.1]" 
![iteration=50 Result](https://github.com/kelvinDevOp/machine-learning-course/blob/master/machine-learning-ex1/diff-lr_50.png "iteration=50")


"When iterations = 400, alpha = [0.003 0.01 0.03 0.1]" 
![iteration=400 Result](https://github.com/kelvinDevOp/machine-learning-course/blob/master/machine-learning-ex1/diff-lr_400.png "iteration=400")

As the graphs show above: 
* the smaller the learning rate, more iterations required to reach the convergency.

* more iterations tend to find the more precise theta.

### Normal Equation 

Noraml Euqation is pretty straightforward solution and it is fast when number of variables is small.(>10000, suit for most of the situation)

- Price Prediction use Normal Equation:
```
Solving with normal equations...
Theta computed from the normal equations: 
 89597.909542 
 139.210674 
 -8738.019112 

Predicted price of a 1650 sq-ft, 3 br house (using normal equations):
 $293081.464335
```
- Price Prediction use Gradient descent(iters=400):
```
Running gradient descent ...
alpha =  0.010000
num_iters =  400
Theta computed from gradient descent: 
 334302.063993 
 100087.116006 
 3673.548451 

Predicted price of a 1650 sq-ft, 3 br house (using gradient descent):
 $289314.620338

```

- Price Prediction use Gradient descent(iters=4000):
```
Running gradient descent ...
alpha =  0.010000
num_iters =  4000
Theta computed from gradient descent: 
 340412.659574 
 110631.048414 
 -6649.472406 

Predicted price of a 1650 sq-ft, 3 br house (using gradient descent):
 $293081.464741
```
- Price Prediction use Gradient descent(iters=40000):
```
Running gradient descent ...
alpha =  0.010000
num_iters =  40000
Theta computed from gradient descent: 
 340412.659574 
 110631.050279 
 -6649.474271 

Predicted price of a 1650 sq-ft, 3 br house (using gradient descent):
 $293081.464335
```

> When interation is big enough, Gradient descent's result is close or similar to Normal Equation, but Normal Equation run faster and easier (it don't need to normalize the features).




