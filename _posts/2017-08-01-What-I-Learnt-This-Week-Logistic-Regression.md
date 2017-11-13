---
layout: post
title: "What I Learnt This Week - Logistic Regression"
date: 2017-08-01
---
---
Ok so I decided to challenge myself to write about machine learning jargon I learnt or finally figured out over the course of my Machine Learning Engineer Nanodegree on Udacity (and hopefully beyond completion).

This is going to help me understand these topics even better. Also, this is my first attempt at any kind of writing and I hope to keep it short and concise.

<p align="center">
  <img src ="{{"assets/images/shall-we-begin.jpg" | absolute_url }}"/>
</p>
<!-- ![yo]() -->

One of the questions asked during this week’s project was to explain in layman’s term, how the machine learning algorithm I chose for the project works. The answer I gave was off the top of my head and I did not carry out any research due to my laziness. I was secretly expecting my reviewer to reject the explanation but lo and behold he/she commended it. So I decided to share it with the *same aim of explaining it to a non-technical audience* with a little more detail.
  

**Logistic Regression in layman’s term.**  
**Backstory:** Logistic Regression is a machine learning algorithm used for classification i.e (predicting whether something is true or not)  

The Logistic Regression algorithm works by learning weights of each features and a constant term from a training dataset. So that given a new observation it multiplies these weights by the corresponding features of our new observation, adding all the products plus the constant term and fitting the result in a special function (Logit Function) that scales it down to a number between 0 and 1 which can be interpreted as probabilities, with results lesser than 0.5 indicating a prediction of false and results greater than or equals to 0.5 indicating a prediction of true.  


*Did not understand any of the jargons i just said? Worry not!*
  

To put it into context given a person’s features like age, weight and height we can predict their sex. Logistic Regression learns the numerical weights of each features such as age, weight, height and a constant term from past data of several peoples age, weight, height and their corresponding sex.

<p align="center">
  <img src ="{{"assets/images/LR-Model.jpg" | absolute_url }}"/>
</p>


Using this diagram, let’s assume x1, x2 and x3 (Input) to represent the person’s age, weight and height respectively. The labels on each arrows representing the weights of the corresponding feature and the square symbol (whatever the color is) representing our special function. The output y representing the probabilities (between 0 and 1) of this person being either male or female.  


To predict the probabilities of the person being either male or female, the values of each features is multiplied by the corresponding weights. Then all the products are added together with the constant term to get a value. Then this value is passed into a special function that scales it down to a value between 0 and 1, with values lesser than 0.5 indicating that the person is female and values greater than or equals to 0.5 indicating that the person is male.
