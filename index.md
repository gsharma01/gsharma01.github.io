---
title       : Shiny App Presentation
subtitle    : 
author      : Gaurav Sharma
job         : 
framework   : io2012        # {io2012, html5slides, shower, dzslides, ...}
highlighter : highlight.js  # {highlight.js, prettify, highlight}
hitheme     : tomorrow      # 
widgets     : []            # {mathjax, quiz, bootstrap}
mode        : selfcontained # {standalone, draft}
knit        : slidify::knit2slides
---

## Linear Regression Model on mtcars 

1. Presenting simple linear regression between MPG as outcome and others as predictors
2. Basic Model: y= b0 + b1x1 + b2x2 +....+bpxp + ei; i= 1 ...n




## Regarding Ui.r

1. Ui.R is having code to show the select box for independent variable
2. User can select any option from select box to create model 
3. select element is reactive and will pass the input to server as per user's actions.
4. Dependent variable is fixed and cannot be changed.

--- .class #id 

## Regarding server.r

1. server.R is having code to create the model from the reactive input
2. Server.R will accept the input as independent variable and will create model 
3. This also uses the helpers.R file, where model creation function is defined.
4. It provides the reactive output variables to UI.R to display various plots.



## helpers.R and model

1. This has function which creates model for server.R
2. It accepts input variable as independent variable.
3. it goes through various statements and select appropriate variable to create model.


--- .class #id

## Outputs

1. Output will show the various model plot
2. Residual vs Fitted
3. Normal Q-Q
4. Scale-Location
5. Cook's Distance
6. Residuals vs Leverage
7. Cook's Distance vs Leverage.
8. Next is an example of a model of mpg as outcome and wt as predictor.

--- .class #id


```r
model<-lm(mpg~wt, data=mtcars)
summary(model)
```

```
## 
## Call:
## lm(formula = mpg ~ wt, data = mtcars)
## 
## Residuals:
##    Min     1Q Median     3Q    Max 
## -4.543 -2.365 -0.125  1.410  6.873 
## 
## Coefficients:
##             Estimate Std. Error t value Pr(>|t|)    
## (Intercept)   37.285      1.878   19.86  < 2e-16 ***
## wt            -5.344      0.559   -9.56  1.3e-10 ***
## ---
## Signif. codes:  0 '***' 0.001 '**' 0.01 '*' 0.05 '.' 0.1 ' ' 1
## 
## Residual standard error: 3.05 on 30 degrees of freedom
## Multiple R-squared:  0.753,	Adjusted R-squared:  0.745 
## F-statistic: 91.4 on 1 and 30 DF,  p-value: 1.29e-10
```




