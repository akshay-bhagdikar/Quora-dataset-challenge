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

So we need to find out the features that explain the meaning of the sentence. In this project I have used some features that can help in understanding the meaning and some features that do not do so but they can sense if the two sentences are similar in their structure such as the number of characters, words and so on. Next, I list the features and my thought process behind selecting those features. 



********************************************************************************************************************************************************************************************************************************************************************************

## Features
 
<b>Feature 1) Word count difference</b>
Similar thoughts can be expressed in two different ways but generally the number of words would not differ much. The important words would mostly remain the same or will be replaced by their synonyms. The difference in the word count would be mostly because of addition/removal of stop words. So higher the difference in word count, higher are the chances that the two sentences differ in meaning. 

<b>Feature 2) Last word check</b>
This feature checks if the last words of the two sentences match. If they match the value is 1 and 0 otherwise. After visualizing the dataset I found that many of the non duplicate questions ended in same word. So I have used this feature out of observation. 

<b>Feature 3) First word check</b>
The first word of a question sentence is the question word. It represents the tone of the question. For example questions starting with "where" are about a place, questions starting with "when" are about time and so on. So two questions with similar meaning would generally have the same question word and hence this feature. This feature is 1 if the first words match and 0 otherwise. 

<b>Feature 4) Character difference</b>
This feature states the difference in character counts of the two sentences. Generally two questions with similar words will have same characters. Higher the value of this feature, more disimilar the characters and hence have higher dissimilarity in the structure and hence higher are the chances that the two sentences are different. 

<b>Feature 5) Word similarity</b>
The first thing that comes to our mind when comparing two sentences for their similarity is the count of similar words. More the number of same words in the two sentences more are the chances of them giving out the same information. This feature finds the count of similar words after removing the stop words. 

Features 6 - 9 are based on different ratios calculated using the fuzzy wuzzy library. This library calculates the fuzzy matching of two strings. Closer the ratio to one more is their similarity quotient.

<b>Feature 6) Simple ratio</b>
This ratio is calculated by finding out the Levenshtein distance of the two strings. So it basically just checks for similar characters and group of characters. 

<b>Feature 7) Partial ratio</b> 
This ratio is suitable for sentences that are of different lengths. If the shorter string is length m, and the longer string is length n, we’re basically interested in the score of the best matching length-m substring. 

<b>Feature 8) Token sort ratio</b>
The token sort approach involves tokenizing the string in question, sorting the tokens alphabetically, and then joining them back into a string. This way we overcome the problem of two sentences that have same words but are out of order. 

<b>Feature 9) Token set ratio</b>
This approach tokenizes the sentences into words, then figure out their intersection and remainder. So it basically finds three sets-
a) (Sorted intersction set) which contains the sorted common words 
b) (Sorted ntersection + remaining part of sentence 1) which contains the sorted commonn words + words which contain the remaining part of sentence 1
c) (Sorted ntersection + remaining part of sentence 2) which contains the sorted commonn words + words which contain the remaining part of sentence 2 
and then these three strings are compared. 

<b>Feature 10) word2vec score/b>
Word2Vec is an important NLP technique. Word2vec is a two-layer neural net that processes text. Its input is a text corpus and its output is a set of vectors: feature vectors for words in that corpus. It turns text into a numerical form that deep nets can understand and then the neural network computes similarity between two words based on the corpus. I have used this module to calculate the vectors for every word in a question and sum it up. So I get a vector for every question. Then I calculate the difference vector by taking the difference of the two vectors of the two questions to be compared. If two questions are related then the difference vector elements are supposed to be close to zero in value. Then I sum up the elements of the difference vector. Again lower this value higher are the chances for the two questions to be similar. 



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


