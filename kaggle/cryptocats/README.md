# CryptoCats Kaggle Competition

This is a dump from a Kaggle kernel for the [How Much Would You Pay for A Fake Cat?](https://www.kaggle.com/c/how-much-would-you-pay-for-a-fake-cat) competition. This competition consists in predicting the asking price of cat NFT based only on its image and its cooldown time. I used this as an excuse to learn PyTorch and its vision-specific library TorchVision. 

In [my solution post](https://www.kaggle.com/competitions/how-much-would-you-pay-for-a-fake-cat/discussion/438369) there's a thorough explanation of my final submission which achieved the **1st** place out of 40 teams. The model consists of a pretrained-backbone (ResNet50, pretrained on ImageNet) whose classification head is dettached and replaced by a regression one, which is in turn equipped with a softplus activation for better representation of the targets which are strictly positive. The training procedure includes performing data augmentation, training on more epochs than usual for finetuning, clipping the targets, using a smoothed L1 loss and selecting the best performing weights on a sizable validation set, as measured by unclipped MAE.

While winning the competition was very rewarding, the major takeaway is learning the tools to work with vision tasks and finetuning pretrained models outside of the HuggingFace framework.

## Winning Solution

The accompanying notebook with the winning solution shows:

1. The EDA used to extract some information from the available data
2. The baseline model, based on robust statistics derived only from grouping training set samples by cooldown time category
3. The deep neural network model, alongside its design choices (and considered variants) and training+evaluation pipeline
