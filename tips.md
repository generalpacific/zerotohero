* Always check the size ond types of your arrays and tensors.
  ```
    tensor.shape and tensor.dtype
  ```
* For tensors you can also index with multiple indices. Eg.
  ```
    C[[1, 5, 8]]
  ```
  * The list of indices can also be a tensor
  ```
    C[torch.tensor([1, 5, 8])]
  ```
    * Alternantively, this tensor for indexing can be an multidimensional
      tensor.
* Pytorch internals: http://blog.ezyang.com/2019/05/pytorch-internals/
* Make sure broadcasting works when adding bias.
* When starting a new layer think about the size of layer hence, figure out the
  size of of your weight and bias vector.
* Use `generator` with a seed to make results reproducible
* Revisit why `cross_entropy` is better than implementing negative log
  likelhood.
* Make sure `requires_grad` is set for the tensors you are using.
* When updating gradients you are updating the data in the parameters.
* `torch.nograd` decorator disables tracking the gradient.
