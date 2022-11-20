# Hearthstone deck completion Kaggle Competition

This is a dump from a Kaggle kernel for the [Hearthstone - What card should I select next ?](https://www.kaggle.com/competitions/what-card-should-i-select-next/overview) deck building competition. This is a very interesting competition in the sense that deck completers are a case of System Recommenders that feature uncommon constraints. 

In [my solution post](https://www.kaggle.com/competitions/what-card-should-i-select-next/discussion/363487) there's a thorough explanation of my final submission which achieved the **5th** place, comprised of the included PopPair model, a hyperparameter-tuned Multinomial VAE and some other, far-less-useful models, all ensembled through a LightGBM Reranker. The reranker's feature importances show that the ensemble is actually working as a booster for PopPair as most of the votes are made by this base model, confirming its predictive power despite its simplicity.

## Versions

### PopPair model

This simple model, also available as a public kaggle notebook [here](https://www.kaggle.com/code/martinerrazquin/hs-cleansing-basic-model/notebook), achieves a very competitive $0.64714$ MAP@3 private LB score which would have ranked 7th (top 19%) in the competition w/o ensembling+reranking. Focus is made on cleansing, exploration and exploitation of key findings in the dataset (e.g. *Pair* and *Duplicate* corrections).
