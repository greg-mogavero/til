# Basics of Logistic Regression

The goal of logistic regression classifiers (and yes, they are classifiers despite the name), is to find the probability of a data point belonging to a class (we'll call this class the positive class). Logistic regression does this by linearly separating the data with a decision boundary. A point that is farther away from this boundary means the model is _more confident_ about its classification. Because the formula for this boundary is just a linear equation, it ranges from -∞ to ∞. When we plug in a data point X and get a value between (0, ∞), it corresponds to X belonging to the + class with probability between (0.5, 1.0]. Similarly, if we get a value between (-∞, 0), it corresponds to a probability between [0.0, 0.5), meaning it is more likely to belong to the negative class. A value of 0 corresponds to a probability of 0.5, meaning the point lies on the boundary and the model isn't sure which class it belongs to. These ranges will be important soon.

It's now time to define the __odds ratio__. The odds ratio is simply the probability of belonging to the positive class divided by the probability of belonging to the negative class.

OR(X) = P(X)/(1 - P(X))

This function has a range of [0, ∞). We can solve for the probability: P(X) = OR(X) / (1 + OR(X))

Let's remember where we are: we're trying to find the probability that X belongs to the positive class, but we only have this linear decision boundary with a range of (-∞, ∞). The odds ratio almost has what we need -- it's a function of the probability, but we can't use it without doing something about its range.

Let's take the natural logarithm of the odds ratio. This is called the __log-odds__, or __logit__, and note how it now ranges from (-∞, ∞)! Let's just _define the boundary function as the log-odds of X_. If we call the boundary function t, then we get e^t = OR(X), and thus, P(X) = (e^t)/(1 + e^t)! So now, we can obtain the probability of X belonging to the positive class simply by plugging in the output of the boundary function.

### But wait... how do we get the boundary function?

The answer to that will have to be in another post! But it involves _maximizing the likelihood that any data point will be classified correctly_, which is also known as the __maximum likelihood estimation__. 

##### [Reference](https://codesachin.wordpress.com/2015/08/16/logistic-regression-for-dummies/)

