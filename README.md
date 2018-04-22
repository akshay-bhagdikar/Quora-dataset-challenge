********************************************************************************************************************************************************************************************************************************************************************************
# Quora-dataset-challenge

********************************************************************************************************************************************************************************************************************************************************************************
## The Dataset 
**Introduction:**
The Quora dataset challenge is about predicting whether two questions have similar meaning or not.It is important for Quora to detect duplicate questions to save space and avoid the hassle of answering the same questions for the users.The goal of this project is to explore natural language processing techniques and integrate them with neural networks.

****************************************************************************************************************************************

**Data Preparation:**

1. The dataset is unbalanced with almost 64% of the labels belong to non-duplicate labels. I have trimmed the dataset by taking equal number of duplicate and non duplicate set of questions and rejecting the remaining non duplicate labels. Although not a good option to do this, I did this as a simple solution to the unbalanced dataset probelm. 
2. Next there were two missing values in the dataset. I removed those rows.
3. The dataset consists of id, qid1, qid2 columns which do not contribute any useful information and so I remove those columns. 

********************************************************************************************************************************************************************************************************************************************************************************

## Feature designing 
Every row of data <b>contains</b> two questions and the label - 1 for duplicate or 0 non duplicate. So unlike other datasets which have features contained in them, this dataset requires us to create features from the two sets of questions. Our goal is to detect if the two 
questions are duplicates or not. 
********************************************************************************************************************************************************************************************************************************************************************************

## Machine Learning Models 

* Piece of code 
```
Test
```

********************************************************************************************************************************************************************************************************************************************************************************

## Futre Scope

********************************************************************************************************************************************************************************************************************************************************************************

## References


********************************************************************************************************************************************************************************************************************************************************************************


