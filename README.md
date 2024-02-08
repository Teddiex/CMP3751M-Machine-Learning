# Machine Learning Workshops

This repository contains the material for the Machine Learning workshops, including model creation and evaluation using Python for models such as SVM, Random Forest, Ensembles, KNN, and ANNs from scratch. 

# Machine Learning Assessment

This folder contains the jupyter notebook with the pdf file for the assessment. In this assessment a singular simple model was created and evaluated on a dataset predicting the class of a battery. Then a grid search was performed to find the best parameters for other models. Finally, the best model was chosen and evaluated using metrics such as precision, recall, and f1-score, with a confusion matrix created to visualise the results.

## Feedback

"Implementation 82/100

Loading the dataset: Your solution is correct with all the required elements.
Simple classification model - Creating train/test sets: Your solution is correct with all the required elements.
Simple classification model - Training a classifier: Your solution is correct with all the required elements.
Improved evaluation strategy: Your implementation correctly calculates one or more metrics beyond accuracy, both summative and a complete set of per-class metrics (such as precision+recall, or sensitivity+specificity, or f1-per-class), uses an advanced model selection strategy such as cross-validation, and selects a metric which takes class imbalance into account.
Different models and parameter search: Your solution is correct with all the required elements: you systematically compare three different models (e.g. using GridSearch or a similar approach), and consistently chose the best variant of each model.
Ensembles: Your solution shows some basic steps to attempt constructing bagged models, but is either incorrect or does not improve on any of your previous models (with no evidence of attempting to improve the performance of the bagged models).
Final model evaluation: Your solution is correct with all the required elements.

Discussion 78/100

Loading the dataset: A complete description of the dataset is provided, and handling of missing values has been both described and justified.
Simple classification model: You provide some discussion, but do not comment on all the required elements (both the advantages and shortcomings of the proposed data split, shortcommings of the current evaluation metrics, no comment on model performance).
Improved evaluation strategy: Your discussion fully supports your implementation by explaining the choice of model evaluation and metrics, describing at least one summative metric other than accuracy and explaining the need for a full set of per-class metrics (e.g. combination of p+r, specificity+sensitivity, OR per-classs-F1)
Different models and parameter search: You provide an in-depth discussion of the proposed evaluation strategy, with some minor incorrect conclusions or missing elements (e.g. you do not compare the performance of the 3 models).
Ensembles: You provide some discussion but it is either descriptive (what was done but not why), or generic (describes bagging and voting ensembles in general but not in context of the results you have obtained).
Final model evaluation: Your solution is detailed, and comments both on the overall model performance using a summative metric, and per-class performance using the confusion matrix and any additional available information.


Notebook:
The notebook runs without any run-time errors, and the format of your submission follows the requirements set out in the brief.
Additional comments:
An amazing set of visualisations and a great amout of info output by your implementation. Some very in-depth analysis, including into the actual meaning and interpreation of the features (that was already beyond the scope, but nice work, well done). A small detail which you missed to comment on (but do so later) is the class imbalance, which will be important later.

Your implementation of a simple model and basic evaluation strategy is correct, and the discussion touches on some important aspects: 20% of the data takes a lot away from the model (but also, since the dataset is small, it also results on reporting the result on a very small amount of samples, <70). You correctly note the potential problems with high variance, however you don't notice that the split doesn't care about the class imbalance. You correctly diagnose that a classifier predicting only the majority class could perform 'relatively well', but it would be better to provide some explicit numerical lower bounds (e.g. 33% for random guessing, 41% for majority class), rather than an arbitrary limit of <0.5.

You select a small number of evaluation metrics, but they satisfy all the task requirements: you have both summative and per-class metrics, and furthermore your chosen metrics (f1 and balanced accuracy) take class imbalance into account. You justify your choices well in your discussion, including why using stratified cross-validation is a good idea.

You implement a good example of parameter search, with a good selection of classifiers. Your discussion is also on point and insightful, with some inconsistencies. First, while model selection based on MCC is indeed a good idea, it is not clear why you didn't include this metric in your evaluation procedure when you had a choice of selecting any metrics you tought would be good. Then, after using that for model selection, you fall back on comparing F1 scores. You also miss one key problem with applying the GridSearcCV the way you do: since it performs cross-validation, the final parameters were chosen based on the results which are later reported as the testing results, so there's some data leakage. (Alternative approaches resolving this problem have their own downsides; it is good to note them explicitly).

You try only a basic bagging combination, without trying out different parameter combinations. Thank you for 'n_jobs=-1'. Your discussion of the obtained results is correct, but it's a shame that you fix your max_samples (and max_features) to 1 as that goes against the basic idea of bagging. Bagging should attempt and combine slightly different classifiers, obtained by subsampling features and samples, and allowing each model to reach the decision slightly differently (typically, 70-90% samples and features are used). While your DecisionTree performance improves substantially, it's not clear whether you could further improve your other models by searching through different % of subsampling your features and samples.

You provide a nicely labelled confusion matrix, and a nice discussion on the model improvements achieved from the original model to the best one chosen for this final task. Overall, very good work.


Total mark: 82*0.55+78*0.45=81"
