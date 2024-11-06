# Gesture Recognition Project
> Develop a gesture recognition system for a smart TV that identifies five distinct user gestures to enable remote-free control.


## Table of Contents :
* [Problem Statement](#problem-statement)
* [Objectives](#objectives)
* [Approach](#approach)
* [Technologies/Libraries Used](#technologies/libraries-used)
* [Conclusions](#conclusions)
* [Acknowledgements](#acknowledgements)
* [Glossary](#glossary)
* [Author](#author)


## Problem Statement
Imagine you are working as a data scientist at a home electronics company which manufactures state of the art smart televisions. You want to develop a cool feature in the smart-TV that can recognise five different gestures performed by the user which will help users control the TV without using a remote.

The gestures are continuously monitored by the webcam mounted on the TV. Each gesture corresponds to a specific command:

- Thumbs up:  Increase the volume
- Thumbs down: Decrease the volume
- Left swipe: 'Jump' backwards 10 seconds
- Right swipe: 'Jump' forward 10 seconds  
- Stop: Pause the movie
 

Each video is a sequence of 30 frames (or images). In the next couple of lectures, our subject matter expert Snehansu will walk you through the structure of the dataset.

The training data consists of a few hundred videos categorised into one of the five classes. Each video (typically 2-3 seconds long) is divided into a sequence of 30 frames(images). These videos have been recorded by various people performing one of the five gestures in front of a webcam - similar to what the smart TV will use.  

The data is in a zip file. The zip file contains a 'train' and a 'val' folder with two CSV files for the two folders. These folders are in turn divided into subfolders where each subfolder represents a video of a particular gesture. Each subfolder, i.e. a video, contains 30 frames (or images). Note that all images in a particular video subfolder have the same dimensions but different videos may have different dimensions. Specifically, videos have two types of dimensions - either 360x360 or 120x160 (depending on the webcam used to record the videos).

Each row of the CSV file represents one video and contains three main pieces of information - the name of the subfolder containing the 30 images of the video, the name of the gesture and the numeric label (between 0-4) of the video.

In order to get the data on the storage, perform the following steps in order
1. Open the terminal
2. go down [dataset]( https://drive.google.com/uc?id=1ehyrYBQ5rbQQe6yL4XbLWe3FMvuVUGiL )
3. unzip Project_data.zip

## Approach

- Step 1: Import Necessary Libraries
- Step 2: Load the Data and Understanding the Data
- Step 3: Data Preparation Steps - Train-Validation Split and Test Set - Geneartor 
- Step 4: Identify parameters and hyperparameters
- Step 5: Conv3D model
- Step 6: CNN and RNN model
- Step 7: Transfer Learning imagenet and RNN model
- Step 8: Making Predictions Using the Models
- Step 9: Conclusion
  
## Technologies/Libraries Used
- Python: 3.10.12 (main, Sep 11 2024, 15:47:36) [GCC 11.4.0]
- NumPy: 1.26.4
- TensorFlow: 2.17.0
- Keras: 3.4.1

## Conclusions
Based on the experiments, Approach 3 - Experiment 6 (MobileNetV2 with transfer learning) appears to be the optimal choice for the final model. It offers a well-balanced trade-off between accuracy, loss, and computational efficiency:

  - High Accuracy and Low Loss: This approach achieved the best results, with a maximum training accuracy of 0.96, maximum validation accuracy of 0.88, minimum training loss of 0.12, and minimum validation loss of 0.21 .
  - Moderate Parameters: By freezing the initial 100 layers of MobileNetV2, the model maintains a manageable parameter count while effectively leveraging transfer learning.
  - Efficient Training Time: Global Average Pooling reduces the feature size, resulting in faster training without sacrificing performance.
Future Work and Improvements: Further experimentation could involve adjusting frame dimensions or exploring more efficient CNN backbones. Testing the model on larger datasets or in real-time scenarios could also enhance robustness and practical applicability.



## Acknowledgements

- The project reference course materieals from upGrads curriculm .
- The project references from presentation in upgrad live class given by [Snehansu Sekhar Sahu]( https://www.linkedin.com/in/snehansu-sekhar-sahu-iisc/ )
- The project references insights and inferences from presentation in upgrad live class given by [Tanisha Medewala](https://www.linkedin.com/in/tanishamedewala/)

## Glossary

- Data Augmentation
- Convolutional Neural Network (CNN)
- RNN
- Transfer Learning using Imagenet
- Dropout
- Learning Rate (LR)
- Overfitting
- Early Stopping
- Cross-Entropy Loss
- Accuracy
- Batch Normalization
- Max Pooling
- Softmax
- Learning Rate Scheduler (ReduceLROnPlateau)

## Author
* [Arnab Bera]( https://www.linkedin.com/in/arnabbera-tech/ )
* [Arpit Nigam]( https://www.linkedin.com/in/arpit-nigam0401/ )
