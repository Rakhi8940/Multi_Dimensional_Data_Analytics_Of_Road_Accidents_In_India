<p align="center"> <img src="https://via.placeholder.com/900x300?text=Road+Accident+Analysis+Banner" width="900" alt="Road Accident Analysis Banner" style="margin: 12px 0; border-radius: 18px; background: #fff; box-shadow: 0 4px 16px rgba(0,0,0,0.12); padding: 0;"> </p>

# 🚗 Road Accident Analysis

Road Accident Analysis is a comprehensive data analytics project that explores patterns, trends, and contributing factors in road accidents using statistical analysis and data visualization. Using Python, it performs data preprocessing, exploratory data analysis, and generates actionable insights from accident data across multiple dimensions.

## 🎯 Objective
- Analyze road accident trends across states and years (2003-2016)
- Identify patterns in accident causes, vehicle types, and time of occurrence
- Examine the impact of safety accessories on accident severity
- Understand the relationship between road characteristics and accident rates
- Visualize demographic trends in accident victims and offenders
- Generate insights for traffic safety improvement

## 📊 Dataset Description

| Feature | Description |
|---------|-------------|
| Accidents | Number of road accidents |
| Injuries | Number of people injured |
| Deaths | Number of deaths |
| State | Geographic location |
| Year | Year of occurrence (2003-2016) |
| Vehicle Type | Type of vehicle involved |
| Lane Count | Number of lanes on road |
| Time of Occurrence | Time when accident occurred |
| Safety Device Usage | Use/Non-use of safety accessories |
| Accident Reason | Cause or fault leading to accident |
| Gender | Gender of victim/offender |

## 🛠️ Technologies Used
- Python
- NumPy – Numerical operations
- Pandas – Data manipulation and analysis
- Matplotlib – Visualization
- Seaborn – Advanced visualization
- Scikit-learn – Data analysis tools
- Jupyter Notebooks – Interactive analysis
- JupyterThemes – Enhanced notebook visualization

## 🧑‍💻 Project Workflow

```python
# Importing libraries
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
import matplotlib as mpl
import seaborn as sns
import sklearn
import csv
import os
import xlrd
from collections import defaultdict
import math as m
from jupyterthemes import jtplot

# Reading datasets
df = pd.read_csv('roadAccStats13-16.csv')
df1 = pd.read_csv('Details_of_road_accident_deaths_by_situation_state_2014.csv')
df2 = pd.read_csv('Persons_killed_due_to_Non-use_of_Safety_Device_2016.csv')
df3 = pd.read_excel('datafile.xls')
df4 = pd.read_csv('laneAccidents.csv')
df5 = pd.read_csv('reasonOfAccident.csv')
df6 = pd.read_csv('typeOfVehicle.csv')
df7 = pd.read_csv('timeOfOccurence.csv')

# Preview data
df.head()
```

## 📈 Key Analysis & Insights

### 📌 DF - Accidents per Lakh Population by State & Year
- Analyzes road accident counts in each state for years 2013-2016
- Normalized by population to identify high-risk states
- Tracks year-on-year trends

### 📌 DF1 - Offender and Victim Deaths by Gender & State
- Examines demographic patterns in accident fatalities
- Compares death rates across genders
- Geographic distribution of accident deaths

### 📌 DF2 - Deaths Due to Non-use of Safety Accessories
- Analyzes impact of safety device usage on fatality rates
- Identifies critical safety gaps
- Data from 2016

### 📌 DF3 - Accident Rate Trends (2003-2016)
- Long-term trend analysis across all states
- Identifies patterns and seasonal variations
- Historical perspective on accident evolution

### 📌 DF4 - Accidents/Injuries/Deaths by Number of Lanes
- Relationship between road characteristics and accident severity
- Impact of lane configuration on safety
- Analysis of accident outcomes

### 📌 DF5 - Accidents/Injuries/Deaths by Fault/Reason
- Identifies primary causes of accidents
- Analyzes preventability of different accident types
- Severity analysis by accident cause

### 📌 DF6 - Accidents/Injuries/Deaths by Vehicle Type
- Performance analysis across different vehicle categories
- Identifies highest-risk vehicle types
- Comparative safety metrics

### 📌 DF7 - Accidents by Time of Occurrence
- Temporal patterns in accident distribution
- Identification of high-risk time periods
- Variation across different times of day

