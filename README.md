[![lifecycle](https://img.shields.io/badge/lifecycle-experimental-orange.svg)](https://www.tidyverse.org/lifecycle/#experimental)

# Flight Distance Calculation with MapReduce

This project was completed as the small scale team project at __YCBS 257 Data at Scale class__ in __Professional Development Certificate Program in Data Science and Machine Learning__ at __McGill University__, and the project introduced the MapReduce functions for solving the problems with Big Data. 

Based on the given flight data, our team extracted the necessary data and calculated the flight distances between Beijing and data points, using MapReduce.

## How to use this repository

This repository has the following main directories and files:

#### __Directories__
* __data:__ flight data with JSON objects in text file
* __output files:__ outputs from the mapper and reducer programs, and from the process of creating the CSV output file
* __images:__ diagrams created for summary of processes and components

#### __Files__
* __mapper_GA_team3.ipynb:__ mapper program in Python
* __reducer_GA_team3.ipynb:__ reducer program in Python
* __Group Presentation Slides_Team3.pdf:__ the group presentation ppt slides

### Workflow Overview

The project was completed in the following five steps:
* __Input Dataset:__ Verify and review the input dataset (i.e. data type, format and structure before processing)
* __Build Mapper:__ Write a mapper program which takes out all flights ids that have the position messages only, the clock, ident and latitude and longitude
* __Build Reducer:__ Write a reducer program which takes the last position of the flight and calculates its distance to Beijing
* __Create CSV List:__ From the reducer output file, produce a CSV list of all flights (ident, id, and distance to Beijing) sorted by closest to furthest to Beijing
* __Data Analysis:__ Analyze the output file with sorted flight distances and summarize the results of the analysis

![workflow](https://github.com/Nicole-Hong/Flight_Distance_Calculation_with_MapReduce/blob/main/images/workflow.JPG)

### Data Requirements

The mapper program was developed, based on the input dataset in a text file with 19,404 JSON objects. The reducer program was developed from the sorted output file from the mapper program, which was also in a text file with JSON objects.

The detail of the input dataset was as follows:

![dataset](https://github.com/Nicole-Hong/Flight_Distance_Calculation_with_MapReduce/blob/main/images/dataset.JPG)

### Distance Calculation

Our team used the following Haversine formula to calculate the distances between Beijing and data points in the given dataset, which were in latitudes and longitudes:
![formula](https://github.com/Nicole-Hong/Flight_Distance_Calculation_with_MapReduce/blob/main/images/haversine.JPG)

The Haversine formula was broken down to three sections and implemented into the reducer program for calculating the distances as follows:

![haversine_details](https://github.com/Nicole-Hong/Flight_Distance_Calculation_with_MapReduce/blob/main/images/haversine_details.JPG)

### Key Outputs

The mapper program produced the flight data in JSON objects, which were mapped and sorted by key-value pairs (__text file: 'groupassignmentdata_mapped_sorted.txt'__), which was further passed to the reducer program as its input. The reducer program produced the data in JSON objects, which were reduced to 'id', 'ident' and 'distance' fields, where 'distance' was calculated from 'latitude' and 'longitude' data by the Haversine function within the reducer program (__text file: 'groupassignmentdata_reducerout.txt'__).  

The final output was the CSV file (__CSV file: 'flight_list_sorted_by_distance.csv'__) with the flight data sorted by the flight distance in the ascending order, after the reducer output text file with JSON objects was transformed to a Pandas dataframe and the sorted flight list in the dataframe was exported to a CSV file.

Additional data analysis was conducted in Jupyter Notebook (__Jupyter Notebook file: 'reducer_GA_team3.ipynb'__), and our team had the following results:

![summary](https://github.com/Nicole-Hong/Flight_Distance_Calculation_with_MapReduce/blob/main/images/summary.JPG)



