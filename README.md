# Udacity Data Science Nanodegree

## Project 3 - Data Science Pipeline

### Read Me

### Table of Contents

<ul>
<li><a href="#Installation">Installation</a></li>
<li><a href="#Project-Motivation">Project Motivation</a></li>
<li><a href="#File-Descriptions">File Descriptions</a></li>
<li><a href="#Results">Results</a></li>
<li><a href="#Licensing,-Authors,-Acknowledgements">Licensing</a></li>
</ul>

### Installation

This code was written by using Python, version 3.12.3 and the following libraries:

- scikit-learn
- pandas
- notebook
- seaborn
- spacy

A requirements.txt file supports the installation of these packages:

```
python -m pip install -r requirements.txt
```

For SpaCy NLP you have to download the following - which is also an optional part of the notebook:

```
python -m spacy download en_core_web_sm
```

It seems, that there are difficulties installing SpaCy on Python, version 3.13. I really recommend you to work on a version lower than 3.13. You can find the more information for installing SpaCy <a href="https://spacy.io/usage">here</a>.

### Project Motivation

The third project of Udacity's Data Scientist Nanodegree deals with a machine learning pipeline.

The project followes the following process:

- **Load and Preparing Data**
- **Data Exploration**
- **Building Pipeline**
- **Training Pipeline**
- **Fine-Tuning Pipeline**

The data is originally from a fashion store and is used to make predictions. The features can be summarized as the following:

- **Clothing ID**: Integer Categorical variable that refers to the specific piece being reviewed.
- **Age**: Positive Integer variable of the reviewers age.
- **Title**: String variable for the title of the review.
- **Review Text**: String variable for the review body.
- **Positive Feedback Count**: Positive Integer documenting the number of other customers who found this review positive.
- **Division Name**: Categorical name of the product high level division.
- **Department Name**: Categorical name of the product department name.
- **Class Name**: Categorical name of the product class name.

The target:
- **Recommended IND**: Binary variable stating where the customer recommends the product where 1 is recommended, 0 is not recommended.

### File Descriptions

There are three relevant files in this repository:

- `requirements.txt`: Relevant Python packages and libraries.
- `starter/starter.ipynb`: Jupyter Notebook including the machine learning pipeline process.
- `starter/data/reviews.csv`: Database includes product reviews and is the base for the pipeline process in `starter.ipynb´ .

### Results

After **loading**, **preparing** and **exploring** the data, it was splittet into three main features numerical, categorical and text.

Every feature was preprocessed seperately and finally combined into a single **pipeline**.

The pipeline was extended by two machine learning models, which were Random Forest Classifier and Support Vector Machines (SVM). After **training** and **evaluation** there is a resulting accuracy of both models by

- Random Forest Classifier: 84,1% and
- Support Vector Machines: 82,3%.

In a **fine-tuning** step using RandomizedSearchCV both models were tuned by specific parameters. This step increased the accuracy of at least the SVM model

- Random Forest Classifier: 84,1% -> 83,5% and
- Support Vector Machines: 82,3% -> 88,3%.

Other metrics of the fine tuned Support Vector Machines model like

- Accuracy: 0.8829268292682927
- Precision: 0.9104665825977302
- Recall: 0.9512516469038208
- F1-Score: 0.9304123711340206

indicate a good performance. All parameters of the fine-tuned SVM model are shown in the Jupyter Notebook.

This machine learning pipeline is a good basis for further steps. Other models like Gradient Boost or choosing other parameters using GridSearchCV could improve the performance.

### Licensing, Authors, Acknowledgements

The project is originally forked on Udacity's GitHub page <a href="https://github.com/udacity/dsnd-pipelines-project">here</a>.

The pipeline process and code is inspired and orientated on Udacity's Data Scientist Nanodegree, Course 4 *Data Science Pipelines* and on Exercices 4.2.19 *Classify Fashion Items with Support Vector Machines* and 4.3.18 *NLP Pipelines*. Other sources and quotes in the Jupyter Notebook are mentioned on the relevant position.

Udacity's licence declaration you can find <a href="https://github.com/stefanschonauer/Udacity_DSND_Project_03/blob/main/LICENSE.txt">here</a>.
