# New York City - Taxi Spending Analysis

## Problem Definition

In this project I tried to predict the average money spent on taxi rides in NYC per given day and hour.

Given that I tried to predict a continuos variable and I had its value in my dataset, this can be identified as a _supervised regression_ problem.

## Methodology

1. I cleaned the data by removing transactions with a negative _total_amount_ (can a taxi ride cost an amount of $ below zero in the real world? I don't think so!) and those transactions with a _total_amount_ which was too high (average is 16$, and only 1K data points out of 7M contained an amount above 200$).

2. As second step I identified the features needed to create the first _benchmark model_ leveraging the data dictionary available [here](https://www1.nyc.gov/assets/tlc/downloads/pdf/data_dictionary_trip_records_yellow.pdf).

3. The benchmark model I used was a Decision Tree, it used only the original features.

4. After the disappointing results of the benchmark model I added a few features using a location-based dataset and weather related data.

5. The algorithms I tried with the new data were: Decision Trees, Random Forest and Gradient Boosting. The Random Forest resulted to be the best performing.

6. As a final step I tuned the model applying the _RandomSearchCV_.

## Final Thoughts

The performance of the model (~43%) can be improved by limiting the regions included in the analysis (taking into account only those with a lot of datapoints) or increasing data collection related to those boroughs with less datapoints.
