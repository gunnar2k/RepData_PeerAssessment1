---
title: "Reproducible Research: Peer Assessment 1"
output:
  html_document:
    keep_md: true
---


## Loading and preprocessing the data


```r
if (!file.exists("activity.csv")) {
  unzip("activity.zip")  
}
data = read.csv("activity.csv")
complete = data[complete.cases(data),]
```

## What is mean total number of steps taken per day?


```r
# Calculate the total number of steps taken per day
steps_per_day = aggregate(complete$steps, by=list(Date=complete$date), FUN=sum)
head(steps_per_day)
```

```
##         Date     x
## 1 2012-10-02   126
## 2 2012-10-03 11352
## 3 2012-10-04 12116
## 4 2012-10-05 13294
## 5 2012-10-06 15420
## 6 2012-10-07 11015
```

```r
# Make a histogram of the total number of steps taken each day
hist(steps_per_day$x, xlab="Total steps", main="Histogram: Total number of steps per day")
```

![plot of chunk unnamed-chunk-2](figure/unnamed-chunk-2-1.png) 

```r
# Calculate and report the mean and median of the total number of steps taken per day
print(c(mean(steps_per_day$x), median(steps_per_day$x)))
```

```
## [1] 10766.19 10765.00
```


## What is the average daily activity pattern?



## Inputing missing values



## Are there differences in activity patterns between weekdays and weekends?
