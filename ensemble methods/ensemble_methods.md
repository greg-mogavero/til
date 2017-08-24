# Types of Ensemble Methods

Ensemble methods involve using a collection of weak learners (simple models whose only constraint is that they perform better than random guessing) to reduce bias or variance.

_Sequential_ ensemble methods use a series of base learners that build on each other. This exploits the dependence of the learners to boost overall performance by giving more importance to misclassified data points.

_Parallel_ ensemble methods generate all the base learners at the same time. This exploits the independence of the learners and can reduce overfitting by taking majority vote or averaging results for regression.

### Bagging

Bagging is a parallel ensemble method that involves generating multiple base learners trained on subsets of the training dataset, and then taking a majority vote or averaging the results. This reduces variance and thus is a useful tool to prevent overfitting.

Random forest classifiers are a popular choice for bagging. The base learners for random forests are decision trees that not only are trained on random subsets of the data, but also get random subsets of features.

### Boosting

Boosting is a sequential ensemble method where each base learner tries to correctly classify the data points that the previous learner misclassified. This is achieved by assigning more weight to the misclassified data points, so the error for misclassifying them again would be much greater. Boosting usually reduces bias.

Adaboost is a popular boosting algorithm.

### Stacking

Stacking is a parallel ensemble method whose base learners are often different types of classifiers. The base learners are trained on the entire training set, and their output becomes the input to a meta-classifier where each base learner is a feature.

#### Reference

https://blog.statsbot.co/ensemble-learning-d1dcd548e936