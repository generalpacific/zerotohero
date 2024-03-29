
* A convolution extracts features from an input image by taking the dot product between the input data and a 3D array of weights (the filter).
* The 2D output of the convolution is called the feature map
* A convolution layer is where the filter slides over the image and computes the dot product
  * This transforms the input volume into an output volume of different size
* Zero padding helps keep more information at the image borders, and is helpful for building deeper networks, because you can build a CONV layer without shrinking the height and width of the volumes
* Pooling layers gradually reduce the height and width of the input by sliding a 2D window over each specified region, then summarizing the features in that region



* Very deep "plain" networks don't work in practice because vanishing gradients make them hard to train.
* Skip connections help address the Vanishing Gradient problem. They also make it easy for a ResNet block to learn an identity function.
* There are two main types of blocks: The identity block and the convolutional block.
* Very deep Residual Networks are built by stacking these blocks together.

* When calling image\_data\_set\_from\_directory(), specify the train/val subsets and match the seeds to prevent overlap
* Use prefetch() to prevent memory bottlenecks when reading from disk
* Give your model more to learn from with simple data augmentations like rotation and flipping.
* When using a pretrained model, it's best to reuse the weights it was trained on.

* MobileNetV2's unique features are:
  * Depthwise separable convolutions that provide lightweight feature filtering and creation
  * Input and output bottlenecks that preserve important information on either end of the block
* Depthwise separable convolutions deal with both spatial and depth (number of channels) dimensions


* To adapt the classifier to new data: Delete the top layer, add a new classification layer, and train only on that layer
* When freezing layers, avoid keeping track of statistics (like in the batch normalization layer)
* Fine-tune the final layers of your model to capture high-level details near the end of the network and potentially improve accuracy

* YOLO is a state-of-the-art object detection model that is fast and accurate
* It runs an input image through a CNN, which outputs a 19x19x5x85 dimensional volume.
* The encoding can be seen as a grid where each of the 19x19 cells contains information about 5 boxes.
* You filter through all the boxes using non-max suppression. Specifically:
  * Score thresholding on the probability of detecting a class to keep only accurate (high probability) boxes
  * Intersection over Union (IoU) thresholding to eliminate overlapping boxes
* Because training a YOLO model from randomly initialized weights is non-trivial and requires a large dataset as well as lot of computation, previously trained model parameters were used in this exercise. If you wish, you can also try fine-tuning the YOLO model with your own dataset, though this would be a fairly non-trivial exercise.


* Semantic image segmentation predicts a label for every single pixel in an image
* U-Net uses an equal number of convolutional blocks and transposed convolutions for downsampling and upsampling
* Skip connections are used to prevent border pixel information loss and overfitting in U-Net

* Face verification solves an easier 1:1 matching problem; face recognition addresses a harder 1:K matching problem.
* Triplet loss is an effective loss function for training a neural network to learn an encoding of a face image.
* The same encoding can be used for verification and recognition. Measuring distances between two images' encodings allows you to determine whether they are pictures of the same person.


* The content cost takes a hidden layer activation of the neural network, and measures how different  𝑎(𝐶) and  𝑎(𝐺) are.
* When you minimize the content cost later, this will help make sure  𝐺 has similar content as  C.

* The style of an image can be represented using the Gram matrix of a hidden layer's activations.
* You get even better results by combining this representation from multiple different layers.
* This is in contrast to the content representation, where usually using just a single hidden layer is sufficient.
* Minimizing the style cost will cause the image  𝐺 to follow the style of the image  𝑆.


* Neural Style Transfer is an algorithm that given a content image C and a style image S can generate an artistic image
* It uses representations (hidden layer activations) based on a pretrained ConvNet.
* The content cost function is computed using one hidden layer's activations.
* The style cost function for one layer is computed using the Gram matrix of that layer's activations. The overall style cost function is obtained using several hidden layers.
* Optimizing the total cost function results in synthesizing new images.
