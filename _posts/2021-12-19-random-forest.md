---
title: "Secrets of higher rating"
date: 2021-12-19
published: true
categories:
  - blog
tags:
  - Github Page
tags: [dataviz, altair, hvplot, holoviews]
excerpt: "Embedding interactive charts on static pages using Jekyll."
hv-loader:
  hv-chart-1: ["feature_imp.html", "280", "600"] # second argument is the height
toc: true
toc_sticky: true
---

## **- Predict scores from reviewers**

### **Train a Random Forest model**

Is a customer's rating of a hotel predictable? What relationship do the customer's review text and the rating give? I try to build a random forest model to predict the rating score of any given reviewer. Through this model, not only can hotels collect customer reviews in advance to predict the customer's potential scores and make corresponding countermeasures, but also can dig out most significant predictors to better understand and manage their average scores.

The final model is based on the hotels' situation:

-   the current average score

-   the total number of reviews

-   scores from non-reviewers

-   the located country

-   and specific reviewer information:

-   information related to the review text

-   the last review time

-   the total review number

-   nationality of the reviewer

-   the month of comments

### **Explore important predictors**

The score of this model is 0.45, and the mean percentage error is 13%. The hotel can input the user's comment text obtained in advance to predict the score and carry out corresponding countermeasures.

At the same time, we can see that the most important predictors are:

-   the number of words in negative reviews given by reviewers

-   the polarity of positive reviews

-   the current average hotel score

<div id="hv-chart-1"></div>

Therefore, just like the sentiment analysis conclusion, to improve the overall scores, the hotels should try to make up for the shortcomings to reduce the factors that can be criticized, and provide users with higher emotional value.