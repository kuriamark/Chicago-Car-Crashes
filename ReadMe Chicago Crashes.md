![Headerimage](./Charts%20%26%20Images/traffic.gif)

# Chicago Car Crash Data
## Predicting Causes of Chicago Car Accidents & Injuries

**Author:** DSPT05 - Group 17


## Overview

In the year 2023, the City of Chicago recorded over one hundred thousand traffic accidents. Over two thousand drivers, passengers, and pedestrians are involved and experience fatal or no injuries

The goal is to build a classifier to predict the cause of total injuries in a car accident, given information about the vehicle age, weather condition, age of the drivers, and traffic control device status

If successful and the City of Chicago implements our recommendations, Chicago will see a decrease in injuries and accidents, a decrease in traffic, and an overall increase in safety for all citizens


## Data 

The source for the datasets came from the Chicago Data Portal. 

***
Datasets Used:

1. Traffic Crashes - Crashes
This dataset contains information about traffic crashes on city streets within the jurisdiction of the Chicago Police Department (CPD). Records are added when crash reports are finalized or amended in the electronic crash reporting system (E-Crash). Data includes parameters such as injuries, street and weather conditions, and posted speed limits. 

   
2. Traffic Crashes - People
This dataset provides details about individuals involved in traffic crashes, including occupants of vehicles, pedestrians, cyclists and others. Injury reports are recorded for each person and the dataset can be linked to the Crash dataset using the "CRASH_RECORD_ID" field, maintaining appropriate relationships.

3. Traffic Crashes - Vehicles
This dataset contains information about vehicles (or units as they are identified in crash reports) involved in a traffic crash. 

***
   
   
## Methods

1. Obtain:
Extracting the data from the following files;
Crash = https://data.cityofchicago.org/Transportation/Traffic-Crashes-Crashes/85ca-t3if/data_preview
Vehicle = https://data.cityofchicago.org/Transportation/Traffic-Crashes-Vehicles/68nd-jvt3/data_preview
People = https://data.cityofchicago.org/Transportation/Traffic-Crashes-People/u6pd-qa9d/data_preview

2. Scrub:
Explore the raw data set and understand the values
Understanding the null values and deciding whether to drop,fill or replace them
Replacing values with meaningful data and converting data types
Deleting irrelevant and redundant columns

3. Explore:
Creating visualizations to better understand the data
Engineering New Columns
Deriving statistics from the data

4. Model:
Created multiple models including KNN and decision trees

5. Interpret:
Evaluating the accuracy score which led to both models having a high accuracy


## Results

### Original Data

The first steps to creating our model was to load the dataset the various data set separately and do cleaning on each by dropping the columns with the highest number of null values.We then merged the cleaned dataset and renamed it to merged dataset which we further did cleaning by eliminating duplicates and irrelevant columns that would not be used in modelling.

This dataset had 529191 rows and 39 columns and this was still a huge dataset to work with we therefore filtered the dataset to only include the year 2023 and we were left with 68767 rows and 39columns 

Furthermore, we created bins or remapped the values to a more simple form for the following columns; 
   * crash_hour
   * age
   * posted_speed_limit
   * traffic_control_device
   * weather_condition
   * crash_date
   * vehicle_year

### Identifying Target
The target column is 'injuries_total'. We converted to '1' if you had one or more injuries and '0' if you had none. The column has been renamed to 'Injuries'.

### Train-Test split
We ran a train-test-split to split the data into training,validation and test sets. We then split the categorical and numerical columns to enable encoding

## Model
We tested the following models k-nearest neighbors and decision trees. They both returned an accuracy rate of 83%

## Conclusion and Observation
- Most of the injuries recorded were caused by drivers between the ages of 25 to 50 years falling into the adult category
- Based on the data, shows that most accidents occur in the afternoon/rush hour.
- It also shows that most accidents occur in speed limit zones labeled between 30-40 mph.
- Most of the vehicles involved in the accidents fell into the old category that is they were on the road for more than ten years
- Most of the accidents occurred where there were no traffic signals but fewer injuries were observed

## Recommendations

1. The City to put restrictions on vehicles allowed on roads to be below ten years
2. The city lowers the speed limit during afternoon/rush hour or more patrol in the 30-40 mph zones.
3. The city should increase the traffic control devices to reduce accidents occurrences


