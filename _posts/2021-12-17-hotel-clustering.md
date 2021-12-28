---
title: "Clustering in hotels and customers"
date: 2021-12-17
published: true
tags: [dataviz, altair, hvplot, holoviews]
hv-loader:
  hv-chart-1: ["charts/cust_cluster.html", "500"] # second argument is the height
toc: true
toc_sticky: true
---

## - Classify hotels based on DBSCAN

Hotels can be classified and located based on their ratings and reviews, which can help hotels figure out which **group** they belong to who are exactly their **rivals**. Here Density-based spatial clustering of applications with noise (**DBSCAN**) is applied, given that characteristics of luxury hotels are more personalized and differentiated with more **outliers** that are difficult to classify.

### Radar map for hotel clusters

Draw a radar map based on the center values of the three groups to visualize their characteristics. (Red represents outliers, not a real group) 
![](https://github.com/keeea/Hotel_Review_Analysis/blob/main/assets/images/table_hot.png?raw=true "Normalized values")

![](https://github.com/keeea/Hotel_Review_Analysis/blob/main/assets/images/hotel.png?raw=true)

Hotels are divided into **three categories** by the algorithm, excluding outliers. According to the radar map, **category-blue** hotels have fewer reviews, and the subjectivity of the comments is lower, while the average score is comparatively higher. The number of comments for the **category-purpple** group is also minimal, but the subjectivity is high and the average score is low. Finally, the **category-grey** group has higher evaluations, subjectivity, and average scores.

These three types of luxury hotels respectively represent: blue - **niche and high-quality simple hotels**, purpple - **niche and general-quality specialty hotels**, and grey - **famous high-end hotels**.

### **Interactive dashboard -** Relationships within clusters by country

Users can explore the specific situation of clusterings by country through the **interactive dashboard** below. Take **Italy** as an example. Compared with other countries, it has much more purple - niche and general-quality specialty hotels, and their scores are not high. Italian purple - niche and high-quality concise hotels are also unexpectedly not highly rated. Combined with the bar chart, the reason may be that customers' evaluations of such hotels in Italy are relatively low subjective. Given the analysis of other parts, in such a strong-style country, providing customers with higher emotional value makes hotel comments more subjective, which often leads to higher ratings.

(Click "launch binder app" to explore interactive dashboard. There may be a delay of about 30s during the option switching process.) [![](https://img.shields.io/badge/launch-binder%20app-E66581.svg?logo=data:image/png;base64,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)](https://mybinder.org/v2/gh/keeea/word_cloud/HEAD?urlpath=%2Fpanel%2Fapp)

(It takes some time to load the app, here is a screenshoot of the interface:)
![](https://github.com/keeea/Hotel_Review_Analysis/blob/main/assets/images/app.png?raw=true)

Here are some other analogous non-interactive relationship charts, which contribute to assist radar map to identify population characteristics. ![](https://github.com/keeea/Hotel_Review_Analysis/blob/main/assets/images/hot_clu_label.png?raw=true)

![](https://github.com/keeea/Hotel_Review_Analysis/blob/main/assets/images/hot_clu_country.png?raw=true)

### Advice:

Hotels can input their information into the model to **locate their sub-markets** to instruct more appropriate **market strategies**. Furthermore, hotel managers can use the interactive dashboard to explore their **current situation** in the segmented competitive market by filtering their own groups and countries (there are 24 market segments through different combinations). For example, they can compare themselves with parallel hotels to see whether their number of reviews is relatively low. And if it is the case, is there any way to stimulate guests' willingness to comment more and better.

## - Identify customers based on K-means

Classify guests with K-means based on their **consuming behaviors**, such as **frequency and monetary**, to conclude different **user portraits**. Different from the previous analysis, this **use case** is more helpful for **Booking.com** itself. Booking.com can implement various motivators for different customers to maintain their **product energy** and the number of reviews in the future.

### Mean statistics and radar map for reviewer clusters

According to the statistical table and the radar map, commenters are divided into **five categories** (according to the colors on the radar map): **red** - new users who are recently active, **blue** - old users who have not been active recently, **yellow** - previously-active users who are close to churn, **purple** - active and talkative old users, and **gray** - users who have always very seldom given reviews. 
![](https://github.com/keeea/Hotel_Review_Analysis/blob/main/assets/images/table_cus.png?raw=true) 

![](https://github.com/keeea/Hotel_Review_Analysis/blob/main/assets/images/customer.png?raw=true)

### Relationships among customer frequency, monetary and sentiment

This **interactive** relationship diagram allows you to view **specific individual information** with the mouse. As we can see from the bubble chart, people with shorter reviews tend to give more hotel reviews. On the other hand, the comment frequency (the interval between the most recent comments) does not seem to correlate with the first two indicators. On top of these, different groups have different distribution characteristics in this chart.

<div id="hv-chart-1"></div>


### Advice:

The most significant target for Booking is **blue-old users who have not been active recentl**y. Because they have a high retention value, and the **retention cost** will be much lower than that of yellow users who have not written reviews for a long time. Incentive method like **discounts and credits** is suitable for such blue users.

In addition, r**ed - new users who are actively commenting lately**, are the ones that Booking also needs to focus on. For these red guests, the **low-cost incentive methods**, such as **punch and lottery after comment**, are more effective in promoting their habit formation.
