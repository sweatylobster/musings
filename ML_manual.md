# Cleaning data
X and y are bijective (len(X) == len(y))
X is somewhat noisy.
If every element of X is an array of size (16, 16)

# Choosing a classifier
There's a flowchart on my Desktop.
First filter is problem-type. (3)
Second filter is n_samples (~10k)

1. Classification
2. Regression
3. Clustering

1 and 3 predict categories,
2 predicts quantities.
Clustering is classification without labels.
Regression is determination of 

# Model, data prep
0. all(X.shape), or uniform resolution of input
1. determine type of problem {clas, regr, clus}
  1. therefore specify X -> y

y_ret = {
'classification': 'category',
'regression':     'quantity',
'clustering':     'category'}


In classification, we learn from {X} to generate the solution, which is a category.
In regression, use X to generate quantities. 
In clustering, we interpret X  so as to represent their similarities in a way that yields clusters as numerous as the set of labels. So we should have len(set('setosa', 'virginica', 'versicolor')) == clf.n_clusters

# Classification workflow in a session
1. import visualization + classifier libraries
2. flatten images / prepare data
3. split data `X_train, X_test, y_train, y_test = sklearn.model_selection.train_test_split(data)`
4. define classifier `clf = svm.SVC(gamma=0.001)`
5. fit data to clf `clf.fit(X_train, y_train)`
6. use clf to generate predictions on test set `predicted = clf.predict(X_test)`
7. check score `metrics.classification_report(y_test, predicted)`
