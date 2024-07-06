
# NYC Taxi Trip Data Analysis

## Overview

This project was completed as part of the "Getting Started with Python" course on Coursera. The aim was to analyze NYC taxi trip data from 2017 to derive insights and understand patterns in the data.

## Dataset

The dataset used in this project is `2017_Yellow_Taxi_Trip_Data.csv`, which contains details about taxi trips in New York City for the year 2017.

## Key Highlights

- Loaded and inspected the dataset to understand its structure.
- Conducted descriptive statistics to summarize the data.
- Investigated variables such as `trip_distance` and `total_amount`.
- Analyzed payment types and their respective tip amounts.

## Key Findings

- The average tip for trips paid with credit cards was significantly higher than those paid with cash.
- There were some outliers in the data, such as unusually high total amounts for short distances.

## Installation

To run the analysis, you need to have Python installed along with the following libraries:

- pandas
- numpy

import pandas as pd

# Load the dataset
df = pd.read_csv('Datasets/2017_Yellow_Taxi_Trip_Data.csv')

# Inspect the data
print(df.head())
print(df.info())
print(df.describe())

# Investigate trip_distance
sorted_trip_distance = df[['trip_distance', 'total_amount']].sort_values(by='trip_distance', ascending=False)
print(sorted_trip_distance.head())

# Investigate total_amount
sorted_total_amount = df[['trip_distance', 'total_amount']].sort_values(by='total_amount', ascending=False)
print(sorted_total_amount.head())

# Payment type analysis
payment_counts = df['payment_type'].value_counts()
print(payment_counts)

# Average tip amounts
avg_cc_tip = df[df['payment_type'] == 1]['tip_amount'].mean()
avg_cash_tip = df[df['payment_type'] == 2]['tip_amount'].mean()
print('Avg. cc tip:', avg_cc_tip)
print('Avg. cash tip:', avg_cash_tip)

