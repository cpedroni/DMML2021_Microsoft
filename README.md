# Data Mining and Machine Learning 2021 - Team Microsoft
## *Detecting the difficulty level of french texts*

Team members :
- Melinda Femminis
- Estelle Valerie Tsague Mbialeu
- Catherine Pedroni

## Project description

Thsi project is part of a kaggle [competition](https://www.kaggle.com/c/detecting-the-difficulty-level-of-french-texts/overview). The main goal of this competition is to be able to predict the difficulty level of a french text according to the [The Common European Framework of Reference for Languages](https://www.coe.int/en/web/common-european-framework-reference-languages) that describes 6 level of language : A1, A2, B1, B2, C1, C2. 

## The data

For this project we have two dataset. The first dataset called `training_data` has three features : id, sentence, difficulty. The second dataset called `unlabelled_test_data` has only two features : id and sentence. By training several models we are going to try and predict the difficulty level for the `unlabelled_test_data` with the best accuracy score possible.

## First results

|                     | Logistic regression |       KNN        |   Decision Tree      |   Random Forest     |
| ------------------- | ------------------- |----------------- | -------------------- |-------------------- |
| Precision           | 0.48                | 0.45             | 0.31                 |  0.38               |
| Recall              | 0.48                | 0.27             | 0.31                 |  0.37               |
| F1-Score            | 0.48                | 0.34             | 0.31                 |  0.38               |
| Accuracy            | 0.48                | 0.27             | 0.31                 |  0.37               |

We can clearly see on this table that the best model is the logistic regression. An interesting see to observe is that for both the regression and the decision tree, all score (Precision, Recall, F1, Accuracy) have the same value. This means that we have as many false positives as false negatives. For our knn model, we can observe a clear difference in the scores' values. The difference between precision and recall will probably mean that the confusion matrix won't display a clear diagonal as opposed to the regression matrix or decision tree matrix.
Overall, this results could still improve but are however above the baseline of 0.169


## Methodology
After Loading the training_data and doing some Exploratory Data analysy, we' ve done several step to build our classifier :
* split the dataset  in 2 set 80% for training and 20 % for test set
* create the function called 'metrics' to print the classification report ( accuracy, precision, recall, f1 score)
* create different  TfIdf vectoriser with some basics parameters (sublinear_tf= True,,  tokenizer=word_tokenize,ngram_range= (1,1)..)  
* test different models such as Logistic regression , Knn, DecisionTree , RandomForest to get the one that gives the best accuracy. after this step, we try our model on the unlabeled data to analyse how good it detect the difficulty.
 To perform the accuracy , we did the
    * preprocess that consisted in removing punctuation, stopword,X most/least frequent words and to do the stemming  
    * reduce the number of feature using the SVD( instead of 3000 circa we' ve used 900)
    * try other models such as multinomial, neural networks with Keras, Support Vector Machine
Unortunatelly , all these methods and models didn't improve the classification report in a significant way 





## Our Video

[![DMML 2021 - Groupe Microsoft | Detecting the difficulty level of french texts](https://res.cloudinary.com/marcomontalbano/image/upload/v1639949988/video_to_markdown/images/youtube--E2dCIjSSVVc-c05b58ac6eb4c4700831b2b3070cd403.jpg)](https://www.youtube.com/watch?v=E2dCIjSSVVc "DMML 2021 - Groupe Microsoft | Detecting the difficulty level of french texts")
