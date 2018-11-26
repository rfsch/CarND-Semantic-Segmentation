# Semantic Segmentation

### Introduction

In this project I have developed a Fully Convolutional Network (FCN) which semantically segmented images from [the Kitti Road dataset](
http://www.cvlibs.net/download.php?file=data_road.zip) into street and non-street segments.

## Project Info
To see the FCN implementation you can have a look at `main.py` in my CarND-Semantic-Segmentation repository.

## Overview
The goal of the project was to implement a Fully Convolutional Network (FCN) using the VGG-16 image classifier architecture to semantically segment(street vs. non-street in images).

## Architecture
I used the pre-trained VGG-16 network provided by Udacity and converted it to a Fully Convolutional Network. I replaced the last fully connected layer with a one-by-one convolution and set the depth to the number of classes required.

I have used two skip connections, one-by-one convolutions on layers before and upsampled as a last step. 

### Optimization Paramters

Loss function: Cross-entropy
Optimizer:     Adam optimizer

### Training

These are the hyperparameters I used:

|  Input          |    MSE   |
|  -----          |  ------- |
|  keep_prob:     |  0.5     |  
|  learning_rate  |  1e-4    |
|  epochs         |  30      |
|  batch_size     |  8       |

### Results
Loss consistently dropped over the course of the 30 epochs, going from an average of 0.30 in epoch 1 to an average of 0.01 in epoch 30. You can see some of the pictures that have been semantically segmented below:

![Sample 1](https://github.com/rfsch/CarND-Semantic-Segmentation/edit/master/output/um_000015.png?raw=true "Sample 1")
### Conclusion

The FCN was able to achieve consistently good results and most of the time correctly segmented streets against non-streets. 

### Setup
##### Frameworks and Packages
Make sure you have the following is installed:
 - [Python 3](https://www.python.org/)
 - [TensorFlow](https://www.tensorflow.org/)
 - [NumPy](http://www.numpy.org/)
 - [SciPy](https://www.scipy.org/)
##### Dataset
Download the [Kitti Road dataset](http://www.cvlibs.net/datasets/kitti/eval_road.php) from [here](http://www.cvlibs.net/download.php?file=data_road.zip).  Extract the dataset in the `data` folder.  This will create the folder `data_road` with all the training a test images.

### Start
##### Implement
Implement the code in the `main.py` module indicated by the "TODO" comments.
The comments indicated with "OPTIONAL" tag are not required to complete.
##### Run
Run the following command to run the project:
```
python main.py
```
**Note** If running this in Jupyter Notebook system messages, such as those regarding test status, may appear in the terminal rather than the notebook.

### Submission
1. Ensure you've passed all the unit tests.
2. Ensure you pass all points on [the rubric](https://review.udacity.com/#!/rubrics/989/view).
3. Submit the following in a zip file.
 - `helper.py`
 - `main.py`
 - `project_tests.py`
 - Newest inference images from `runs` folder
