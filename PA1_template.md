---
title: "Reproducible Research: Peer Assessment 1"
output: 
  html_document:
    keep_md: true
---


## Loading and preprocessing the data

The activity data represents personal activity measured by a monitoring device. The measurements are taken every 5 minutes during two months, counting the steps of a subject. The variables in the dataset are:

* steps: Number of steps by each 5 minutues.
* date: Measurement date in YYYY-MM-DD format.
* interval: Identifier for the measurement time each day.

First we have to load the activity data in .csv





```r
act <- read.csv("activity.csv")
da <- as.Date(act$date,"%Y-%m-%d")
```



## What is mean total number of steps taken per day?

Grouping the data by day and plotting a histogram we have:


```r
ts <- act %>% group_by(date) %>% summarize(sum(steps,na.rm=TRUE))
names(ts)[2] <- "total"
hist(ts$total,main="Total steps per day",xlab="Steps",col=co[1],breaks=20,xlim=c(0,25000))
```

![](PA1_template_files/figure-html/total-1.png)<!-- -->
The mean and median of total steps per day are:


```
##     Mean   Median 
##  9354.23 10395.00
```



## What is the average daily activity pattern?



## Imputing missing values



## Are there differences in activity patterns between weekdays and weekends?
