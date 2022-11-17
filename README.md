[![lifecycle](https://img.shields.io/badge/lifecycle-experimental-orange.svg)](https://www.tidyverse.org/lifecycle/#experimental)

# Flight Distance Calculation with MapReduce

This project was completed as the Team Project at __YCBS 257 Data at Scale class__ in __Professional Development Certificate Program in Data Science and Machine Learning__ at __McGill University__, and the project introduced the MapReduce functions for solving the problems with Big Data. 

## How to use this repository

This repository has the following main directories and files:

#### __Directories__
* __data:__ data with JSON objects in text file
* __output files:__ summary of Kaggle scores / leaderboard status & Kaggle submission files
* __images:__ diagrams created for summary of processes and components

#### __Files__
* __mapper_GA_team3.ipynb:__ mapper program in Python
* __reducer_GA_team3.ipynb:__ reducer program in Python
* __Group Presentation Slides_Team3.pdf:__ the group presentation ppt slides

### Workflow Overview

The project was completed in the following five steps:
* __Review Input Dataset:__
* __Build Mapper:__ 
* __Build Reducer:__
* __Create CSV List:__
* __Data Analysis:__

![workflow](https://github.com/Nicole-Hong/Flight_Distance_Calculation_with_MapReduce/blob/main/images/workflow.JPG)

### System Requirements

This project has been developed using Python and Jupyter Notebook, which are run on a Windows system and Visual Studio Code. 

### Data Requirements

The base model was developed, based on text files with 10,000 JSON objects

### Distance Calculation

Our team used the following Haversine formula to calculate the distances between Beijing and data points in the given dataset, which were in latitudes and longitudes:
![formula](https://github.com/Nicole-Hong/Flight_Distance_Calculation_with_MapReduce/blob/main/images/haversine.JPG)

The Haversine formula was broken down to three sections and implemented into the reducer program for calculating the distances as follows:

![haversine_details](https://github.com/Nicole-Hong/Flight_Distance_Calculation_with_MapReduce/blob/main/images/haversine_details.JPG)

### Key Outputs

The key outpus



