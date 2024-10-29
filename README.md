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
- Step 3: Data Preparation Steps - Train-Validation Split and Test Set
- Step 4: Building the Initial Model (Model 1)
- Step 5: Data Augmentation - Build Model after Applying Augmentation
- Step 6: Fix Class Imbalance and Build the Model
- Step 7: Fine-tune and Optimize the Model
- Step 8: Making Predictions Using the Models
- Step 9: Conclusion
  
## Technologies/Libraries Used
- numpy : 1.26.4
- pandas : 2.2.2
- matplotlib : 3.7.1
- tensorflow : 2.17.0
- keras : 3.4.1
- augmentor : 0.2.12

## Conclusions
**Based on the model comparison and evaluation, the following insights can be drawn: -**
- Model 8 (Base Model + Augmented Layers + Balanced Class + Controlled LR + More Layers + Less Dropouts) achieved the best overall performance with the highest validation accuracy (0.68) and test accuracy (0.47). This suggests that optimizing dropout rates and balancing the class distribution improves model generalization.
- Model 4 (Base Model + Augmented Layers + Balanced Class + Controlled LR) and Model 5 (Base Model + Augmented Layers + Balanced Class + Increased / Controlled LR) both show competitive results, with test accuracies of 0.43. These models effectively address class imbalance and fine-tune the learning rate.
- Model 6 (Base Model + Augmented Layers + Balanced Class + Controlled LR + More Epochs) achieved better training accuracy (0.65) but slightly lower test accuracy (0.42), indicating potential overfitting as the model learned too well on the training data.
- Base Models (1, 2, 3) show lower test accuracies, especially Model 1 which had high training accuracy (0.84) but low generalization on the test set (0.31), demonstrating severe overfitting without any regularization techniques.
- Overall, applying data augmentation, class balancing, learning rate control, dropout optimization, and deeper architectures significantly enhanced the performance of the CNN models for melanoma detection, with Model 8 emerging as the most balanced in terms of validation and test performance. Further optimization could continue to improve this performance.

**Q :- Which class has the least number of samples?
Answer - seborrheic keratosis has the least number of samples - 77
**Q :- Which classes dominate the data in terms proportionate number of samples?
Answer - pigmented benign keratosis dominates the data in terms proportionate number of samples - 462



## Acknowledgements

- The project reference course materieals from upGrads curriculm .
- The project references from presentation in upgrad live class given by [Snehansu Sekhar Sahu]( https://www.linkedin.com/in/snehansu-sekhar-sahu-iisc/ )
- The project references insights and inferences from presentation in upgrad live class given by [Tanisha Medewala](https://www.linkedin.com/in/tanishamedewala/)

## Glossary

- Data Augmentation
- Class Imbalance
- Train-Validation Split
- Test Set
- Convolutional Neural Network (CNN)
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
