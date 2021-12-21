---
title: "Classify hotels based on their ratings and reviews"
date: 2021-12-19
published: true
categories:
  - blog
tags:
  - Github Page
tags: [dataviz, altair, hvplot, holoviews]
excerpt: "Embedding interactive charts on static pages using Jekyll."
altair-loader:
  altair-chart-1: "charts/hotelAltair.json"
  altair-chart-2: "charts/hotelAltair2.json"
toc: true
toc_sticky: true
---

## - Clustering based on DBSCAN

### Mean statistics for clusters


<div>
```{=html}
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
```
+---+-------+---------------+-------------------------+--------------------+
|   | label | Average_Score | Total_Number_of_Reviews | total_subjectivity |
+===+=======+===============+=========================+====================+
| 0 | -1    | 8.057679      | 2576.573379             | 0.478019           |
+---+-------+---------------+-------------------------+--------------------+
| 1 | 0     | 8.565745      | 904.440219              | 0.486050           |
+---+-------+---------------+-------------------------+--------------------+
| 2 | 1     | 8.462500      | 3836.531250             | 0.589238           |
+---+-------+---------------+-------------------------+--------------------+
| 3 | 2     | 8.130000      | 3454.600000             | 0.571613           |
+---+-------+---------------+-------------------------+--------------------+
</div>

### Relationships between scores, subjectivity, and number of reviews

<div id="altair-chart-1"></div>

(Below is the process code to embed interactive plots:)

``` {.python}
import altair as alt
alt.renderers.enable('notebook')
```

### Relationships between scores, subjectivity, and number of reviews

<div id="altair-chart-2"></div>

(Below is the process code to embed interactive plots:)

``` {.python}
import altair as alt
alt.renderers.enable('notebook')
```

### **Radar map for hotel clusters**

![](https://github.com/keeea/Hotel_Review_Analysis/blob/main/assets/images/hotel.png?raw=true)
