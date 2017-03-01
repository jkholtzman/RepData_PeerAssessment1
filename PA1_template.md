# Reproducible Research: Peer Assessment 1


## Loading and preprocessing the data

```r
library(lubridate)
library(ggplot2)
library(xtable)
library(dplyr)
```


```r
st <- read.csv('activity.csv')
#st$date <- ymd(st$date)
gb <- group_by(st, date)
by_day <- summarise(gb, sum(steps))
names(by_day) <- c('date', 'total_steps')
```


## What is mean total number of steps taken per day?

The total number of steps taken per day is as follows.

```r
xt <- xtable(by_day)
print(xt, type='html')
```

<!-- html table generated in R 3.3.2 by xtable 1.8-2 package -->
<!-- Tue Feb 28 16:46:27 2017 -->
<table border=1>
<tr> <th>  </th> <th> date </th> <th> total_steps </th>  </tr>
  <tr> <td align="right"> 1 </td> <td> 2012-10-01 </td> <td align="right">  </td> </tr>
  <tr> <td align="right"> 2 </td> <td> 2012-10-02 </td> <td align="right"> 126 </td> </tr>
  <tr> <td align="right"> 3 </td> <td> 2012-10-03 </td> <td align="right"> 11352 </td> </tr>
  <tr> <td align="right"> 4 </td> <td> 2012-10-04 </td> <td align="right"> 12116 </td> </tr>
  <tr> <td align="right"> 5 </td> <td> 2012-10-05 </td> <td align="right"> 13294 </td> </tr>
  <tr> <td align="right"> 6 </td> <td> 2012-10-06 </td> <td align="right"> 15420 </td> </tr>
  <tr> <td align="right"> 7 </td> <td> 2012-10-07 </td> <td align="right"> 11015 </td> </tr>
  <tr> <td align="right"> 8 </td> <td> 2012-10-08 </td> <td align="right">  </td> </tr>
  <tr> <td align="right"> 9 </td> <td> 2012-10-09 </td> <td align="right"> 12811 </td> </tr>
  <tr> <td align="right"> 10 </td> <td> 2012-10-10 </td> <td align="right"> 9900 </td> </tr>
  <tr> <td align="right"> 11 </td> <td> 2012-10-11 </td> <td align="right"> 10304 </td> </tr>
  <tr> <td align="right"> 12 </td> <td> 2012-10-12 </td> <td align="right"> 17382 </td> </tr>
  <tr> <td align="right"> 13 </td> <td> 2012-10-13 </td> <td align="right"> 12426 </td> </tr>
  <tr> <td align="right"> 14 </td> <td> 2012-10-14 </td> <td align="right"> 15098 </td> </tr>
  <tr> <td align="right"> 15 </td> <td> 2012-10-15 </td> <td align="right"> 10139 </td> </tr>
  <tr> <td align="right"> 16 </td> <td> 2012-10-16 </td> <td align="right"> 15084 </td> </tr>
  <tr> <td align="right"> 17 </td> <td> 2012-10-17 </td> <td align="right"> 13452 </td> </tr>
  <tr> <td align="right"> 18 </td> <td> 2012-10-18 </td> <td align="right"> 10056 </td> </tr>
  <tr> <td align="right"> 19 </td> <td> 2012-10-19 </td> <td align="right"> 11829 </td> </tr>
  <tr> <td align="right"> 20 </td> <td> 2012-10-20 </td> <td align="right"> 10395 </td> </tr>
  <tr> <td align="right"> 21 </td> <td> 2012-10-21 </td> <td align="right"> 8821 </td> </tr>
  <tr> <td align="right"> 22 </td> <td> 2012-10-22 </td> <td align="right"> 13460 </td> </tr>
  <tr> <td align="right"> 23 </td> <td> 2012-10-23 </td> <td align="right"> 8918 </td> </tr>
  <tr> <td align="right"> 24 </td> <td> 2012-10-24 </td> <td align="right"> 8355 </td> </tr>
  <tr> <td align="right"> 25 </td> <td> 2012-10-25 </td> <td align="right"> 2492 </td> </tr>
  <tr> <td align="right"> 26 </td> <td> 2012-10-26 </td> <td align="right"> 6778 </td> </tr>
  <tr> <td align="right"> 27 </td> <td> 2012-10-27 </td> <td align="right"> 10119 </td> </tr>
  <tr> <td align="right"> 28 </td> <td> 2012-10-28 </td> <td align="right"> 11458 </td> </tr>
  <tr> <td align="right"> 29 </td> <td> 2012-10-29 </td> <td align="right"> 5018 </td> </tr>
  <tr> <td align="right"> 30 </td> <td> 2012-10-30 </td> <td align="right"> 9819 </td> </tr>
  <tr> <td align="right"> 31 </td> <td> 2012-10-31 </td> <td align="right"> 15414 </td> </tr>
  <tr> <td align="right"> 32 </td> <td> 2012-11-01 </td> <td align="right">  </td> </tr>
  <tr> <td align="right"> 33 </td> <td> 2012-11-02 </td> <td align="right"> 10600 </td> </tr>
  <tr> <td align="right"> 34 </td> <td> 2012-11-03 </td> <td align="right"> 10571 </td> </tr>
  <tr> <td align="right"> 35 </td> <td> 2012-11-04 </td> <td align="right">  </td> </tr>
  <tr> <td align="right"> 36 </td> <td> 2012-11-05 </td> <td align="right"> 10439 </td> </tr>
  <tr> <td align="right"> 37 </td> <td> 2012-11-06 </td> <td align="right"> 8334 </td> </tr>
  <tr> <td align="right"> 38 </td> <td> 2012-11-07 </td> <td align="right"> 12883 </td> </tr>
  <tr> <td align="right"> 39 </td> <td> 2012-11-08 </td> <td align="right"> 3219 </td> </tr>
  <tr> <td align="right"> 40 </td> <td> 2012-11-09 </td> <td align="right">  </td> </tr>
  <tr> <td align="right"> 41 </td> <td> 2012-11-10 </td> <td align="right">  </td> </tr>
  <tr> <td align="right"> 42 </td> <td> 2012-11-11 </td> <td align="right"> 12608 </td> </tr>
  <tr> <td align="right"> 43 </td> <td> 2012-11-12 </td> <td align="right"> 10765 </td> </tr>
  <tr> <td align="right"> 44 </td> <td> 2012-11-13 </td> <td align="right"> 7336 </td> </tr>
  <tr> <td align="right"> 45 </td> <td> 2012-11-14 </td> <td align="right">  </td> </tr>
  <tr> <td align="right"> 46 </td> <td> 2012-11-15 </td> <td align="right">  41 </td> </tr>
  <tr> <td align="right"> 47 </td> <td> 2012-11-16 </td> <td align="right"> 5441 </td> </tr>
  <tr> <td align="right"> 48 </td> <td> 2012-11-17 </td> <td align="right"> 14339 </td> </tr>
  <tr> <td align="right"> 49 </td> <td> 2012-11-18 </td> <td align="right"> 15110 </td> </tr>
  <tr> <td align="right"> 50 </td> <td> 2012-11-19 </td> <td align="right"> 8841 </td> </tr>
  <tr> <td align="right"> 51 </td> <td> 2012-11-20 </td> <td align="right"> 4472 </td> </tr>
  <tr> <td align="right"> 52 </td> <td> 2012-11-21 </td> <td align="right"> 12787 </td> </tr>
  <tr> <td align="right"> 53 </td> <td> 2012-11-22 </td> <td align="right"> 20427 </td> </tr>
  <tr> <td align="right"> 54 </td> <td> 2012-11-23 </td> <td align="right"> 21194 </td> </tr>
  <tr> <td align="right"> 55 </td> <td> 2012-11-24 </td> <td align="right"> 14478 </td> </tr>
  <tr> <td align="right"> 56 </td> <td> 2012-11-25 </td> <td align="right"> 11834 </td> </tr>
  <tr> <td align="right"> 57 </td> <td> 2012-11-26 </td> <td align="right"> 11162 </td> </tr>
  <tr> <td align="right"> 58 </td> <td> 2012-11-27 </td> <td align="right"> 13646 </td> </tr>
  <tr> <td align="right"> 59 </td> <td> 2012-11-28 </td> <td align="right"> 10183 </td> </tr>
  <tr> <td align="right"> 60 </td> <td> 2012-11-29 </td> <td align="right"> 7047 </td> </tr>
  <tr> <td align="right"> 61 </td> <td> 2012-11-30 </td> <td align="right">  </td> </tr>
   </table>