## 📊 Visualizations
📦 DF - Accidents per Lakh Population
<p align="center" /> <img width="350" height="300" alt="image" src="https://via.placeholder.com/350x300?text=DF+Accidents+per+Lakh" />
📦 DF1 - Offender and Victim Deaths
<p align="center" /> <img width="350" height="300" alt="image" src="https://via.placeholder.com/350x300?text=DF1+Deaths+by+Gender" />
📦 DF1 - Deaths Analysis (Visualization 2)
<p align="center" /> <img width="350" height="300" alt="image" src="https://via.placeholder.com/350x300?text=DF1+Deaths+Analysis+2" />
📦 DF1 - Deaths Analysis (Visualization 3)
<p align="center" /> <img width="350" height="300" alt="image" src="https://via.placeholder.com/350x300?text=DF1+Deaths+Analysis+3" />
📦 DF2 - Safety Accessories Impact
<p align="center" /> <img width="350" height="300" alt="image" src="https://via.placeholder.com/350x300?text=DF2+Safety+Accessories" />
📦 DF3 - Accident Rate Trends (2003-2016)
<p align="center" /> <img width="350" height="300" alt="image" src="https://via.placeholder.com/350x300?text=DF3+Accident+Trends" />
📦 DF3 - State-wise Accident Rates
<p align="center" /> <img width="350" height="300" alt="image" src="https://via.placeholder.com/350x300?text=DF3+State+Trends" />
📦 DF3 - Accident Distribution by State
<p align="center" /> <img width="350" height="300" alt="image" src="https://via.placeholder.com/350x300?text=DF3+State+Distribution" />
📦 DF4 - Accidents by Lane Count
<p align="center" /> <img width="350" height="300" alt="image" src="https://via.placeholder.com/350x300?text=DF4+Lanes+Analysis" />
📦 DF5 - Accidents by Fault/Reason
<p align="center" /> <img width="350" height="300" alt="image" src="https://via.placeholder.com/350x300?text=DF5+Fault+Analysis" />
📦 DF6 - Accidents by Vehicle Type
<p align="center" /> <img width="350" height="300" alt="image" src="https://via.placeholder.com/350x300?text=DF6+Vehicle+Type" />
📦 DF7 - Accidents by Time of Occurrence
<p align="center" /> <img width="350" height="300" alt="image" src="https://via.placeholder.com/350x300?text=DF7+Time+Analysis" />

 ## 🔌 Example Use Cases
- Identify high-risk states and time periods for targeted intervention
- Understand vehicle safety performance comparisons
- Analyze effectiveness of safety device usage
- Determine optimal road design for accident prevention
- Predict accident hotspots based on historical patterns
- Support policy-making for traffic safety improvements

## 📁 Project Structure
```
Road-Accident-Analysis/
├── Code/
│   ├── Report.html
│   ├── Report.ipynb
│   ├── Road-Accidents-Analysis-Part-1.ipynb
│   └── Road-Accidents-Analysis-Part-2.ipynb
├── Databases/
│   ├── accidentRate.csv
│   ├── accidents03-16.xls
│   ├── Details_of_road_accident_deaths_by_situation_state_2014.csv
│   ├── laneAccidents.csv
│   ├── location.xls
│   ├── Persons_killed_due_to_Non-use_of_Safety_Device_2016.csv
│   ├── reasonOfAccident.csv
│   ├── roadAccStats13-16.csv
│   ├── timeOfOccurrence.csv
│   └── typeOfVehicle.csv
├── Images/
│   ├── DF Accidents/
│   │   ├── 1.png
│   │   ├── 2.png
│   │   ├── 3.png
│   │   └── 4.png
│   ├── DF1 Offenders-Victims/
│   │   ├── 1.png
│   │   ├── 2.png
│   │   └── 3.png
│   ├── DF2 Accessories/
│   │   └── 1.png
│   ├── DF3 AccidentsPerState/
│   ├── DF4 Lanes/
│   ├── DF5 ReasonsFaults/
│   ├── DF6 VehicleType/
│   ├── DF7 TimeOfOccurrence/
│   └── Images/
├── README.md
└── ...
```

## 🧠 Future Improvements
- Build predictive models for accident forecasting
- Create interactive dashboards (Streamlit/Tableau)
- Implement machine learning for risk classification
- Develop real-time accident monitoring system
- Add geospatial analysis and mapping
- Integrate weather and traffic data for enhanced insights
- Build recommendation system for safety improvements

## 👩‍💻 Author
Made with ❤️ by Rakhi Yadav

### Transforming accident data into safety insights 🚗📊✨
