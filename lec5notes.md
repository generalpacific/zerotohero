# Introduction

Implementing WaveNet. Why? 
* Since the validation and training loss is similar, it means that we are not
  overfitting on the data so a way to improve is to make the neural net more
  bigger and deeper.
  * But there is not a naive way to make the current NN bigger and deeper in a
    productive way.
    * Since the first layer is present, we squash the input layer in that layer.
      So, no use in increasing the number of neurons in the first hidden layer.
* Hence, to solve the crushing input problem is to divide the first hidden layer and take part of the input
  for each smaller layer and so on. Idea is progressive fusion.
  * This is basically the WaveNet architecture.

## Pytorch multiplication

* `@` operator is pretty powerful. You can change `torch.randn(x, y) @ torch(y, z)` which will produce a `x, z` shape tensor to `torch.randn(a, b, y) @ torch.randn(y, z)` that produces a `a, b, z` shape tensor.
* This will be useful in dividing the input layer and do the multiplications.

## How to find bug in `BatchNorm` layer?
* Hand run the code and print if the dimensions are correct.

## Why CNN?
* The hidden layers are kind of like a `for` loop, hence allows to forward
  linear layers efficiently over space.