```r
qplot(total_steps, data=na.omit(by_day), geom="histogram", ylim=c(0,10), binwidth=500, xlab='Total Steps', main='Histogram of Total Steps per Day')
```

![](PA1_template_files/figure-html/unnamed-chunk-57-1.png)<!-- -->

```r
mean_steps <- as.character(round(mean(by_day$total_steps, na.rm = TRUE)))
median_steps <- as.character(round(median(by_day$total_steps, na.rm = TRUE)))
```

The mean total number of steps taken per day is 10766.

The median total number of steps taken per day is 10765.

## What is the average daily activity pattern?


```r
gbi <- group_by(st, interval)
mean_intervals <- summarise(gbi, round(mean(steps, na.rm=TRUE)))
names(mean_intervals) <- c('interval', 'mean_steps')

ggplot(mean_intervals, aes(x=interval, y=mean_steps)) + 
    #geom_point(pch=19, size=1, alpha=0.25) + 
    geom_line() + 
    xlab('Interval') + 
    ylab('Mean Steps') + 
    labs(title = 'Mean Steps per 5-Minute Interval')
```

![](PA1_template_files/figure-html/unnamed-chunk-59-1.png)<!-- -->


```r
max_interval_steps <- max(mean_intervals$mean_steps)
max_interval <- mean_intervals[mean_intervals$mean_steps==max_interval_steps,]
max_interval <- max_interval[[1]]
```

