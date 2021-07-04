<h1>American Sign Language Recognition</h1>

The purpose of this project is to predict letters of the American Sign Language through images.
In order to achieve our goal, we had to build a Convolutional Neural Network which was trained on the ASL Alphabet dataset (https://www.kaggle.com/grassknoted/asl-alphabet/code).

At the beginning of this project and after importing the necessary libraries, we loaded the dataset and specified the class names, as well as the desired dimensions for each image. Afterwards, we defined X_train set which is consisted of the set of images on which our model will be trained and y_train set which is consisted of all the labels corresponding to the said images. Then, we split the dataset in training and test sets. Training set contains 80% of the initial dataset, while test set contains the remaining 20%. Finally, we one-hot-encoded y_train and y_test in order to have categorical values for our labels/classes.

The model which is built in this project is a Sequential CNN with three 2D layers. The architecture of the model and the model summary can be seen in the following images:

![cnn_model](https://user-images.githubusercontent.com/75978785/124388632-6502b180-dcec-11eb-85b1-681f5840c569.png)

![modelsummary](https://user-images.githubusercontent.com/75978785/124388664-84014380-dcec-11eb-94a6-09b42820df29.PNG)



We will also use early stopping on our model, which will monitor the validation loss of and will stop the model's operation after observing that its performance has stopped improving. This is done in order to make sure that the model fitting stops at the most optimized accuracy point and it does not overfit. 
After having built our model, we proceeded with compiling and fitting the CNN model. Concerning the compiling hyperparameters, the optimizer we used is Adam and the loss is "categorical_crossentropy" which is ideal for multiclass problems. Finally the fitting of our model is done for 20 epochs and with a batch size of 64. For the evaluation of our model, we loaded random images found online and ran the model prediction function.

To conlude, we present the metrics graphs that were recorded from TensorBoard while the whole project was running.
Accuracy is not a very reliable metric for measuring the performance of our model, so we also observe the evolution of F1 score per epoch. Also, we observe the loss' behavior during all epochs in order to better understand how good our model is.

In the following graphs, validation is depicted in blue color, while train is in orange.

<h3> Accuracy </h3>

![acc](https://user-images.githubusercontent.com/75978785/124388837-49e47180-dced-11eb-8705-ec54229dc2fe.PNG)

<h3> F1 Score </h3>

![f1](https://user-images.githubusercontent.com/75978785/124389136-819fe900-dcee-11eb-9522-517e995ba57e.PNG)

<h3> Loss </h3>

![loss](https://user-images.githubusercontent.com/75978785/124389137-85cc0680-dcee-11eb-90dd-24f7da8dce8c.PNG)


The fact that we achieved scores of 99.8% on accuracy, 99.8% on f1 score and less than 0.01 on loss, shows that our model is almost accurate in recognizing the American Sign Alphabet via images. 
