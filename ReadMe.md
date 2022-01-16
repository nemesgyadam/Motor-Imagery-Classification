# Task

In this project we classified different imagined movements with machine learning tools.
The subjects EEG signals has been recorded during the experiment and this signals was processed with  Deep Learning (convolutional neural network)

&nbsp;
# Paradigm
The object of the project was to classify the following 3 different tasks:

    * Rest    (reference state)
    * Left    (Thinking about moving the left hand)
    * Right   (Thinking about moving the right hand)

&nbsp;
### Device:

The EEG signals was recorded with the Mindrove device:

[Official Site](https://mindrove.com/)

[Github Repo](https://github.com/MindRove/SDK_Public)

&nbsp;
### Details of recording:


We recorded 6 channels with 500hz sampling rate.
The electrodes were placed over the Motor Cortex.

The expriment contained separated sessions from the same subject, recorded in different times.

During one session the subject executed 30 of each class (90 total) in random order. 

(In this particular case, the subject imagined to raise the given hand, and write a letter in the air with it.)


Each task was recorded with the following timeline:

    - 1 second stand by time 
    - The instructions appeared
    - 2 second of recording period(additional 200 ms added to this part to make sure enough signal is recorded)

&nbsp;
# Dataset
The recorded sessions are available in the resource folder in numpy format. The raw EEG signals has been stored, all filtering and preprocessing applied before the train. Each session stored in separated folder.
The 3 class has been stored in separated npy files. Each file contains 20 samples. So the files has the following dimension:

(30,6,1000) --> N_sample, N_channel, Time_points(2sec*500hz)

&nbsp;
# Training
The Train.ipynb contains an implementaion of a  "traditional" feed forward training method, with a custom CNN specified for EEG classification.