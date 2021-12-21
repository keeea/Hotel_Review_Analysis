---
title: "Reviewers sentiment"
date: 2021-12-19
published: true
categories:
  - blog
tags:
  - Github Page
tags: [dataviz, altair, hvplot, holoviews]
excerpt: "Embedding interactive charts on static pages using Jekyll."
hv-loader:
  hv-chart-1: ["charts/polarity_dist.html", "200"] # second argument is the height
  hv-chart-2: ["charts/subjectivity_dist.html", "200"] # second argument is the height
toc: true
toc_sticky: true
---

## - Sentiment analysis

Are customers' reviews of each hotel positive or negative, subjective or objective? Let's analyze negative, positive, and integrated reviews.

First, count how many reviews are overall unbiased (Polarity = 0) in integrated reviews. The result is around 17%. But zero-value polarities with this algorithm may not represent unbiased for hotel reviews, further distributions of polarities are required.

> Number of unbiased reviews: 45595
>
> Proportion of unbiased reviews: 17.24 %

### The distribution of polarity

Polarity runs from -1 (most negative) to +1 (most positive). Plot the histograms of the polarities of positive, negative and integrated reviews together with different colors. We can see that the polarity of negative reviews is concentrated in 0-0.2, while the polarity of positive reviews is concentrated in the range of 0.3-0.7, which proves that the algorithm's evaluation value of review sentiment is larger than the normal one. Therefore, the polarity of the true neutral evaluation should be slightly greater than 0.

> The average polarity of integrated reviews: 0.2052
>
> The median polarity of integrated reviews: 0.15
>
> The average polarity of positive reviews: 0.3801
>
> The median polarity of positive reviews: 0.4
>
> The average polarity of negative reviews: 0.0355
>
> The median polarity of negative reviews: 0.0

Then we look at the polarity distribution of the integrated reviews. Most polarities are near 0, which represents slightly negative feelings, and some are in the range of -0.2 to -0.1, which means strongly negative emotions. Also, some polarities are more evenly distributed in the field of 0.3-0.7, while a small number of polarities are more significant than 0.7.

::: {#hv-chart-1}
:::

In summary, positive reviews are a bit more than negative reviews overall, but some negative reviews are very extreme. This result enlightens hotel managers that the most important thing to pay attention to is to reduce the appearance of these extremely negative comments, that is, to prioritize improving the shortest board rather than further optimizing the existing advantages.


``` {.python}
import altair as alt
alt.renderers.enable('notebook')
```

### The distribution of subjectivity

The subjectivity of negative reviews is more concentrated at 0.4 and below, while positive reviews are more distributed above 0.5. It indicates that negative consumer reviews are often more objective than positive ones. Therefore, if hotels want to increase the number of positive reviews, it's best to provide customers with higher emotional value, such as low-cost surprise gifts or services, and a significantly warm attitude.

::: {#hv-chart-2}
:::

### Explore the monthly trend of subjectivity

At last, explore the monthly trend of polarity and subjectivity. Interestingly, the reviewers' comments text will be more positive and subjective in the summer. This phenomenon may be because the weather and temperature will affect the users' mood or experience. In any case, it means that European hotels need to pay more attention to maintaining user experience, complaints, and evaluations in winter.![](https://github.com/keeea/Hotel_Review_Analysis/blob/main/assets/images/polarity_trend.png?raw=true "fig.1 - Polarity trend")![](https://github.com/keeea/Hotel_Review_Analysis/blob/main/assets/images/sub_trend.png?raw=true "Subjectivity trend")
