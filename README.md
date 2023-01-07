# 2nd_team_project
## Amazon Alexa Review Classification
- Dataset consists of 3000 Amazon customer reviews, star ratings, date of review, variant and feedback of various amazon Alexa products like Alexa Echo, Echo dots.
- The objectives is to discover insights into consumer reviews and perform sentiment analysis on the data

1. Amazon Alexa review dataset is very unbalanced (2893 positives review vs 257 negative reviews).

2. Variation of different products of Alexa is not even and have more than 10 varieties (high cardinality).

3. The review length is also different for both positive and negative reviews.

4. I've trained models with alexa variation and new created features (like 'length'), but results were all overfitted. And trained with different variations of alexa. And results also were overfitted. So, I used only preprocessed text with TF-IDF vectorizer in training models.
In this study I've trained machine learning models with regularization (class_weight = 'balanced'), then implemented balancing methods and specific algorithms from scikit-learn.imbalanced library, and at the end used Voting Classifier.

*** Strategies how to fitting model on imbalanced dataset:

1. Penalize with parameter class_weight = 'balanced'
2. Balancing the class before classification: from sklearn.imblearn - RandomUnderSampler, RandomOverSampler
3. Use of specific balanced algorithms from imbalanced-learn:
- BalancedRandomForestClassifier
- EasyEnsembleClassifier,
- RUSBoostClassifier
- BalancedBaggingClassifier

### Insights:
- In the case of an unbalanced dataset, they do a better job of predicting models in which you can adjust parameter class_weight = 'balanced' (like Logistic Regression, some of ensemble models)

- Also, you can apply strategies to balance the dataset, but the result may not always be better than if we did not change the balance

- Under-sampling can help improve run time and storage problems by reducing the number of training data samples when the training data set is huge.

- Under-sampling can discard potentially useful information which could be important for building rule classifiers. The sample chosen by random under-sampling may be a biased sample. And it will not be an accurate representation of the population. Thereby, resulting in inaccurate results with the actual test data set (in my case, SVC).

- Over-sampling unlike under-sampling, this method leads to no information loss. Outperforms under sampling.

But it increases the likelihood of overfitting since it replicates the minority class events.

- And also I used specific models from scikit-learn imbalanced library. They also scored not bad.

 -> In accordance with the results of the tested models, the best estimate was shown by VotingClassifier.
