<p align="center"> <img src="https://github.com/user-attachments/assets/3a99bd7c-2ab5-4bf6-887e-b039c5cf9961" width="900" alt="Road Accident Analysis Banner" style="margin: 12px 0; border-radius: 18px; background: #fff; box-shadow: 0 4px 16px rgba(0,0,0,0.12); padding: 0;"> </p>

# India Road Safety Analytics — Multi-Dimensional EDA & KPI Analysis

A data analytics portfolio project performing exploratory data analysis on India's national road accident statistics (2003–2016). The project analyzes accident patterns across 8 dimensions — state, vehicle type, lane configuration, accident cause, safety device usage, gender demographics, and time of occurrence — to surface actionable road safety insights for policymakers, urban planners, and traffic safety authorities.

---

## Business Problem

Road accidents are a critical public health and infrastructure challenge. India consistently ranks among the highest countries globally for road accident fatalities. Policymakers and traffic authorities need evidence-based answers to questions such as:

- Which states have disproportionately high accident and fatality rates relative to population?
- What are the primary causes of fatal accidents, and which are most preventable?
- Which vehicle types are involved in the most fatalities?
- Does road infrastructure (number of lanes) correlate with accident severity?
- What proportion of deaths are attributable to non-use of safety devices?
- Have accident rates improved over the 2003–2016 period?

This analysis answers those questions using government-published data and quantitative analysis.

---

## Objective

- Identify high-risk states using population-normalized accident and fatality rates
- Quantify the contribution of driver fault vs. infrastructure/environmental causes
- Analyze the relationship between road characteristics (lane count) and accident severity
- Assess the safety performance of different vehicle categories
- Measure the mortality burden attributable to non-use of helmets and seat belts
- Track long-term trends in national accident rates (2003–2016)
- Deliver data-driven recommendations for targeted safety interventions

---

## Dataset

| Dataset | Source | Period | Key Fields |
|---|---|---|---|
| `roadAccStats13-16.csv` | Government road accident statistics | 2013–2016 | Accidents, injuries, deaths per state per lakh population |
| `Details_of_road_accident_deaths_by_situation_state_2014.csv` | NCRB | 2014 | Offender/victim deaths by gender and state |
| `Persons_killed_due_to_Non-use_of_Safety_Device_2016.csv` | MoRTH | 2016 | Deaths by safety device non-usage (helmet, seat belt) |
| `accidents03-16.xls` | MoRTH historical records | 2003–2016 | All-India accident count per year |
| `laneAccidents.csv` | Road infrastructure safety data | 2014 | Accidents/injuries/deaths by lane type per state |
| `reasonOfAccident.csv` | MoRTH | 2014 | Accidents/injuries/deaths by fault category (10 causes) |
| `typeOfVehicle.csv` | MoRTH | 2014 | Accidents/fatalities by vehicle type per state |
| `timeOfOccurence.xls` | MoRTH | 2014, 2016 | Accidents by 3-hour time bands (day vs. night) |

**Coverage:** 37 States and Union Territories  
**Note:** All datasets are sourced from public government publications (MoRTH / NCRB). This is a portfolio project and does not represent any commercial engagement.

---

## Tools & Technologies

| Category | Tools |
|---|---|
| Language | Python 3 |
| Data Manipulation | Pandas, NumPy |
| Visualization | Matplotlib, Seaborn |
| Environment | Jupyter Notebook |

---

## Data Preparation

- Assessed column-level completeness (% non-null) across all datasets
- Dropped rows with missing values in lane and vehicle type datasets (`dropna`)
- Verified no duplicate state records in the primary dataset
- Created derived aggregation columns (sum totals across lane types, vehicle types, fault categories) for cross-state comparison
- Engineered day/night accident totals by summing 3-hour time bands
- Transposed the long-form historical dataset to produce year-as-row format for trend charting

---

## Key Performance Indicators (KPIs)

| KPI | Description |
|---|---|
| Accidents per Lakh Population | Population-normalized accident frequency by state |
| Fatality Rate (Deaths / Accidents) | Proportion of accidents resulting in death |
| Injury Rate (Injured / Accidents) | Proportion of accidents resulting in injury |
| Driver-Fault Accident Share | % of accidents attributable to driver error |
| Two-Wheeler Fatality Share | % of total road deaths involving two-wheelers |
| Helmet Non-Use Death Rate | Deaths per lakh population from non-wearing of helmets |
| Night Accident Ratio | Night accidents as % of total accidents |
| Year-over-Year Accident Trend | National accident count change 2003–2016 |

---

## Analysis Sections

### 1. State-Level Accident Distribution (2013–2016)
- Identifies highest and lowest accident-rate states on a per-lakh-population basis
- Tracks whether state-level rates improved, stagnated, or worsened over four years
- **Finding:** Maharashtra and Tamil Nadu consistently account for the highest absolute accident volumes. North-eastern states (Arunachal Pradesh, Manipur, Mizoram, Nagaland, Tripura) record the lowest volumes, likely reflecting lower vehicle density and road network size.

