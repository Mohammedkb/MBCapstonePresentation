<style>

/* slide titles */
.reveal h3 { 
  font-size: 60px;
  color: blue;
  font-weight: bold;
}

/* heading for slides with two hashes ## */
.reveal .slides section .slideContent h2 {
   font-size: 40px;
   font-weight: bold;
   color: green;
}

.sld2 .reveal .state-background {
  background: #E3CEF6;
} 

.sld3 .reveal .state-background {
  background: #A9F5E1;
} 

.sld4 .reveal .state-background {
  background: #F6D8CE;
} 

.sld5 .reveal .state-background {
  background: #81DAF5;
} 

</style>

Predicting the Usefulness of a Yelp Review Using Machine Learning
========================================================
author: Mohammed K. Barakat 
date: 8 Nov 2015
width: 1300

========================================================
type: sld2

## About Yelp.com

Yelp is a place that helps people find great local businesses. It reflects on users' experience with products and services through online reviews.

## The Question

This research tries to answer the question *"Can we predict to what extent a user's review for a business is useful by predicting the number of "useful" votes the review will receive and by predicting a "usefulness" category of the review?"*

## The Benefit

The outcome of this analysis helps exploit potential useful reviews as soon as they are posted to improve businesses and provide quicker recommendations to potential customers.

Research Methodology
========================================================
type: sld3

1. Input Data
    + <small>download and read data into R (part of the Yelp Dataset Challenge data)</small>
2. Data Processing
    + <small>Select outcome variable and predictors</small>
    + <small>Process and screen variables. Merge datasets</small>
3. Exploratory Data Analysis
    + <small>Explore outcome variable and features relationships</small>
4. Prediction Algorithms
    + <small>Fit, train and test **Model-A** to predict number of *useful* votes (**GLM** algorithm).</small>
    + <small>Fit, train and test **Model-B** to predict *Usefulness Category* (**Random Forest** algorithm).</small>
5. Concluding the results

Prediction Output
========================================================
type: sld4

<small>
**Model-A**: Predicts number of *useful votes* with **1.68** votes out-of-sample error. Random sample of testing results is shown below.
</small>
<font size="6">
<small>

|review_id              | Actual.Votes | Predicted.Votes |
|:----------------------|:------------:|:---------------:|
|-NAFwv6T1d7kWkC9vPJsvA |      3       |        4        |
|d2iHH5X6u_NNQh5e74dWYw |      0       |        1        |
|_Fy_4jkJlnxo678Qh9JtpQ |      1       |        2        |
|UNW6sZMc3IJlULuG6J8X2A |      0       |        1        |
|WVaheCoNqwJgBA2l5u4kZA |      1       |        0        |
|5Ji2qhXxRKI26K_vK_2Bvg |      2       |        2        |
|5GDxwCUdR3AUTcMDxXS8FA |      0       |        0        |
</small>
</font>

***
<small>
**Model-B**: Predicts *usefulness* category with **79%** accuracy (21% out-of-sample error). Random sample of testing results is shown below.
</small>
<font size="6">
<small>

|review_id              | Actual.Category | Predicted.Category |
|:----------------------|:---------------:|:------------------:|
|-NAFwv6T1d7kWkC9vPJsvA | Slightly Useful |  Slightly Useful   |
|d2iHH5X6u_NNQh5e74dWYw |   Not Useful    |     Not Useful     |
|_Fy_4jkJlnxo678Qh9JtpQ |   Not Useful    |     Not Useful     |
|UNW6sZMc3IJlULuG6J8X2A |   Not Useful    |     Not Useful     |
|WVaheCoNqwJgBA2l5u4kZA |   Not Useful    |     Not Useful     |
|5Ji2qhXxRKI26K_vK_2Bvg | Slightly Useful |     Not Useful     |
|5GDxwCUdR3AUTcMDxXS8FA |   Not Useful    |     Not Useful     |
</small>
</font>

Discussion (Answer to the Question)
========================================================
type: sld5

- Applying both prediction models (**Mode-A** and **Model-B**) to the Yelp data enables us to predict, with an **acceptable accuracy level**, the extent of usefulness of a user's review for a business by predicting the number of *useful* votes and the *usefulness* category.

- In **Model-A** the prediction error (**1.68** "useful" votes) is very reasonable in predicting the number of useful votes. Similarly, in **Model-B** the prediction accuracy (**79%**) looks also reasonable in classifying the usefulness of a user's review.

- Both models can have positive implications on yelp.com, yelpers, and businesses. Their prediction capacity helps exploit potential useful reviews as soon as they are posted in an effort to be proactive in improving businesses and in providing quicker recommendations for potential customers.
