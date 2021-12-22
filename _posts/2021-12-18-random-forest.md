---
title: "Secrets of higher rating"
date: 2021-12-18
published: true
categories:
  - blog
tags:
  - Github Page
tags: [dataviz, altair, hvplot, holoviews]
hv-loader:
  hv-chart-1: ["charts/feature_imp.html", "300"] # second argument is the height
toc: true
toc_sticky: true
---

## - Predict scores from reviewers
Is a customer's rating of a hotel predictable? What relationship do the customer's review text and the rating give? I try to build **a random forest mode**l to predict the rating score of any given reviewer. Through this model, not only can hotels collect customer reviews in advance to predict the customer's **potential scores** and make **corresponding countermeasures**, but also can dig out most **significant predictors** to better understand and manage their average scores.

### Train a Random Forest model
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

Here is a correlation matrix of four major predictors to see whther they are multilinear.
![](https://github.com/keeea/Hotel_Review_Analysis/blob/main/assets/images/matrix.png?raw=true)

This is the simplified version of the prediction model, excluding feature engineering, parameters optimization and some model evaluations. 
```{python}
# Set up the column transformer with two transformers
transformer = ColumnTransformer(
    transformers=[("num", StandardScaler(), num_cols),
        ("cat", OneHotEncoder(handle_unknown="ignore"), cat_cols)])

# Initialize the pipeline after optimazing parameters
pipe2 = make_pipeline(transformer, RandomForestRegressor(n_estimators=600, 
                                       max_depth=13,
                                       random_state=42))

# Fit the training set
pipe2.fit(train_set, y_train);
```

### Explore important predictors

The score of this model is 0.45, and the mean percentage error is **13%.** The hotel can input the user's comment text obtained in advance to predict the score and carry out corresponding countermeasures.

Explore this **interactive** bar chart, we can see that the most important predictors are:

-   **the number of words in negative reviews** given by reviewers

-   **the polarity of positive reviews**

-   the current **average hotel score**

<div id="hv-chart-1"></div>

### Advice:

Therefore, just like the **sentiment analysis conclusion**, to improve the overall scores, the hotels should try to **make up for the shortcomings** first to reduce the factors that can be criticized, and then provide users with **higher emotional value**.
