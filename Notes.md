## Hyperparameter tuning

Hyperparameters are parameters that are not directly learnt by the model. They control the capacity of the model.

The parameters of the model are intrinsic t model equation and are optimized during training. Hyperparameters are defined before training and constrain the algorithm.

A search of a hyperparameter consists of:

- Hyperparameter space
- A method for sampling candidate hyperparameters
- A cross-validation scheme
- A performance metric to optimize

Low effective dimension: Some hyperparameters dimensions don't matter so much, they don't impact the cost that much.

## Performance metrics

Use `make_score` to use a custom scoring function in scikit-learn.

## Cross-validation

### Schemes

- **K-fold cross-validation**: The higher the K, the bigger the training set for each one of the k models 
- **Leave-One-Out cross-validation**: Computationally expensive + Some metrics can't be estimated when we have one observation in the test fold
- **Leave-P-Out cross-validation**
- **Repeated K-Fold cross-validation**: Repeat a # of times (shuffle the data + K-fold CV)
- **Stratified K-fold cross-validation**: Same as K-fold, but with the real proportion of observations of each class - Useful with imbalanced data

Some data may not be independent or identically distributed (Grouped data from the same subject, time series, etc) and normal cross-validation cannot be applied and a scheme from the **grouped cross-validation** family should be used instead. 

- **Grouped K-fold cross-validation**
- **Leave-One-Group-Out cross-validation**
- **Leave-P-Out cross-validation**
- **Cross-validation for time-series**: Successive training sets are supersets of those that come before them (Image below from scikit-learn doc).

![image-20210811220550203](_assets/Notes/image-20210811220550203.png)

Some advanced schemes are:

- Nested cross-validation: We do two cross-validations, one to get the best model and one to get a better estimate of the generalization error. With every loop in the generalization error cross-val, one gets a new model and ends up then with many models at the end. The difficulty is to decide what to do with them!

