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

One task I find myself doing a lot is simply bulk extraction of data from csv files.
CSVs take space and they are slow to open. So I like to bulk convert inputs into rds files to make my life easier. So here we go:

{% highlight css %}

# import libs
require(readr)
require(tools)

# set paths
readpath = 'blah' # 'C:/Users/me/docs'
writepath = 'blah2' # 'C:/Users/me/outputs'
files = list.files(readpath)
Iterator_frame = as.data.frame(files)
Iterator_frame$FileType <- tools::file_ext(Iterator_frame$files)
Iterator_frame$Filename <- tools::file_path_sans_ext(Iterator_frame$files)

# make sure that our path object has full paths
Iterator_frame$FullPath <- paste0(readpath, files)
Iterator_frame$write_path <- paste0(writepath, Iterator_frame$Filename, '.rds')

for (i in 1:nrow(Iterator_frame)) {
  Dataset = read_csv(Iterator_frame[i,4])
  saveRDS(Dataset, Iterator_frame[i,5])
}

{% endhighlight %}

