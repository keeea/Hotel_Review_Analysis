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

+-------------------+-------------------+-----------------------------+----------------------------------------+
| **Cluster label** | **Average Score** | **Total Number of Reviews** | **Subjectivity of Integrated Reviews** |
+:=================:+:=================:+:===========================:+:======================================:+
| -1                | 8.376015          | 1719.720787                 | 0.502717                               |
+-------------------+-------------------+-----------------------------+----------------------------------------+
| 0                 | 8.663081          | 663.550122                  | 0.397988                               |
+-------------------+-------------------+-----------------------------+----------------------------------------+
| 1                 | 8.304951          | 1122.517570                 | 0.586961                               |
+-------------------+-------------------+-----------------------------+----------------------------------------+
| 2                 | 8.785000          | 965.425000                  | 0.600886                               |
+-------------------+-------------------+-----------------------------+----------------------------------------+

### Relationships between scores, subjectivity, and number of reviews

::: {#altair-chart-1}
:::

(Below is the process code to embed interactive plots:)

``` {.python}
import altair as alt
alt.renderers.enable('notebook')
```

### Relationships between scores, subjectivity, and number of reviews

::: {#altair-chart-2}
:::

(Below is the process code to embed interactive plots:)

``` {.python}
import altair as alt
alt.renderers.enable('notebook')
```

### **Radar map for hotel clusters**

![](https://github.com/keeea/Hotel_Review_Analysis/blob/main/assets/images/hotel.png?raw=true)
