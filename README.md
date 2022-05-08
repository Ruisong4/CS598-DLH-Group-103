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

## Citation to the original paper
Liu, X., Chen, Y., Bae, J., Li, H., Johnston, J., & Sanger, T. (2019, November). Predicting heart failure readmission from clinical notes using deep learning. In 2019 IEEE International Conference on Bioinformatics and Biomedicine (BIBM) (pp. 2642-2648). IEEE.

## Data download instruction
First, you should go to [MIMIC-III Clinical Database](https://physionet.org/content/mimiciii/1.4/), and then scroll down to the bottom of the page and download three compressed CSV files: ADMISSIONS.csv.gz, DIAGNOSES_ICD.csv.gz, NOTEEVENTS.csv.gz. After that, you should create a new folder called ‘mimic-iii-clinical-database-1.4’ under current directory and uncompress these CSV files into this folder. 


## File Structure

`pre_preprocess.ipynb`: Preprocess admission data, digonsis data and clinical notes from MIMIC-iii dataset.

`random_forest.ipynb`: Implement baseline model Random Forest classifier using sikit-learn.

`CNN.ipynb`: Implement CNN model with Word2Vec word embedding using Pytorch.

## Running the code

1. pre-processing code: Data preprocessing is implemented in the Jupyter Notebook data_preprocess.ipynb. Once you download and uncompress the data following the instruction above, you can open that Jupyter Notebook and run all cells to preprocess the data. We have added comments for each cell, and finally, the preprocessing code will save the training data and its corresponding label for general heart failure readmission and 30 days heart failure readmission prediction as .txt files in the new created directory called 'CS598_DATA'.

2. Baseline model: Open `random_forest.ipynb` in Google Colab or Jupyter Notebook, execute all cells from top to bottom, it will load the dataset and build baseline model and finally evaluate and print the model performance. We have added the comment for each cell.

3. CNN model: If using google colab, place the output files from the pre-processing step and the pre-trained word2vec weights under the root directory of Google Drive, then execute the cells from top to bottom. We have added the comment for each cell.

## Dependencies

`pandas==1.4.0`

`numpy==1.22.1`

`scikit-learn==1.0.2`

`gensim==4.1.2`

`torch==1.11.0`

`nltk==3.7`

## Table of results

### Baseline Model

| Task                         | Accuracy |  F1   | Recall | Prescision |
| :--------------------------- | :------: | :---: | :----: | :--------: |
| Reported General Readmission |  0.694   | 0.674 | 0.633  |   0.720    |
| Reported 30-day Readmission  |  0.672   | 0.656 | 0.625  |   0.690    |
| General Readmission          |  0.703   | 0.718 | 0.746  |   0.693    |
| 30-day Readmission           |  0.710   | 0.706 | 0.727  |   0.686    |

### CNN Model

| Task                         | Accuracy |  F1   | Recall | Prescision |
| :--------------------------- | :------: | :---: | :----: | :--------: |
| Reported General Readmission |  0.757   | 0.756 | 0.754  |   0.759    |
| Reported 30-day Readmission  |  0.693   | 0.674 | 0.633  |   0.698    |
| General Readmission          |  0.701   | 0.712 | 0.720  |   0.704    |
| 30-day Readmission           |  0.652   | 0.666 | 0.716  |   0.623    |

## Dataset downloading Link

[MIMIC-III Clinical Database](https://physionet.org/content/mimiciii/1.4/) Approval from Physionet Required </br>
[Pre-trained Word2Vec Weights](https://bio.nlplab.org/) publicly available
