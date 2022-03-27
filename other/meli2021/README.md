# MeLi 2021 Data Challenge

This competition was hosted by [Mercado Libre in 2021](https://ml-challenge.mercadolibre.com/).

Given a pretty large dataset of (date, SKU)->sold\_quantity rows with extra features (minutes available, kind of shipping for that date, etc.) + an extra dataset of SKU-level information the task was to forecast a *distribution probability* for the stock-out day of a given target stock in the next 30 days. That is, what's the probability for each day in the next 30 days that I'll run out of stock for each SKU if I currently have X items in stock.

While facing hardware constraints (16 GB RAM, 3-core CPU) and not being available when the competition happened, I decided to pivot my approach and instead explore some other ideas.
Mainly, this approach consists of:
* Residual Analysis instead of EDA
* **Very** simple statistical models that make strong assumptions in order to make processing easier
* Some optimizing for efficiency of computation

## Versions

### base\_estimators

The challenge featured a workshop in which some tools were given (they are mentioned in the notebook). Mainly, a validation-set builder and two baselines: a uniformly distributed blind predictor and a expected-days-scaling-std gaussian model. Building upon that, some ideas were developed, including:
* Different scalings for the dispersion of the gaussian model
* Mixture of centrality measures for better & faster stabilization
* Bernoulli counting process based models, one with and another without a Zero Inflation component
* Expected-days as a predictor for both the target variable and row-conditioning

Even though this may look lackluster, according to my estimations the best model obtained here would have put me around rank 57, with the second best getting around rank 61. Notably, this is achieved without using **even a linear regressor**. Conclusions can be read at the end of the notebook.

**Disclaimer:** some *very* short run times are depicted in this notebook that do not correspond with actual computation times. The `@load_or_exec` decorator is defined in `result_save.py`, and what it does is intercepting the return value of an idempotent function and save it to disk so that later calls to the same function only read from the 'cached' result.
