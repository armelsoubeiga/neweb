---
title: 'South African COVID-19 Vulnerability Map hackathon 24th place solution'
date: 2020-04-07
permalink: /posts/2020/04/zindi-south-africa-hack-covid
tags:
  - machine learning
  - competition
  - covid19
  - africa
---

Details of my solution ranked in top 14% (24 / 179) at a hackathon which goal were to predict areas with most risks of vulnerability for COVID-19 in South Africa

![leaderboard](/images/hack-zindi/south-africa-covid/leaderboard.jpeg)

The hackathon was hosted by [Zindi](https://zindi.africa) and the goal was to predict the percentage of households that fall into a particularly vulnerable bracket - large households who must leave their homes to fetch water using 2011 South African census data.
The hackathon was from April 3th 13:59 to April 5th 23:59 GMT. I joined it on April 4th.

My solution is ranked 24th over 179 is a linear meta-regressor of LightGBM, XGBOOST and CatBoost. A 5-Fold cross-validation (CV) were used for each model before the stacking, and each CV was iterated 10 times with different seed.

### Scores
The scoring function is the root mean squared error.
* CV LightGBM: 6.048 +/- 0.0332
* CV XGBOOST: 6.35 +/- 0.0634
* CV CatBoost: 5.914 +/- 0.0198
* Blend: 0.8 * predictions(oof_CatBoost) + 0.2 * (0.5 * (predictions(oof_LightGBM) + predictions(oof_XGBOOST))): 5.8164 Linear regression as meta-regressor: 5.8122

Private leaderboard: 3.975, first place score: 3.512.

In the feature engineering step a created new features as follow:
* rounding total_households and total_individuals variables to be of type int, and computing the number of individuals per household total_individuals/total_households.
* adding statistics of each data object as the mean, standard deviation, skew, percentiles
* creating polynomial features with interactions of degree 2 of the 10th most important features
* adding the maximum index of same group of variables (let set A is a variable and has a domain of responses a, b, c, in this competition the probability of each response were created as new variable of each response in the training and test data, so with have A_a, A_b, A_c. Computing the index of the maximum on the later variables will help to have the response category having the highest probability).
* adding cumulative odds-like of each group of variables. Since a lot of variables are probabilities this will help models to better capture interactions between responses of a group of variables.

### What worked
* Most of the variables described above contribute to improving the score.
* CV with different seeds and shuffling helped a little bit to improve the score
* Blending CatBoost, XGBOOST and LightGBM as follow:
* blend = 0.8 * predictions(CatBoost) + 0.2 * (0.5 * (predictions(LightGBM) + predictions(XGBOOST)))
* since CatBoost gave the best CV scores in the local. This helped to improve the score.
* The linear stacking with linear regression: instead of fixing weights a preceding in the blending, I used linear regression as meta-regressor to compute optimal weights.
* Feature selection with SelectFromModel on LightGBM (use on train set containing all feature engineering techniques +
* 25*5-Fold CV with different seeds of LGBM
* 25*5-Fold CV with different seeds of XGBOOST
* 25*5-Fold CV with different seeds of CatBoost +
* Blending with linear regression.

### What didn't work
* Adding PCA and TSNE with two components as new variables. Even if the two variables improved the local CV score, the one the leaderboard decreased.
* Clustering the data and adding the clusters labels and aggregated data from these labels (mean of variables by cluster) as new variables.
* Count encoding the integers features.
* Transforming the target to log(1 + x) and taking the inverse of the predictions.
* Transforming the target to binary (target < 20? 0 : 1) and do target encoding of the 10th most important variables.
* Binning and label encoding of top 10th most important features.
*  Sequential layers with 4 hidden layers. I didn't tune the model architecture and hyperparameters due to the time. But, deep learning should have worked well.

### What could have improved the model
* More data cleansing for instance dropping outliers.
* Hyperparameters tuning.
* Adding more models in the stacking.
* Tuning the architecture of the deep learning model.
Note that a lot of experimentation is not shown in this notebook.

The source code is available **here**.
