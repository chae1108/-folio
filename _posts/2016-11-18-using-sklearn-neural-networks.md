---
layout: post
title: Using Scikit learn Neural Networks
date: 2016-11-17 14:09:00
description: Predicting Political Affiliation based on Congressional Voting Records.
img: /img/1.jpg
---
The full code used is available on [Github](https://github.com/chae1108/congressional-voting-1984).

In this project, a MLPClassifier (Multi-Layer Perception) model was used on a house-votes dataset to predict whether the vote came from a Republican or a Democrat.  I used the newly-implemented neural networks component in Scikit-Learn version 0.18 to build the model.

The dataset was obtained from [UCI Machine Learning Repository](https://archive.ics.uci.edu/ml/datasets/Congressional+Voting+Records). The Congressional Voting Records Dataset contains the following 16 key votes by the U.S. House of Representatives:

1. handicapped-infants
2. water-project-cost-sharing
3. adoption-of-the-budget-resolution
4. physician-fee-freeze
5. el-salvador-aid
6. religious-groups-in-schools
7. anti-satellite-test-ban
8. aid-to-nicaraguan-contras
9. mx-missile
10. immigration
11. synfuels-corporation-cutback
12. education-spending
13. superfund-right-to-sue
14. crime
15. duty-free-exports
16. export-administration-act-south-africa

Below code snippet shows how MLPClassifier can be used:
{% highlight python %}
from sklearn.neural_network import MLPClassifier
mlp = MLPClassifier(hidden_layer_sizes=(20,20,20))
mlp.fit(X_train,y_train)
predictions = mlp.predict(X_test)
{% endhighlight %}

Nothing unusual. Using Neural Networks is similar to using any other machine learning algorithms in Python.  After doing train-test-split, you load the model, then initialize the model + set parameters, fit the data into your model, and finally make predictions based on X_test data.

The model yielded the accuracy of 97%, which is great especially considering the amount of code it took to create the model.

The only thing that you need to pay attention to is making sure that StandardScaler is done to normalize the data.  This will allow the neural networks model to converge faster.

The full code used is available on [Github](https://github.com/chae1108/congressional-voting-1984).
