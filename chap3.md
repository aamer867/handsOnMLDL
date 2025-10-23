# Measuring Accuracy Using Cross-Validation

This demonstrates why accuracy is generally not the preferred performance measure for classifiers, especially when you are dealing with skewed datasets (i.e., when some classes are much more frequent than others). A much better way to evaluate the performance of a classifier is to look at the **confusion matrix (CM)**.

## Confusion Matrices

The general idea of a confusion matrix is to count the number of times instances of class A are classified as class B, for all A/B pairs.

The first row of this matrix considers non-5 images (the **negative class**):  
53,892 of them were correctly classified as non-5s (they are called **true negatives**), while the remaining 687 were wrongly classified as 5s (**false positives**, also called **type I errors**).

The second row considers the images of 5s (the **positive class**):  
1,891 were wrongly classified as non-5s (**false negatives**, also called **type II errors**), while the remaining 3,530 were correctly classified as 5s (**true positives**).

A perfect classifier would only have true positives and true negatives, so its confusion matrix would have nonzero values only on its main diagonal.

---

An interesting one to look at is the accuracy of the positive predictions; this is called the **precision** of the classifier.

A trivial way to have perfect precision is to create a classifier that always makes negative predictions, except for one single positive prediction on the instance it’s most confident about.

It is often convenient to combine **precision** and **recall** into a single metric called the **F1 score**, especially when you need a single metric to compare two classifiers.  

The **F1 score** is the **harmonic mean** of precision and recall (Equation 3-3).  
Whereas the regular mean treats all values equally, the harmonic mean gives much more weight to low values.  

As a result, the classifier will only get a high **F1 score** if both **recall** and **precision** are high.

