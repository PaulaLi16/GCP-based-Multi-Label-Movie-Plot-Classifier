# GCP-based-Multi-Label-Movie-Plot-Classifier

## Overview
This GitHub repository contains the code and data for a Big Data Machine Learning project aimed at solving the multi-label movie plot classification problem. The project leverages PySpark to build a robust NLP pipeline and classification models for predicting multiple movie tags. It is executed on Google Cloud Platform (GCP) DataProc, utilizing a big data cluster.

The repository is organized as follows:

data: This directory contains the dataset file mpst_full_data.csv, which can be downloaded from Kaggle (https://www.kaggle.com/datasets/cryptexcode/mpst-movie-plot-synopses-with-tags) and placed here.

notebooks: The Jupyter Notebook movie_plot_multi_label_classifier.ipynb in this directory serves as the primary code file for the project. 

README.md: The project's README file provides an overview of the project and its structured layout.

## Project Structure
### 1) Data Exploration
This part involved importing movie synopsis data into Spark, generating basic summary statistics using SparkSQL, and creating charts to visualize the distribution of popular movie tags, with a focus on identifying the top 10 tags. 

### 2) Machine Learning Models
First, Natural Language Processing (NLP) pipelines were established to handle text preprocessing for the movie synopsis data. This included tasks such as removing stopwords and conducting tokenization on the movie synopses. To ensure flexibility and facilitate comparisons, various vectorization methods, including Count Vectorization, Word2Vec, and HashingTF, were implemented.

To enable customized tag classification, the data was restructured through pivoting, facilitating the training of individual models for each genre tag. These models were specifically crafted to utilize movie synopsis text as input features and individual tags as labels.

Addressing the challenge of multi-label classification, ten models were created using each NLP pipeline. These models employed the Logistic Regression algorithm to classify movies into the top 10 most popular tags. Subsequently, validation scores were computed for each of these ten models. Below, you can find an example of the final output, presenting the results of these ten ML models that utilized the NLP pipeline with Word2Vec:

|      model_name|accuracy|    F1|
|----------------|--------|------|
|          murder|  0.7012|0.7075|
|        violence|  0.7437|  0.76|
|       flashback|  0.7102|0.7916|
|        romantic|  0.7637| 0.806|
|            cult|  0.7388|0.8088|
|         revenge|  0.7697|0.8208|
|     psychedelic|  0.8336| 0.873|
|          comedy|  0.8204|0.8747|
|     suspenseful|  0.8911|0.9224|
|good versus evil|  0.9188|0.9334|


### 3) Inference
Synopsis data for a minimum of 10 recent movies (from 2020 to the present) was gathered from sources including IMDb and Wikipedia. Utilizing the ML models developed earlier, an analysis was conducted to determine which of the 10 popular tags were applicable to these movies. Based on the results, the hashingTF approach employed in Model yielded the most accurate and multifaceted tag predictions for inference data.






