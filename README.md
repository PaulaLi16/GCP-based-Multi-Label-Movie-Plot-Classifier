# GCP-based-Multi-Label-Movie-Plot-Classifier

## Overview
This GitHub repository contains the code and data for a Big Data Machine Learning project aimed at solving the multi-label movie plot classification problem. The project leverages PySpark to build a robust NLP pipeline and classification models for predicting multiple movie tags. It is executed using a big data cluster on Google Cloud Platform (GCP) DataProc

The repository is organized as follows:

data: This directory contains the dataset file mpst_full_data.csv, which can be downloaded from Kaggle (https://www.kaggle.com/datasets/cryptexcode/mpst-movie-plot-synopses-with-tags) and placed here.

notebooks: The Jupyter Notebook movie_plot_multi_label_classifier.ipynb in this directory serves as the primary code file for the project. You'll also find the notebook available HTML formats (movie_plot_multi_label_classifier.html).

README.md: The project's README file provides an overview of the project and other relevant information.

## Project Structure
### 1) Data Exploration
This part involved importing movie synopsis data into Spark, generating basic summary statistics using SparkSQL, and creating charts to visualize the distribution of popular movie tags, with a focus on identifying the top 10 tags. 

### 2) Machine Learning Models
I constructed SparkML pipelines to create models for classifying movies into the top 10 most popular tags. The NLP pipeline involved essential preprocessing steps like removing stopwords and tokenizing the synopsis data. I incorporated multiple vectorization methods for the synopsis text, inlcuidng Count Vectorization, Word2Vec and HashingTF, to allow for comparison.

To facilitate individualized tag classification, I pivoted the data, enabling the training of one model for each genre tag. The models were designed to take movie synopsis text as input features and individual tags as labels. 




