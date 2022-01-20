# Generating Bach-like music

## Intro
A small project done in the course ID2223 at KTH where we tried to generate Bach-like music using RNNs and CNNs.  

Similar exercise can be found in chapter 15 in *Hands-On Machine Learning with Scikit-Learn, Keras, & TensorFlow* by Aurélien Géron.

## Data
We used the Bach Chorales Dataset *(available [here](https://github.com/ageron/handson-ml2/blob/master/datasets/jsb_chorales/README.md))*. It contains 382 chorales (songs) composed by Bach, each one of these chorales consists of 100 to 640 chords where each chord is composed of four notes. 
Each note is an integer *(36-81 and 0)* that represents a MIDI note number. These numbers correspond to the piano notes C2 (36) to A5 (81) plus 0 for silence.

## Method
We pre-processed the data by first scaling the data so the integers ranged from 0 to 47. We also chose to represent the chords as arpeggios (broken chords) which means that instead of predicting a chord (4 notes) we predict a single note at a time.

We then trained some different neural network models, a basic RNN model, an LSTM model, a GRU model and a diluted CNN model with an LSTM layer. 

In order to evaluate the models we listen to the generated songs. 

## Results
We believe that the diluted CNN model produces the most authentic music.


This is how one of the original chorales (first chorale in the training data) sound:
https://user-images.githubusercontent.com/85300362/150366627-fc9a7f49-b09d-4d08-b66c-e926ece48ea9.mp4

We used the beginning of this chorale to generate new songs with our different models. The following are the generated songs:

Diluted CNN with LSTM (best result in our opinion):
https://user-images.githubusercontent.com/85300362/150367193-89be67d1-5f2f-4db7-af87-0c7a27b98997.mp4


Simple RNN:
https://user-images.githubusercontent.com/85300362/150367294-6fc37460-49fe-4947-8f85-0c2877310417.mp4

GRU:
https://user-images.githubusercontent.com/85300362/150367376-3b901ef2-0c9f-431d-a6f2-832f9e01c25c.mp4

LSTM:
https://user-images.githubusercontent.com/85300362/150367403-310b7a52-8a53-4440-adeb-adbe7d47c613.mp4





More comments and the code is found in the notebook.






