---
layout: post
title: "Super Charging Data Analysis - Bulk reformatting"
date: 2016-10-07
excerpt: "Hints on getting things done in R"
tags: [bulk processing, data munging, R, data science]
comments: true
---

## Super Charging Data Analysis

As much as people working in Data Science like to discuss the relative merits of and the different applications for various models, the bulk of data science work is just data processing.
Or as I like to think of it, how to transform the garbage you are given as an analyst into actual usable data for that fancy model. 

One task I find myself doing a lot is simply bulk extraction of data from excel files.
Excel files are the most common encountered in any organisation. 
So I like to bulk convert inputs into rds files to make my life easier. So here we go:

{% gist d4faa7d465c7a5bcb94ab988f4a7bcae %}

