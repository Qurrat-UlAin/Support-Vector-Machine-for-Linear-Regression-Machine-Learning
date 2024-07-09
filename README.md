###Details:###
-Notebook1: simple data anlaysis 
-Notebook2: partitioning of data, we identified our target varaible which we have to predict. we create a sliding window, using min max scalre we created our matrices. we also have identified the fact that we'll be using 4 columns to rpedict one column (from the shape)
-Notebook3: linear kernel has only two parameters to be optimized: C and epsilon 
-Notebook4: Polynomial kernel has three parameters to be optimized: C and epsilon and degree
-Notebook5: Rdial Basis Kernel kernel has three parameters to be optimized: C and epsilon and gamma
###Important Things To Remember###
-C: This parameter controls the trade-off between achieving a low training error and a low testing error that is, between bias and variance. A lower C value makes the decision surface smooth, while a higher C value aims to classify all training examples correctly.
-epsilon: This parameter specifies the epsilon-tube within which no penalty is associated in the training loss function with points predicted within a distance epsilon from the actual value.
##Types of Kernel Used:##
-Linear:A kernel in SVM is a function used to transform the data into a higher-dimensional space to make it easier to separate using a hyperplane. The linear kernel is one of the simplest kernels, which does not transform the data but rather uses the original feature space. It is suitable when the data is linearly separable or when you want to perform linear regression.
-Polynomial: This kernel allows the algorithm to fit the model to polynomial relationships of the input features, which can be useful when the data is not linearly separable.
-RBF: The RBF kernel can map the input space into an infinite-dimensional space, allowing the SVM to create a highly flexible decision boundary. It's particularly effective when the relationship between the input features and the target variable is complex and not linearly separable.


##BayesSearchCV:##
-lsvr: The estimator object (SVR with a linear kernel) to be optimized.
-param: The parameter grid over which to perform the search.
-n_iter=15: Number of parameter settings that are sampled. This trades off runtime vs quality of the solution.
-cv=TimeSeriesSplit(n_splits=5, gap=w+1): Specifies the cross-validation splitting strategy. TimeSeriesSplit is used for time series data, where n_splits=5 means splitting the data into 5 folds and gap=w+1 introduces a gap between the training and test sets to avoid leakage.
-scoring=make_scorer(mean_squared_error, greater_is_better=False): The scoring function to evaluate the predictions on the test set. mean_squared_error is used here, and greater_is_better=False indicates that lower scores are better.
-n_jobs=-1: Uses all available processors to perform the search.
-refit=True: After finding the best parameter combination, refit the model using the entire training set.
-random_state=0: Ensures reproducibility by setting the random seed.
