---
title: "Kaggle H&M Recommender System"
description: "Initial Rec Sys Project"
layout: default
---

# H&M Rec Sys
Kaggle hosted a data science competition back in 2022, where H&M provided almost 35gb of purchase history and metadata. Here is the official website with more details. 
This was my first project building a Rec Sys, and was aimed at learning as much as possible in the Search and Rec space. Below highlights major aspects of the project.

# Data Analysis
This was by far the most important step in my journey to learning about Search & Rec Sys. I spent a lot of time just getting familiar with all of the data, and exploring what all I could do with it. To get a feel for what the transaction history table looks like, I’ve printed a few transactions that occurred on 09/20/18:

Add table here

Each transaction includes a transaction date, customer ID, article ID, and varying levels of item descriptions. Across September 2018 to September 2020, there are 31,788,324 transactions, encompassing 105,542 distinct articles purchased by 1,371,980 customers. Many of these customers bought exactly one article: 154,947 purchased just a single article, and 23,433 of those made multiple purchases of that same article on different dates.

This distinction is important because we need to differentiate between customers who purchase only one article on a single occasion and those who purchase the same single article multiple times. In the latter scenario, that article might be correlated with additional future purchases. Reflecting on this led me to clarify the main goal:

***Goal: at any point in time, and considering a Customer’s past purchases, identify the most relevant Articles to recommend***

However, single-purchase Customers introduce a cold-start challenge, since there is no prior data to inform recommendations. One straightforward solution is to offer Articles based on current trends—for example, presenting a list of the top 10 Articles purchased in the past week. At the same time, if a Customer rebuys the same Article across multiple shopping experiences without co-purchasing any other Articles, those repeat purchases should be captured in the training data so the model can factor in their likelihood of future sales.
