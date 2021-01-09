# M48-FDS20
20HS MINF4566 Foundations of Data Science (L+E)

# Practical 1 Implementation of Linear Regression

To begin with, we split the different task amongst our group, which resulted in the following split:

Kevin: 1, 4, 5, 8, 11
Flavia: 2, 6, 9, 13
Gabriel, 3, 7, 10, 12

When approaching the task we quickly noticed that splitting the task work was possible only to the extent that the different task do not rely on each other. Therefore trying out the code would have to wait until all dependent tasks were completed by the respective team members. 

Task 1 and 2 were relatively straight forward as such no problems encountered there as we the respective functions (plot and calc average). 

With Task 3 we encountered the first challenge by understanding which formula to apply when calculating the MSE given that as per the literature sometimes the total number of data points was sometimes multiplied by two and sometimes not. After doing further research, we understood that multiplying the total by a scalar or not is not so relevant but rather that we have to apply a consistent approach in order to have comparable results. As such we finally decided to pass on the multiplication by 2. 

Task 4 was rather straightforward again, given the vast amount of literature available to answer this question

Instead of using an existing library for calculating the optimal “w” task 6 and 5 was in particular good since here we could see how a library may implement the equation in order to build a closed form solution and also to understand how to implement a function to normalize a data set for linear regression analysis.

Task 7 and 8 was then the result of the things created in the tasks before and it helped us to better understand eventually how to analyse the model which we created and understanding how under and overfitting may occur resp. how to pick an optimal model.

With task 9 to 13  we noticed how to use basis expansion and learned that it may take a lot of time to increase the basis of a model, which is why we could see how kernels might be useful with very large data sets. Further we also saw that the validation data set is important as we have to pick hyper parameters for our model. 
In particular interesting was to see how k-fold validation would take a lot of time to compute so we had to reduce our reproduction random state from over 1000 to 100 in order to have a result in a meaningful timeframe. Eventually what was in particular interesting to observe was that our k-fold cross validation program resulted also in an optimal polynomial expansion of 2 degree like in task 12 yet the MSE’s were larger than in task 12. Even though we would have expected in such case that the MSE’s are the same. We found that the reason for this might be found in the way how the MSE’s are calculated in the different libraries used

# Practical 2 Generative and Discriminative Models


# Practical 3: Artificial Neural Network & Transfer Learning

Since the two tasks could not be well divided, we solved them using the pair programming method. All members participated in solving the tasks.

## Task 1: Artificial Neural Network

The difficulty of the first task was to get familiar with Keras and Tensorflow. We were overwhelmed by the countless possibilities that could be used to train a neural network. It helped that we started with only one fully connected layer and systematically worked our way up to more complex models by adding Batch-Normalization and Dropout-Layer. First we chose RandomCV in order to fine-tune simple model an later decided to dive into the library Hyperas. The difficulty here was that we first had to familiarize ourselves with hyperas. An existing example on its Github page was extremely helpful to understand how the library should be used. With the help of Hyperas we managed to achieve a appropriate result at the end.

## Task 2: Transfer Learning

As already mentioned in the summary the main challenge in this task was to use Transfer learning in order to adapt to the dataset accordingly. As we familiarized ourselves with Keras already, we were able to manipulate ResNet50 as we wanted but we were not sure how it should be done properly to enhance the accuracy. We tried many things such as using only the first part of the model and adding one fully connected layer on top followed by the softmax layer. It turned out that removing layers from the model did not give the desired result. We finally stick with the original size (without the fully connected layers) and decided to only retrain the last part of the model. This resulted already in better accuracy but as we continued digging further we realized that the input size of the images must be at least 200x200 pixels to unravel the full potential of the chosen model. After training the model with an upscaling layer we finally reached an accuracy above 80%.