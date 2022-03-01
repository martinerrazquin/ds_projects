# Predicting Rains in Australia

This is a Python (pseudo-)port of a final project for the **Statistical Learning** postgraduate course taught at FI-UBA. 

Given a dataset consisting of several weather measurements, the task is to predict whether tomorrow will rain or not (binary classication problem). The assignment, though, emphasized the importance of evaluating the feasibility of the task, assessing advantages and disadvantages for each model and not "just maximizing accuracy".

Although not all the work was ported, it retains the core features:

* Subsetting the original dataset through different policies and representativity checks
* Exploration of marginal distributions both for insights and encoding assessment
* Consideration of multi-collinearity and highly-correlated groups of features
* Evaluation of different models, favoring both parsimony and recall based on business rules
* CV-based mean and $1_{SE}$ optimization of a $L_1$-penalized logistic regressor
* Conclusions about dropped and preserved features, representativity of data subsets and estimated performance for the final model.
