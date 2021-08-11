### Hyperparameter tuning

Hyperparameters are parameters that are not directly learnt by the model. They control the capacity of the model.

The parameters of the model are intrinsic t model equation and are optimized during training. Hyperparameters are defined before training and constrain the algorithm.

A search of a hyperparameter consists of:

- Hyperparameter space
- A method for sampling candidate hyperparameters
- A cross-validation scheme
- A performance metric to optimize

Low effective dimension: Some hyperparameters dimensions don't matter so much, they don't impact the cost that much.

### Performance metrics

Use `make_score` to use a custom scoring function in scikit-learn.