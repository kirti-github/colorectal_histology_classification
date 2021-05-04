# colorectal_histology_classification

About the dataset
------------------
The dataset used here is the colorectal histology dataset from tensorflow. This dataset consists of 5000 images belonging to 8 different classes. The classes are: Tumor, Stroma, Complex, Mucosa, Lympho, Adipose, Debris, Empty. These are RGB images and have the dimensions 150X150. Each class has 625 number of images 

About the choice of parameters/hyperparameters
-------------------------------------
Number of convolutional layers --> To reduce the computational complexity of the algorithm, the maximum number of convolutional layers chosen here is 2.
Number of kernels/filters in convolutional layer 1  --> In order to get maximum features from the image, the number of filters chosen is 128. This number was obtained through experimentation.
Number of kernels/filters in convolutional layer 2  --> Through experimentation, 64 gave the best result. Values more than 64 took more training time but didn’t contribute much to the accuracy
Kernel size in convolutional layer 1--> A window size of 5X5 was chosen in the first conv layer to get the high level features.
Kernel size in convolutional layer 2 --> Since in this layer, we need to work on images of reduced dimension (output of maxpool layer 1), 3X3 seemed ideal choice.
Stride in convolutional layer 1 and 2 --> 2,2 is the most widely used stride. Worked well even in this case. 1,1 would have resulted in larger feature map which is computationally expensive.
Activation function used in convolutional layer 1 and 2 --> relu for non linearity.
Number of pooling layers --> 2. One after each convolutional layer.
Number of layers in the fully connected/Dense layer (including output layer) --> One hidden layer and one output layer gave best results.
Optimizer function --> adam, which is widely used and computationally efficient
Loss function --> categorical_crossentropy, usually used for multi class classification
batch size --> 200 . Higher batch size would result in faster convergence.
epochs --> Since model checkpoint is used, the algorithm converged at the end of 476 epochs.
The dataset is split as 70% training data, 15% validation and 15% test data.
