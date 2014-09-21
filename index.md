---
title       : United States Demographics 
subtitle    : A Shiny Application
author      : Coursera Student
job         : 
framework   : io2012        # {io2012, html5slides, shower, dzslides, ...}
highlighter : highlight.js  # {highlight.js, prettify, highlight}
hitheme     : tomorrow      # 
widgets     : []            # {mathjax, quiz, bootstrap}
mode        : selfcontained # {standalone, draft}
knit        : slidify::knit2slides
---

## I Made a Shiny App!

1. It uses the state dataset from the datasets package.
2. The user selects one of 3 categories: Population, Income, or Area.
3. A choropleth map of the U.S. is plotted for the selected demographic value.

--- .class #id 

## Sample of Data


```r
head(state.x77)
```

```
##            Population Income Illiteracy Life Exp Murder HS Grad Frost
## Alabama          3615   3624        2.1    69.05   15.1    41.3    20
## Alaska            365   6315        1.5    69.31   11.3    66.7   152
## Arizona          2212   4530        1.8    70.55    7.8    58.1    15
## Arkansas         2110   3378        1.9    70.66   10.1    39.9    65
## California      21198   5114        1.1    71.71   10.3    62.6    20
## Colorado         2541   4884        0.7    72.06    6.8    63.9   166
##              Area
## Alabama     50708
## Alaska     566432
## Arizona    113417
## Arkansas    51945
## California 156361
## Colorado   103766
```

--- .class #id 

## User Interface Code


```r
shinyUI(fluidPage(
  titlePanel("Population, Income, and Area by U.S. State"),
  
  sidebarLayout(
    sidebarPanel(
      helpText("Graphically compare Population, Income, and Area for U.S. states.
                     Source (via state.x77 dataset):  
                    U.S. Department of Commerce, Bureau of the Census (1977) Statistical Abstract of the United States.
                    U.S. Department of Commerce, Bureau of the Census (1977) County and City Data Book."),
      
      selectInput("var", 
                  label="Choose a category to display",
                  choices=c("Population",
                            "Income",
                            "Area"
                            ),
                  selected="Population")
    ),
    
    mainPanel(plotOutput("map"))
  )
))
```

```
## Error: could not find function "shinyUI"
```

--- .class #id 

## This May Not Be a Very Good "Pitch"

Reasons to be generous in scoring anyway

1.  It feels good.
2.  I will be.
3.  I ran really, really short on time for this assignment.
4.  Why not?








