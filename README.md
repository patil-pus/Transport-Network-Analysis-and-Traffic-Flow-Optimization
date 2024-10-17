## Dataset Overview

The dataset used for traffic volume prediction and shortest path analysis contains various road attributes such as **length**, **speed**, **capacity**, and **traffic flow**. Below is a sample of the dataset structure:
| ID  | LENGTH (km) | STREET_NAM          | FF_SPEED_I | FF_SPEED | FF_TIME (min) | AB_CAPACI1 | BA_CAPACI1 | AB_FLOW_AM | BA_FLOW_AM | AB_FLOW_MD | BA_FLOW_MD | AB_FLOW_PM | BA_FLOW_PM | AB_FLOW_NT | BA_FLOW_NT | AB_VOL_DAI | BA_VOL_DAI | TOT_VOL_DA | AB_TRK_DAI | BA_TRK_DAI | TOT_TRK_DA | Shape_Leng | geometry (example) |
|-----|-------------|---------------------|------------|----------|---------------|------------|------------|------------|------------|------------|------------|------------|------------|------------|------------|------------|------------|------------|------------|------------|------------|------------|--------------------|
| 101 | 2.5         | BUCKMINSTER ROAD     | 50         | 60       | 5             | 1000       | 1200       | 800        | 700        | 850        | 750        | 900        | 850        | 600        | 500        | 4500       | 4300       | 8800       | 1000       | 950        | 1950       | 2500       | POINT(1.0, 2.0)    |
| 102 | 1.8         | SUMNER ROAD          | 45         | 55       | 4             | 900        | 950        | 600        | 620        | 700        | 680        | 750        | 780        | 550        | 500        | 3600       | 3500       | 7100       | 850        | 800        | 1650       | 1800       | POINT(1.5, 2.5)    |
| 103 | 3.2         | PROSPECT HILL STREET | 55         | 65       | 6             | 1100       | 1300       | 900        | 880        | 950        | 910        | 1000       | 980        | 750        | 600        | 4850       | 4700       | 9550       | 1100       | 1050       | 2150       | 2700       | POINT(2.0, 3.0)    |
| 104 | 2.0         | DIAMOND HILL RD      | 50         | 60       | 5             | 950        | 1000       | 700        | 750        | 780        | 800        | 820        | 850        | 600        | 580        | 3900       | 3850       | 7750       | 950        | 900        | 1850       | 2300       | POINT(1.8, 2.3)    |

### Column Descriptions:
- **ID**: Unique identifier for each road segment.
- **LENGTH**: Length of the road segment in kilometers.
- **STREET_NAM**: Name of the street.
- **FF_SPEED_I / FF_SPEED**: Initial and final free-flow speeds (km/h).
- **FF_TIME**: Free-flow travel time in minutes.
- **AB_CAPACI1 / BA_CAPACI1**: Road capacity in both directions (AB and BA).
- **AB_FLOW_AM / BA_FLOW_AM**: Traffic flow in the morning (AM) peak for both directions.
- **AB_FLOW_MD / BA_FLOW_MD**: Traffic flow in the midday (MD) peak for both directions.
- **AB_FLOW_PM / BA_FLOW_PM**: Traffic flow in the evening (PM) peak for both directions.
- **AB_FLOW_NT / BA_FLOW_NT**: Traffic flow in the nighttime (NT) peak for both directions.
- **TOT_VOL_DA**: Total daily traffic volume.
- **AB_TRK_DAI / BA_TRK_DAI**: Daily truck traffic for both directions.
- **TOT_TRK_DA**: Total daily truck volume.
- **Shape_Leng**: Length of the road shape (used for geospatial analysis).
- **geometry**: Geospatial coordinates for mapping purposes (example shown as `POINT(x, y)`).

---

# Traffic Volume Prediction and Shortest Path Analysis using Machine Learning and NetworkX

This project focuses on predicting traffic volumes on road segments and calculating the shortest path between streets using machine learning models and graph-based algorithms with NetworkX.

## Project Overview

1. **Traffic Volume Prediction**:
   - We applied multiple machine learning models, including **Random Forest**, **Gradient Boosting**, **XGBoost**, **Support Vector Regressor (SVR)**, and **MLP Regressor**.
   - The models were used to predict daily traffic volume based on features such as road **length**, **capacity**, and **free-flow speed**.
   - After comparing model performance, **Random Forest** and **Gradient Boosting** were identified as the best performing models, minimizing error and maximizing prediction accuracy.

2. **Shortest Path Analysis**:
   - Using **NetworkX**, a graph of streets was built where nodes represent streets and edges represent connections (roads).
   - The shortest path between two streets was calculated using road lengths to help identify optimal traffic routes.
   - This analysis helps in identifying problematic areas in the transport network and suggests possible routing optimizations.


Below is a screenshot of the database file used for traffic prediction and analysis:
*Note: The dataset includes columns like `STREET_NAM`, `LENGTH`, `FF_SPEED`, `CAPACITY`, and traffic flow data.*

## Technologies Used
- **Python**: For scripting and model development.
- **Machine Learning**: Using `scikit-learn` and `XGBoost` libraries for predictive modeling.
- **NetworkX**: For building and analyzing the transport network graph.
- **GeoPandas**: For handling geospatial data and shapefiles.
- **Matplotlib**: For data visualization.

## Installation & Usage

1. Clone the repository:
   ```bash
   git clone https://github.com/patil-pus/Transport-Network-Analysis-and-Traffic-Flow-Optimization.git


### Notes:
- The dataset contains essential features used for both **traffic volume prediction** and **shortest path analysis**.
- The **geometry** column provides geospatial data that allows visualization and network analysis of the road segments.
