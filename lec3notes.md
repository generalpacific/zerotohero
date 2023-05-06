* Initial loss is very high.
  * Why would the initial loss be high?
    * First think about what loss are we expecting. 1/27
    * The initial loss can be high if the logits in the first pass are very
      random. For example, if weight of one the outputs is predicted very high
      the loss will be high.
  * How to fix it?
    * Look at the neural net and last pass if adding a very random bias.
    * Try making bias to 0.
    * Also making the initial `W2`s smaller helps.

* What is the issue with `tanh`/`h`?
  * `h` is the activation at the first layer.
  * Plotting `h` can give an idea what might be wrong.
  * If there a lot more 1s and -1s in the activations this is problem:
    * because we will stop the backpropagation at that point as end up
      multiplying by 0.
  * Same issue will be true for other activation functions like `sigmoid`, `ReLU`.
    * Because these are squashing functions e.g. tanh they squash values between 1,
      -1.
  * How to fix it?
    * We want to make sure the inputs to the activation functions are as close
      to 0.
    * i.e. same as above set the initial weights and biases very small. (`b1`
      and `w1` in case of the current neural net.)

* `Kaiming_normal` 
  * a way to initialize the magic numbers for weights and biases in the neural
    net.

* `BatchNorm`
  * Standardize the hidden activations so that they are roughly Gaussian.

* Recall: why the bias adding is removed after Batchnorm in the code?

* Summary
  * Covered importance of activations, gradients and their statistics.
  * Fixed the initial weights and biases to fix the hockey stick like loss
    reduction and hence achieved better accuracy by reducing the wasteful
    training work.
  * You want roughly guassian activations through out the neural net.
  * Normalization layer to deal with the above the issues.
  * 
