# Robust-Hand-Gesture-Recognition
Repo for the Hand Gesture Recognition assignment done in COL780: Computer Vision @ IIT Delhi

## Introduction
The purpose of this assignment is to train a Convolutional Neural Network to recognise the hand gestures. The hand gestures could be termed as ​ Previous, Next
and Stop ​ signifying the sign used to control a Music Player.

## Model
We chose to use Keras due to our familiarity with it and also because there were few things which were beneficial such as callbacks. We decided to use 3 Conv Layer with Channel Size of (16, 32, 64) and one dense layer with size of 400 which was chosen after tuning the hyperparameter. Also we chose the optimiser over ADAM over RMSPROP as shown in the model below.

## Preprocessing Steps
### Without PreProcessing
In the first iteration, we were not doing any pre-processing. We thought that the model should be able to predict as we had a lot of data. Then as we were testing it, we realised that it was not general enough and it was giving biased output based on the background with which it was trained on. For eg it was giving result also based on the colour of the t-shirt or the face of the version.

### Pre-processing Step
So, we thought to remove this. There were many things that we tried. First was using dilation and erosion, but it didn’t work out. Then we tried to just run on the model on the hand. We then extracted only those colours which were representative of the skin. So during training we applied this function to each training images and wefound that the model was working better than before and on the validation set we found the accuracy to be 93%.

### Data Augmentation
The next thing that we tried was data augmentation. In this we added zoom factor, vertical flip and rotation of images by certain degree. But then we noticed that it was getting relatively poor accuracy, and our model was able to generalise over various transformations very well without this itself. So, we decided to remove this.

## Hyperparameters
We optimised our model to get the best parameters. We realised that ADAM had the best accuracy with dense connected layer value to be 400. This was surprising as we thought that as we will increase the number of layers the accuracy should increase but this was not the case. We also varied learning rate(0.01 to 0.0001) and dropout values and it turned out that the hyperparameter that were best are reported below.

