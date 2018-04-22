********************************************************************************************************************************************************************************************************************************************************************************
# Quora-dataset-challenge

********************************************************************************************************************************************************************************************************************************************************************************
## The Dataset 
**Introduction:**
The [Quora] (https://www.kaggle.com/c/quora-question-pairs/data) dataset challenge is about predicting whether two questions have similar meaning or not.It is important for Quora to detect duplicate questions to save space and avoid the hassle of answering the same questions for the users.The goal of this project is to explore natural language processing techniques and integrate them with neural networks.

****************************************************************************************************************************************

**Data Preparation:**

1. The dataset is unbalanced with almost 64% of the labels belong to non-duplicate labels. I have trimmed the dataset by taking equal number of duplicate and non duplicate set of questions and rejecting the remaining non duplicate labels. Although not a good option to do this, I did this as a simple solution to the unbalanced dataset probelm. 
2. Next there were two missing values in the dataset. I removed those rows.
3. The dataset consists of id, qid1, qid2 columns which do not contribute any useful information and so I remove those columns. 

********************************************************************************************************************************************************************************************************************************************************************************

## Feature designing 
Every row of data contains two questions and the label - 1 for duplicate or 0 non duplicate. So unlike other datasets which have features contained in them, this dataset requires us to create features from the two sets of questions. Our goal is to detect if two questions have the same meaning even though they contain different words. So we need features that can extract semantics out of the sentence. For example: 
Question 1 - Astrology: I am a Capricorn Sun Cap moon and cap rising...what does that say about me?
Question 2 - I'm a triple Capricorn (Sun, Moon and ascendant in Capricorn) What does this say about me?
Here although the words in both the sentences are different, the meaning is the same. 

So we need to find out the features that explain the meaning of the sentence. In this project I have used some features that can help in understanding the meaning and some features that do not do so but they can sense if the two sentences are similar in their structure such as the number of characters, words and so on. 



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


