# Cleaning data
X_train and y_train are bijective (len(X) == len(y))
Y_pred, y_test, and X_test are trijective (len, len, len...)
How is data adapted to be ideal input for a given ML algorithm?
How does a method take input to produce output? 
If we have to simplify input for an algorithm to work:
  How to represent without losing important information (How to define importance of information? How to rank?)
There may need to be methods/algorithms for evaluating the importance of data components for making stastical inferences
If I can compress the data (.jpeg) and get 'practically' the same image (RGB) as an uncompressed (.raw) or other file (.png) -- because my compression algorithm 'filters' data: what 'skeleton' faithfully represents the image? What's redundant? 
This means that the algorithm has some measure of redundancy
Likewise, could there be general compression algorithms for data?
Can I know what bits can be sifted out for various representations of real things?
Is it possible to feed the learning algorithm to be used, the training data, and the target;
  into an algorithm/function, and receive a representation of the training data which practically gives the same accuracy as a lossless data format? Isn't this the same as training the model on the data? The point is to save time.
  This is why a general method would be useful, for figuring out how to clean data, and only feed what is necessary for inference? But if the data is lossy, then the shape of patterns is reduced -- forms lose their meaning, and the idea of weighing the meaning of diverse shapes makes the model ----- but wait -- we want this for a particular dataset,
  which is to be used to train a particular model (by a particular alg) for a particular target! That is -- .jpeg compresses *images* (obviously). It's not an algorithm we'd expect to preserve the most significant bits of an audio file. (We'd use ~.mp3 for that.)


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
