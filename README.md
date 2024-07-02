# Gesture Recognition
# Problem statement
> You are a data scientist at a home electronics company developing a smart TV feature to recognize five user gestures, allowing remote-free control:
•	Thumbs up: Increase volume
•	Thumbs down: Decrease volume
•	Left swipe: Rewind 10 seconds
•	Right swipe: Fast forward 10 seconds
•	Stop: Pause the movie
	

## Table of Contents
* [General Info](#general-information)
* [Steps Followed in the Projects](#Steps Followed in the Projects)
* [Technologies Used](#technologies-used)
* [Conclusions](#conclusions)
* [Acknowledgements](#acknowledgements)


## Understanding the Dataset
- The dataset includes hundreds of short videos (2-3 seconds, 30 frames each) of people performing the gestures. The data is divided into 'train' and 'val' folders, each with corresponding CSV files.

## Objective
- Train models on the 'train' dataset to accurately predict gestures and evaluate performance on the 'val' dataset. The final model will be tested on a withheld 'test' set.


## Model Descriptions

1.	CNN + RNN Architecture:
-	CNN: Extracts feature vectors from each frame.
-	RNN: Processes the sequence of feature vectors.
-	Output: Softmax layer for classification.
2.	3D Convolutional Neural Networks (Conv3D):
-	Processes video as a 4D tensor (e.g., 100 x 100 x 30 x 3).
-	Uses 3D filters to convolve across the x, y, and z dimensions.

## Data Pre-processing:
-	Resizing: Standardizes frame dimensions.
-	Normalization: Mitigates lighting and shadow distortions.
## Data Generator:
- 	Pre-processes images to handle different dimensions (70x70, 100x100, 120x120) and creates batches of video frames. Ensures consistent cropping, resizing, and normalization.


## Model Training:
-	Experiments: Tested various model configurations, hyper-parameters, batch sizes, image dimensions, filter sizes, padding, and stride lengths.
-	Optimization: Used SGD optimizer for better accuracy, adjusting parameters like decay rate and learning rate.
-	Regularization: Implemented batch normalization, pooling, and dropout layers to combat overfitting.
-	Early Stopping: Halted training when validation loss plateaued.


## Conclusions
- 	The project involved experimenting with various models and configurations to achieve optimal gesture recognition for smart TV controls. Key observations include:
-	Conv3D Models:
o	Early models (Models 1-5) struggled with low accuracy and signs of overfitting. Increasing epochs and adjusting image size helped, but improvements were limited.
-	CNN + RNN Models:
o	Model 6, using a TimeDistributed CNN2D with GRU, achieved high accuracy (90% training, 75% validation) with no overfitting, indicating strong performance.
o	Model 7 showed some overfitting with slightly lower validation accuracy.
-	Conv2D + Dense Model:
o	Model 8 performed well with 96% training and 71% validation accuracy, showing it to be a robust configuration.
-	Conv2D + LSTM Models:
o	Models 9 and 10 showed poor accuracy, indicating this architecture was not effective for this task.
-	Transfer Learning Models:
o	Model 11 (VGG16) achieved the best results with 99.5% training and 85% validation accuracy, making it the top-performing model.
o	Model 12 (ResNet50) showed high training accuracy but significant overfitting with low validation accuracy.
-	Overall, transfer learning using VGG16 provided the best performance, while CNN + RNN and Conv2D + Dense architectures also showed promising results. Models using Conv2D + LSTM 	were the least effective.

## Technologies Used
- RNN
- CNN
- VGG16
- ResNet50
- keras
- tensorflow
- matplotlib


## Acknowledgements
Give credit here.
- This project was inspired by home electronics company developing a smart TV.
- I would like to thank my upGrad Buddy and tutor for assisting me to complete this assignment
- Reference: Stack Overflow, Wikipedia, Google Collab & GPT 


## Contact
Created by [@subham0206] - feel free to contact me!

