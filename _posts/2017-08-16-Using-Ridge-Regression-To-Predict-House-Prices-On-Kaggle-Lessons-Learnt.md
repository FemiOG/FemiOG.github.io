---
layout: post
title: "Using Ridge Regression to Predict House Prices on Kaggle - Lessons Learnt"
date: 2017-08-16 
---
---
I challenged myself last month to build a model every month for the rest of the year while covering most machine learning methods such as supervised (Regression and Classification) and unsupervised learning (Clustering and Dimensionality Reduction)  

So far I think I’m still on track considering I started a Machine Learning Engineer Nanodegree on Udacity leaving me with less time for other things I planned to do but nevertheless, I will try to complete the challenge.  

For the month of July I decided to pick a regression problem on Kaggle, which involves predicting house prices in Ames, Iowa.  

I’m going to pick just 3 new major stuff I finally figured out while building the model.  

* Feature Scaling (Standardisation)
* Regularisation
* PCA  

**Feature Scaling (Standardization)**  

Simply put, its scaling features so we have them on the the same scale.

I struggled to understand the reason behind doing feature scaling. I mean why can’t I just throw in my features of different scales into my model without having to transform them? Here’s why (Shout out to Akinkunle Allen for breaking it down while explaining how SMOTE works)  

Most machine learning algorithms operate in the vector space which might include calculations like euclidean distance between vectors e.g KNN, K-Means, SMOTE.  

Having features on different scales would cause features with high range to bully features with a lower range in the vector space while performing calculations.  

<!-- <p>
  <img src ="{{"assets/images/ridge-regression/data-preview.jpg" | absolute_url }}"/>
</p> -->
![yo]({{"assets/images/ridge-regression/data-preview.jpg" | absolute_url }})

I’ll try listing out classes of algorithms that standardization improves it’s performance.  

* Algorithms that uses euclidean distance e.g KNN.
* Those that involve learning rates e.g regularization techniques.
* Algorithms that use gradient descent for optimization.
* Principal Component Analysis  

Though I think the 2nd & 3rd are kind of the same.  

I’ll recommend this [article](http://sebastianraschka.com/Articles/2014_about_feature_scaling.html#about-standardization) to better understand feature scaling and when to use it.  

Finally, if I decided to use regularization (which I did) for my model or wanted to use PCA to capture some underlying structure in my features (which I plan on doing) standardization would come in handy.  

**Regularization**  
This is an attempt to prevent overfitting by penalizing the cost function. As more features are added to the dataset the model becomes more complex and overfitting is bound to happen.  

So what regularization does is to introduce a regularization parameter which essentially penalizes the feature with large weights. Hence, for features with large weight the regularisation parameter minimizes it. The intuition is, if all our feature weights are somewhat relatively small, the complexity of our model is reduced.  

Doing the project I decided to try out different algorithms to see how they compare (just for the fun of it…I knew already that I wanted to use a linear model). So below are the scores from the ‘experiment’.  

<p align="center"> 
  <img src ="{{"assets/images/ridge-regression/model-comparison.jpg" | absolute_url }}"/>
</p>

Obviously my linear models (Linear Regression & Ridge) outperformed others in terms of generalization. But the trade-off between the training set score and cross validation score of the ridge model (which is a regularization option for linear regression models) seems good enough, even slightly better than the linear regression model.  

You can read this [article](http://www.chioka.in/differences-between-l1-and-l2-as-loss-function-and-regularization/) to learn about different regularization options and their use cases. Also, Andrew Ng gave a very good introduction in his machine learning coursera course under the section “Regularization” in week 3.  

**PCA**  
Principal component analysis is a dimensionality reduction technique that works by projecting high dimensional data onto a plane of lower dimension while trying to minimizes the projection error.  

For example given a 2 dimensional dataset, what PCA does is to try to find directions in the plane that captures most variance in the data points whilst trying to minimize the projection error.  

<p align="center">
  <img src ="{{"assets/images/ridge-regression/pca.jpg" | absolute_url }}"/>
</p>  

PCA is useful in cases where you have latent features. Let me deviate a bit, latent features are features that capture the same concept in our problem.  

Contextually, in predicting house prices, features like square footage and number of rooms describes a concept (latent feature) like size, also features like neighborhood safety and schools generally describes the latent feature, neighborhood. Applying PCA to this dataset of 4 features reduces it to just 2 essential features which makes it easier to visualize their relationship.  

I’ll not be diving deeper into PCA (though I really want to). I only highlighted it because for my next machine learning project, I will be using PCA to understand the features and see how the number of features can be reduced. And hopefully I get to write an article about what I learnt doing it.  

---

I made it to the top 23% on the competition leaderboard with my ‘simple’ model and you can check out my [notebook](https://github.com/FemiOG/Linear-Regression-Model-For-House-Prices-Ames) for the model.

I look forward to writing about my experience on the next project.



