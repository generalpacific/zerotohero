# Notes

* What you should remember:
  * The weights  𝑊[𝑙] should be initialized randomly to break symmetry.
  * However, it's okay to initialize the biases  𝑏[𝑙] to zeros. Symmetry is still broken so long as  𝑊[𝑙] is initialized randomly.
  * Although initializing weights to very large random values doesn't work well. Initializing with small random values should do better. 
  * The implications of L2-regularization on:
    * The cost computation:
      * A regularization term is added to the cost.
    * The backpropagation function:
      * There are extra terms in the gradients with respect to weight matrices.
      * Weights end up smaller ("weight decay"):
      * Weights are pushed to smaller values.

  * Dropout is a regularization technique.
    * You only use dropout during training. Don't use dropout (randomly eliminate nodes) during test time.
    * Apply dropout both during forward and backward propagation.
    * During training time, divide each dropout layer by keep_prob to keep the same expected value for the activations. For example, if keep_prob is 0.5, then we will on average shut down half the nodes, so the output will be scaled by 0.5 since only the remaining half are contributing to the solution. Dividing by 0.5 is equivalent to multiplying by 2. Hence, the output now has the same expected value. You can check that this works even when keep_prob is other values than 0.5.


  * Gradient checking verifies closeness between the gradients from backpropagation and the numerical approximation of the gradient (computed using forward propagation).
  * Gradient checking is slow, so you don't want to run it in every iteration of training. You would usually run it only to make sure your code is correct, then turn it off and use backprop for the actual learning process.
