---
title       : Global Temperature Trends
subtitle    : Coursera Data Products Class Project
author      : Coursera10062014
job         : 
framework   : io2012        # {io2012, html5slides, shower, dzslides, ...}
highlighter : highlight.js  # {highlight.js, prettify, highlight}
hitheme     : tomorrow      # 
widgets     : [mathjax]            # {mathjax, quiz, bootstrap}
mode        : selfcontained # {standalone, draft}
knit        : slidify::knit2slides
---

# Global Temperatures are Rising

While temperatures are rising, all the so-called debate in the press
might leave you asking questions, like...

   1. How fast are temperatures rising?
   2. Are they rising faster now than in the past?
   3. How do we know?
   
# NASA has answers

NASA publishes data tables with historical temperature records.

I chose to use [this table](http://data.giss.nasa.gov/gistemp/tabledata_v3/NH.Ts+dSST.txt)
as my topic for analysis.

That table starts by measuring land and sea temperatures in various
time aggreagations (monthly, quarterly, and annually), starting from
1880 until today.

--- .class #id 

# What's in the data?

The data table represents deviations from the baseline period, in units
of one hundredth of a degree Celcius.

I worked with the January to December annual averages.

--- .class #id

# Temperatures fell during the mid 20th century



```r
d <- filterYears(data, c(1940, 1960))
lm(d$AnnualMeanJanToDec ~ d$Year)$coefficients[2]
```

```
##     d$Year 
## -0.5935065
```

This suggests that based on the mid-century trend, temperatures would fall 0.59&deg;C over a century.  But...

# Temperatures rose sharply in the last 30 years


```r
d <- filterYears(data, c(1984, 2014))
lm(d$AnnualMeanJanToDec ~ d$Year)$coefficients[2]
```

```
## d$Year 
## 2.5625
```

This suggests that temperatures would rise 2.6&deg;C over a century.

--- .class #id 

# Explore the data

[Take me to the app](https://coursera10062014b.shinyapps.io/DataProductsClassProjectShiny/)

See what conclusions you can draw.