The maximum number of steps (206) was taken in interval 835.


## Imputing missing values


```r
total_na <- sum(is.na(st))
```

The total number of NAs in the original data set is 2304.

Next, we will create a new data set, substitute the mean values for the NA intervals, and then proceed with further analysis. (I did not like doing this in a for loop, but couldn't figure out how to do it using a vectorized approach.)


```r
st1 <- st
x <- which(is.na(st1))
for(i in x) {
    ivl <- st1[i,]$interval
    mn <- mean_intervals[mean_intervals$interval == ivl,]$mean_steps
    st1[i,]$steps <- mn
}

gb1 <- group_by(st1, date)
by_day1 <- summarise(gb1, sum(steps))
names(by_day1) <- c('date', 'total_steps')

mean_steps1 <- as.character(round(mean(by_day1$total_steps, na.rm = TRUE)))
median_steps1 <- as.character(round(median(by_day1$total_steps, na.rm = TRUE)))

qplot(total_steps, data=na.omit(by_day1), geom="histogram", ylim=c(0,10), binwidth=500, xlab='Total Steps', main='Histogram of Total Steps per Day')
```

```
## Warning: Removed 1 rows containing missing values (geom_bar).
```

![](PA1_template_files/figure-html/unnamed-chunk-62-1.png)<!-- -->

The mean total number of steps taken per day is 10766. The median total number of steps taken per day is 10762. These values and the histogram above show that adding imputed values which are the mean of each interval do not materially affect the overall mean and median of steps per day.



## Are there differences in activity patterns between weekdays and weekends?


```r
st1$date_date <- ymd(st1$date)
st1$date_day <- weekdays(st1$date_date, abbreviate=T)
st1$date_type <- ifelse(st1$date_day %in% c('Sat', 'Sun'), 'Weekend', 'Weekday')

#qplot(interval, steps, data=st1, facets=.~date_type)

p <- ggplot(st1, aes(interval, steps)) + 
    #geom_point(color='red', size=.5, alpha=1/2) + 
    facet_grid(date_type ~ .) + 
    geom_line() + 
    xlab('Interval') + 
    ylab('Mean Steps') + 
    labs(title = 'Mean Steps per 5-Minute Interval')

print(p)
```

![](PA1_template_files/figure-html/unnamed-chunk-63-1.png)<!-- -->
