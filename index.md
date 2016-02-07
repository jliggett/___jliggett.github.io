---
title       : Top Releases By Country per Genre, According to Discogs 
subtitle    : Pitch for Cousera Data Products Course
author      : jlliggett
job         : Cousrera Student
framework   : io2012        # {io2012, html5slides, shower, dzslides, ...}
highlighter : highlight.js  # {highlight.js, prettify, highlight}
hitheme     : tomorrow      # 
widgets     : []            # {mathjax, quiz, bootstrap}
mode        : selfcontained # {standalone, draft}
---

## What does this app accomplish?

### This app will help answer the following questions... 
1. Link to app: https://jlliggett.shinyapps.io/newapp/
2. How easy is it to get Master release data from Discogs?
3. Can we identify which countries contribute most to the top 5 genres releasing albums?
4. Can we scale this app to grab additional years of data?

--- .class #id 

## How do we get the Discogs Data?

1. Data is captured using the Discogs API
    a. https://api.discogs.com
2. Data is returned in JSON format

--- .class #id 
## What does the cleaned data look like?
1. The JSON data is then cleaned and transformed into a CSV file
2. CSV file is made available via an Amazon S3 link to the app


```r
mydata.map <- read.csv("http://s3.amazonaws.com/jliggettrstudio/discogs_master_2015_clean.csv")
head(mydata.map)
```

```
##   X    Group.1     Group.2   x
## 1 1 electronic   Argentina  17
## 2 2       rock   Argentina   8
## 3 3       rock Australasia   1
## 4 4 electronic   Australia 141
## 5 5    hip hop   Australia  16
## 6 6      other   Australia   4
```

--- .class #id 
## How to Use the App
### Selecting a country on the left sidepanel will display its discogs info
![Width](assets/img/shiny_app.png)

--- .class #id 
## Additional improvements for the app
1. Grab more data from the Discogs API
2. Attempt to predict likelihood of genre numbers for each country
3. Add review information for each release for additional analysis


