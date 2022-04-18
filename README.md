# CS598 DLH Final Project Group 103

## Overview

In this project, we are going to reproduce the paper
”Predicting Heart Failure Readmission from Clinical Notes Using Deep Learning”. Predicting heart
failure readmission accurately can help patients get
treatment in time and reduce the burden on hospital
resources. Previous literature on this topic usually
use structured healthcare data like procedure code
and diagnosis code as the input to the neural network, and those clinical variables often require a
lot of feature engineering from experts. This paper
combines the NLP approach with the Convolution
Neural Network to achieve this goal. The patients’
discharge summary notes of their most recent heart
failure hospital admission are converted into vector
representation using word embedding, and then a
CNN model is used to extract features and learn
useful information from the document vectors. In
this project, we will reproduce the model demonstrated in the paper to predict heart failure readmission and its corresponding baseline models.

## File Structure

`pre_preprocess.ipynb`: Preprocess admission data, digonsis data and clinical notes from MIMIC-iii dataset.

`random_forest.ipynb`: Implement baseline model Random Forest classifier using sikit-learn.

`CNN.ipynb`: Implement CNN model with Word2Vec word embedding using Pytorch.

## Requirments

`pandas==1.4.0`

`numpy==1.22.1`

`scikit-learn==1.0.2`

`gensim==4.1.2`

`torch==1.11.0`

`nltk==3.7`

## Dataset

[MIMIC-III Clinical Database](https://physionet.org/content/mimiciii/1.4/)