### 2. Offender & Victim Demographics by Gender (2014)
- Breaks down accident-related deaths by offender and victim gender
- **Finding:** Male offenders and victims account for the overwhelming majority (~94%) of accident-related deaths, indicating male road users face the highest risk exposure — relevant for targeted awareness campaigns.

### 3. Safety Device Non-Compliance Deaths (2016)
- Measures fatalities directly attributable to non-wearing of helmets and non-use of seat belts
- **Finding:** Non-wearing of helmets accounts for a significantly higher share of preventable deaths than non-use of seat belts, highlighting the two-wheeler safety gap.

### 4. Long-Term Accident Trend — All India (2003–2016)
- Plots total national accident count year-over-year
- **Finding:** National accident counts show a broadly increasing trend from 2003, with some moderation after 2012 — but no sustained reduction, indicating that population and vehicle growth has outpaced safety improvements.

### 5. Road Infrastructure Analysis — Accidents by Lane Type (2014)
- Compares accidents, injuries, and deaths across single-lane, two-lane, three-lane (no median), and four-lane (with median) roads
- **Finding:** Two-lane roads account for the highest accident volumes in most states, reflecting their dominance in India's road network. Highways with medians show relatively lower per-accident fatality rates, consistent with international evidence on median barriers reducing head-on collisions.

### 6. Accident Cause Analysis — Fault/Reason Breakdown (2014)
- Decomposes accidents into 10 fault categories: driver fault, other driver fault, pedestrian fault, vehicle condition defect, road condition defect, weather, passenger fault, poor lighting, boulders, and other/unknown
- **Finding:** Driver fault is the dominant cause of accidents and fatalities across nearly all states. Road condition defects and weather account for a small but preventable share. This confirms that human behavior is the primary lever for accident reduction.

### 7. Vehicle Type Safety Analysis (2014)
- Compares total accidents, fatal accidents, persons killed, and persons injured across 7 vehicle categories
- **Finding:** Two-wheelers are involved in the highest number of total and fatal accidents across most states. Trucks/Tempos/Tractors show a disproportionately high fatality-to-accident ratio, indicating higher crash severity. Cars/Jeeps/Taxis represent a high-volume category.

### 8. Time of Occurrence Analysis (2014 & 2016)
- Aggregates accident counts into daytime (06:00–18:00) and nighttime (18:00–06:00) bands across states
- Compares 2014 vs. 2016 day/night patterns
- **Finding:** Daytime accidents significantly outnumber nighttime accidents in total volume, driven by higher traffic density during day hours. However, nighttime accidents tend to have higher severity (fatality rate per accident), consistent with reduced visibility and response time.

---

## Key Insights

| # | Insight | Evidence | Business Implication |
|---|---|---|---|
| 1 | **Driver error dominates accident causation** | Driver fault is the leading category across all states in the reasons dataset | Behavior-change interventions (enforcement, driver education) offer the highest return on investment for accident reduction |
| 2 | **Two-wheelers are the highest-risk vehicle category** | Two-wheelers lead total and fatal accidents in the vehicle type analysis | Helmet enforcement and two-wheeler safety policy should be the primary vehicle-specific focus |
| 3 | **Non-helmet use is a major preventable mortality factor** | Helmet non-use deaths significantly exceed seat belt non-use deaths in 2016 data | Mandatory helmet laws with active enforcement can directly reduce fatality rates |
| 4 | **High-volume states show persistent high rates** | Maharashtra and Tamil Nadu maintain top accident volumes across all four years (2013–2016) | State-level road safety task forces in high-volume states could have outsized national impact |
| 5 | **National accident rates have not meaningfully declined** | All-India trend (2003–2016) shows no sustained downward trend | Systemic policy intervention is needed — incremental measures have not moved the needle |
| 6 | **Night accidents are fewer but more severe** | Day accidents outnumber night accidents; night fatality rates are comparatively higher | Street lighting improvements and night-time enforcement could reduce disproportionate night fatalities |
| 7 | **Trucks and heavy vehicles have high crash severity** | Fatality-to-accident ratios are elevated for trucks/tempos/tractors vs. cars | Overloading regulation, driver fatigue rules, and truck lane restrictions warrant priority attention |

---

## Business Recommendations

1. **Deploy targeted enforcement in top-10 high-accident states** — Maharashtra, Tamil Nadu, Madhya Pradesh, Karnataka, and Rajasthan consistently appear in high-accident brackets. State-specific road safety programs will have the highest national impact.

2. **Prioritize helmet law enforcement for two-wheeler users** — The data clearly shows two-wheelers as the highest-volume and highest-fatality vehicle category, with non-helmet use as a major preventable cause. Active enforcement rather than awareness campaigns alone is supported by the data.

3. **Invest in median barriers on high-volume two-lane highways** — The lane analysis shows two-lane roads with the most accidents. Converting high-traffic stretches to divided highways (4-lane with median) has evidence-based safety benefits.

