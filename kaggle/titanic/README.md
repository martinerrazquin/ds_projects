# Titanic Kaggle Competition

This is a dump from a Kaggle kernel for the [Titanic - Machine Learning from Disaster](https://www.kaggle.com/c/titanic/overview) competition.

## Versions

### Titanic1

This notebook achieves a decent public leaderboard score of around $0.7511$ (accuracy), although there was no heavy focus in leaderboard-score-oriented model tuning nor feature engineering. It instead emphasizes usage of different libraries such as:

* *Matplotlib/Seaborn* for different insightful plots during EDA.
* *Pandas* for data analysis and manipulation.
* *Scikit-Learn* for data preprocessing (imputation, encoding/transformation, pipelining) and model training + evaluation (through CV unbiased scoring)
* *XGBoost* for the model itself
* *Hyperopt-sklearn* for hyperparameter tuning for both *ExtraTrees* and *XGboost* classifiers