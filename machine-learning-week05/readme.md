# Week 5 - Neural Networks: Learning (Exercise 4)

### [Cost Function](https://www.coursera.org/learn/machine-learning/supplement/afqGa/cost-function)



### [Backpropagation Algorithm](https://www.coursera.org/learn/machine-learning/supplement/pjdBA/backpropagation-algorithm)


Gradient Computation

[Backpropagation Intuition](https://www.coursera.org/learn/machine-learning/supplement/v5Bu8/backpropagation-intuition)

### [Implementation Note: Unrolling Parameters](https://www.coursera.org/learn/machine-learning/supplement/v88ik/implementation-note-unrolling-parameters)


```
thetaVector = [ Theta1(:); Theta2(:); Theta3(:); ]
deltaVector = [ D1(:); D2(:); D3(:) ]
```

```
Theta1 = reshape(thetaVector(1:110),10,11)
Theta2 = reshape(thetaVector(111:220),10,11)
Theta3 = reshape(thetaVector(221:231),1,11)

```


### [Random Initialization](https://www.coursera.org/learn/machine-learning/supplement/KMzY7/random-initialization)

Training a Neural Network

1. Randomly initialize the weights
2. Implement forward propagation to get hΘ(x(i)) for any x(i) 
3. Implement the cost function.
4. Implement backpropagation to compute partial derivatives
5. Use gradient checking to confirm that your backpropagation works. Then disable gradient checking.
6. Use gradient descent or a built-in optimization function to minimize the cost function with the weights in theta.

[Put it together](https://www.coursera.org/learn/machine-learning/supplement/Uskwd/putting-it-together)