4. **Focus night-time road safety interventions** — While day accidents are higher in volume, nighttime accidents carry higher mortality. Street lighting upgrades and night patrol deployment on major highways should be prioritized.

5. **Address truck/heavy vehicle fatality severity** — Fatality rates per accident are highest in this category. Hours-of-service regulations, mandatory speed limiters, and overloading checks at state entry points are evidence-based interventions.

6. **Target male road users with behavior-change campaigns** — Male offenders and victims account for ~94% of accident deaths. Gender-targeted awareness and enforcement programs are warranted.

---

## Visualizations

### State/UT-wise Total Number of Road Accidents
<p align="center"><img width="950" height="300" alt="State-wise Road Accidents" src="https://github.com/user-attachments/assets/7218856c-8293-443b-9b4d-f50651e49c8a" /></p>

### Mean Accidents per Lakh Population by Year
<p align="center"><img width="350" alt="Mean Accidents per Lakh Population" src="https://github.com/user-attachments/assets/a6443664-f28b-422d-82ee-20d751a83a5f" /></p>

### State-wise Total Accident Count
<p align="center"><img width="950" alt="State-wise Total Accidents" src="https://github.com/user-attachments/assets/7a3d3b61-48eb-47a2-a1d2-ef4b652440c2" /></p>

### Accident Deaths by Gender
<p align="center"><img width="950" alt="Deaths by Gender" src="https://github.com/user-attachments/assets/8cd3eb86-5c82-4380-a348-765844840361" /></p>

### Accidents by Number of Lanes
<p align="center"><img width="950" alt="Accidents by Lane Type" src="https://github.com/user-attachments/assets/b8e5a8a6-a3e3-4969-a23b-a00fe6f8bca1" /></p>

### People Killed per Lakh Population by State
<p align="center"><img width="950" alt="Killed per Lakh Population" src="https://github.com/user-attachments/assets/f746a032-e49d-41f6-b30a-b6283b42e323" /></p>

### Total Accidents vs. Killed (Scatter — State-level)
<p align="center"><img width="950" alt="Accidents vs Killed" src="https://github.com/user-attachments/assets/4878b269-8738-4a9f-baee-93ec8e855fc0" /></p>

### People Killed by Accident Cause
<p align="center"><img width="950" alt="Killed by Reason" src="https://github.com/user-attachments/assets/d9f03c0c-3bfb-4076-a4b5-ca8d7b08c9e0" /></p>

### Fatal Accidents by Vehicle Type
<p align="center"><img width="950" alt="Fatal Accidents by Vehicle Type" src="https://github.com/user-attachments/assets/4fa17d14-355b-4c34-a620-bbfecf887b43" /></p>

### Accidents by Time of Day (Day vs. Night)
<p align="center"><img width="950" alt="Accidents by Time of Day" src="https://github.com/user-attachments/assets/9360b45b-be2c-40ce-8dac-581261be70e7" /></p>

### National Accident Count Trend (2003–2016)
<p align="center"><img width="950" alt="Accidents per Year" src="https://github.com/user-attachments/assets/76bf2671-d4c0-4e68-b52a-3745b9ebbd50" /></p>

---

## Project Structure

```
├── Code/
│   ├── Road-Accidents-Analysis.ipynb   # Main analysis notebook
│   └── Report.ipynb                    # Summary report notebook
├── Databases/
│   ├── roadAccStats13-16.csv           # State-level accident stats 2013–2016
│   ├── Details_of_road_accident_deaths_by_situation_state_2014.csv
│   ├── Persons_killed_due_to_Non-use_of_Safety_Device_2016.csv
│   ├── accidents03-16.xls              # Historical accident trend 2003–2016
│   ├── laneAccidents.csv               # Accidents by road lane type
│   ├── reasonOfAccident.csv            # Accidents by fault/cause
│   ├── typeOfVehicle.csv               # Accidents by vehicle type
│   └── timeOfOccurence.xls             # Accidents by time of day
├── Images/                             # Exported visualization screenshots
└── README.md
```

---

## How to Run

1. Clone the repository
2. Install dependencies:
   ```bash
   pip install pandas numpy matplotlib seaborn openpyxl xlrd jupyter
   ```
3. Open `Code/Road-Accidents-Analysis.ipynb` in Jupyter Notebook or JupyterLab
4. Update the dataset paths in the data loading cells to point to the `Databases/` folder
5. Run all cells in order (`Kernel > Restart & Run All`)

---

## Conclusion

India's road accident data reveals that the safety challenge is primarily behavioral — driver fault accounts for the largest share of accidents and deaths — with compounding infrastructure and enforcement gaps. Two-wheelers and heavy vehicles represent the highest-priority vehicle categories for safety intervention. The absence of a meaningful declining trend in national accident counts from 2003 to 2016 underscores that incremental measures have not been sufficient, and data-driven, targeted, state-level interventions are needed to move the needle.

This analysis demonstrates end-to-end data analytics skills: data ingestion, quality assessment, cleaning, multi-dimensional exploratory analysis, KPI definition, visualization, and translation of findings into actionable recommendations.
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
