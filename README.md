# 2nd_team_project_NLP
## 1. Amazon Alexa Review Classification
## 2. Yelp Review Classification

### Objective of projects
- Discover insights into consumer reviews and perform sentiment analysis on the data and wrangling with unbalanced dataset

### My role
Worked more that 20 hours a week as a data scientist within a team of 4 to produce visualizations of reviews using Matplotlib, Seaborn, Wordcloud and learned how to deal with unbalanced dataset.

### Data
#### Amazon Alexa dataset
1. Amazon Alexa review dataset is very unbalanced (2893 positives review vs 257 negative reviews or 91.8% vs 8.2%).
2. Variation of different products of Alexa is not even and have more than 10 varieties (high cardinality).
3. The review length is also different for both positive and negative reviews.

#### Yelp dataset
1. Yelp review dataset is also very unbalanced (3337 positives review vs 749 negative reviews or 81.7% vs 18.3%).
2. The review length is also different for both positive and negative reviews.

### Models and Tools Used

1. Penalizing with parameter class_weight = 'balanced'
2. Balancing the class before classification from sklearn.imblearn: RandomUnderSampler, RandomOverSampler, SMOTE, NearMiss
3. Using of specific balanced algorithms from imbalanced-learn:
- BalancedRandomForestClassifier
- EasyEnsembleClassifier,
- RUSBoostClassifier
- BalancedBaggingClassifier

### Results and Insights:
- In the case of an imbalanced dataset, I would choose algorithms where you can tune the class_weight = 'balanced' parameter (e.g. logistic regression, some ensemble models)

- Also, you can apply strategies to balance the dataset, but the result may not always be better than if we did not change the balance

- Under-sampling can help improve run time and storage problems by reducing the number of training data samples when the training data set is huge.

- Over-sampling unlike under-sampling, this method leads to no information loss. Outperforms under sampling.

But it increases the likelihood of overfitting since it replicates the minority class events.

- And also I tested specific models from scikit-learn imbalanced library.

 -> In accordance with the results of the tested models, the best estimate was shown by VotingClassifier in amazon review dataset.
