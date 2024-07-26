---
title: "Reproducible Research: Peer Assessment 1"
output: 
  html_document:
    keep_md: true
---


## Loading and preprocessing the data


``` r
unzip("activity.zip")
activity <- read.csv("activity.csv")
```


## What is mean total number of steps taken per day?





``` r
library(dplyr)

grouped_activity <- group_by(activity, date) 
daily_activity <- summarize(grouped_activity, 
          mean = mean(steps, na.rm = TRUE), 
          total = sum(steps, na.rm = T) 
          )
```


``` r
steps_mean <- mean(daily_activity$mean, na.rm = T)
steps_median <- median(daily_activity$mean, na.rm = T)

#steps_mean <- round(steps_mean, digits = 3) 
#steps_median <- round(steps_median, digits = 3) 
```
The mean number of steps taken is  37.3825996

The median number of steps taken is 37.3784722

![](PA1_template_files/figure-html/unnamed-chunk-5-1.png)<!-- -->


## What is the average daily activity pattern?



## Imputing missing values



## Are there differences in activity patterns between weekdays and weekends?
