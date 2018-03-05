# Lesson 2: Naive Bayes
Example of Arcerous vs. Non-Arcerous using a horse as a target and providing numerous examples of what is arcerous and what is non-arcerous.
* Need to identify **features** of the object to be classfied, such as colour, size, number of legs etc. Machine learning can classify objects into classes by using examples that it can learn from.
* This is called **supervised classification**. The system learns from **tagged** examples.

## Features & Labels
* We input **features** and try to input **labels**.
* We determine features of music, and then we take a person's interest as Like or Dislike.
* Use a **scatterplot**

## Stanley Terrain Classificiation
* Features: steepness (grade) and bumpiness
* Using scatter plots
  * Make predictions of new points when viewing a dataset
* Decision Surfaces
  * A **decision surface** separates one class from another so we can generalize to new data points.
  * linear decision surface
  * Exercise: Given a set of data points (two classes of points) and 3 possible linear decision surfaces, have the students choose the most reasonable decision surface to help classify new points into either class

> "A **machine learning algorithm** takes in data and transforms it into a **decision surface**." - Sabastian Thrun

# Naive Bayes
**Naive Bayes** is an algorithm used to determine a decision surface!
* 750 data points from the driving dataset (2 classes), using Python
* Get started with `sklearn`
  * Google `sklearn naive base` and use Gaussian Naive Bayes from `scikitlearn`
  * Contains lots of sample code you can start with
  * Use the GaussianNB module to create a **classifier**
  * Call the `fit()` function on your classifier to *train* the classifier on the training data. In that example, X are the **features**, Y are the **labels**. They are Python lists of ordered pairs.
  ```
   from sklearn.naive_bayes import GaussianNB
   clf = GaussianNB()
   clf.fit(*features*, *labels*)
   print(clf.predict(features_test))
  ```
  ## Accuracy
  After our classification algorithm runs and creates/plots a decision surface, we can measure or quantify how well the classifier did it's job. We can measure the accuracy of the classifier.
  
  This can be done with `sklearn` using the `score(X, y)` method as explained on the <a href="http://scikit-learn.org/stable/modules/generated/sklearn.naive_bayes.GaussianNB.html#sklearn.naive_bayes.GaussianNB.score">sklearn webpage</a>.
  
  Another technique was:
  ```
  from sklearn.metrics import accuracy_score
  print accuracy_score(pred, labels_test)
  ```
## Training and Testing Data
It is important that you train and test on 2 different sets of data. Otherwise you run the risk of **overtraining** your model and results using other data will not be accurate. Your model will not be able to generalize.

* Save 10% of your data for your testing set.

# Bayes Rule
Bayes Rule is the holy grail of **probablistic inference**. 
A brief discussion on probability, **sensitivity** of a test and the **specificty** <a href="https://en.wikipedia.org/wiki/Sensitivity_and_specificity">of a test</a>.

**Prior probability**: Probability before you run a test.
**Posterior probability**: Prior probabilty + evidence.

##Example
Imagine the chance of having cancer being 1% and the chance that a certain test can detect it is 90% if it exists.

Prior: P(C) = 0.01 or 1% - Probabilty of having cancer
       P(Neg|!C) = 0.9, P(Pos|!C) = 0.01 * 0.9 = 0.009
Posterior: P(C|Pos) = P(C) DOT P(Pos|C)
           P(!C|Pos) = P(!C) DOT P(Pos|!C)
                     = 0.99 * 0.1
                     = 0.099
                     
Normalize by adding the two values together.

Again: Posterior probalities require dividing by the *total* probability to normalize them.
See example of Chris and Sara regarding emails.

It's called **Naive Bayes** because it ignores word order.

Supervised Learning Algorithm

Why choose Naive Bayes?
* Easy to implement
* Quite efficient

Cons:
* Phrases with difference meanings
         
           
           
