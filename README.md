# Analyzing the Impact of Demographic Factors on Crime Patterns in Los Angeles

## Project Overview

This project investigates crime data within the Los Angeles area, aiming to uncover correlations between demographic factors and crime patterns. We explore various aspects of this relationship, including crime distribution, trends over time, victim demographics, and geographical clustering to gain a deeper understanding of crime trends and vulnerabilities in different communities.

## Data Sources

*   **Crime Data:** The primary dataset comes from the City of Los Angeles Data Portal: "Crime Data from 2020 to Present" ([https://catalog.data.gov/dataset/crime-data-from-2020-to-present](https://catalog.data.gov/dataset/crime-data-from-2020-to-present))
*   **Los Angeles Demographics:** Demographic data for the Los Angeles area was referenced from DataUSA: ([https://datausa.io/profile/geo/los-angeles-ca#:~:text=1.89M%20people-,In%202021%2C%20there%20were%201.19%20times%20more%20White%20(Non%2D,hispanic%20(1.89M%20people).](https://datausa.io/profile/geo/los-angeles-ca#:~:text=1.89M%20people-,In%202021%2C%20there%20were%201.19%20times%20more%20White%20(Non%2D,hispanic%20(1.89M%20people).))
*   **UCR Handbook:** We use the UCR (Uniform Crime Reporting) Handbook to provide context for crime codes and their associated descriptions.

## Key Findings

### 1. Exploratory Data Analysis (EDA)

*   **Crime Distribution by Area:** We visualized how crime incidents are distributed across different areas using both pie charts and stacked bar plots.
*   **Time Series Analysis:** We tracked crime trends over time, noting a decrease in 2020 potentially influenced by the COVID-19 pandemic.
*   **Top Crime Types:** The analysis identified the most common crimes, with stolen vehicles and simple assault topping the list.
*   **Secondary Crime Codes:** Most crimes involved only a primary code, with less than 7% having secondary codes.
*   **Time of Day:** Crime incidents are most likely to occur in the late afternoon and evening.
*   **Victim Demographics:** We analyzed the distribution of victim descents and ages.

### 2. Data Preparation

*   **Categorical Encoding:** Mapped sex and race to numerical values for modeling.
*   **Age Grouping:** Victims were grouped into age categories.
*   **Rape Code Identification:** A list of crime codes specifically associated with rape was generated.
*   **Crime Classification:** We classified crimes into property and violent crimes based on the UCR guidelines.

### 3. Data Analysis

#### 3.1. All Crimes vs. Violent Crimes
* Initial attempts to correlate crime to demographic factors were unsuccessful, prompting a more specific approach.

#### 3.2. Sexual Crimes
*   Logistic regression identified that individuals in the 0-18 age group and women were more likely to be victims of sexual assault.
*   Random forest regression corroborated these findings, confirming age and sex as significant features.

#### 3.3. Domestic Violence
*   Random forest regression on domestic violence cases showed that age and victim descent were influential predictors of victim sex.
*   We looked at the 'solved' status of crimes, where victim descent was identified as the most significant factor.
*   Logistic regression highlighted specific descents associated with higher solved rates in domestic violence cases.

#### 3.4. Property Crimes
*   Using random forest regression we found that victim descent is the most crucial feature in property crimes.
*   Logistic regression further detailed this insight, showing that specific descents were correlated with higher solved rates.

#### 3.5. Location vs Crime
*   K-Means clustering was used to identify 5 crime hot spots.
*   Each geographical region had distinct crime patterns.
*   Vehicle theft was isolated for further study to understand geographic trends in theft.
*   Kernel density estimation gave a fine-grained view of vehicle theft density.

### Patterns Found

*   **Youth Vulnerability:** The youth population is more vulnerable and has a higher likelihood of experiencing violent crimes.
*   **Ethnic Disparities:** Black and Hispanic communities are disproportionately affected by violent crime.
*   **Minority Vulnerability:** Minority populations, particularly Black and Hispanic, face increased risk of violent crime.
*   **Child Sexual Assault:** Children are most vulnerable to sexual assault.

## Key Code Components

*   **Python Libraries**: Core libraries include `numpy`, `pandas`, `seaborn`, `matplotlib`, `sklearn`, and `pandasql`.
*   **Data Loading**: The crime data is loaded from a CSV using `pandas`, with Google Drive mounting for Colab integration.
*   **Data Cleaning**: We employ mapping techniques to standardize features and remove rows to clean data.
*   **SQL Queries**: `pandasql` is used to execute SQL queries within the notebook for specific data aggregations.
*   **Data Visualization**: Visualizations such as pie charts, bar plots, box plots, heatmaps, and scatter plots were created using `matplotlib` and `seaborn`.
*   **Machine Learning Models**: Logistic Regression, Random Forests, and K-Means clustering were used to get statistical insights from the data.


## Insights and Limitations

### 1. Intensified Policing Post-Protests
*   **Insight:** Increased police presence in inner cities after protests led to more reported crimes, potentially inflating overall statistics.
*   **Limitations:** Underreporting bias, and the potential for correlation vs. causation.

### 2. Post-Protest Civil Unrest
*   **Insight:** Civil unrest after protests may have increased crime, instability, and theft.
*   **Limitations:** Complex social dynamics, and the need for long-term analysis.

### 3. Economic Circumstances
*   **Insight:** The current spike in crime may be related to economic hardship, indicating a transient trend.
*   **Limitations:** Economic indicators alone do not explain the full trend, need for long term observation.

## Conclusion

This analysis reveals crucial demographic and geographic factors that impact crime patterns in Los Angeles. The study highlights the disproportionate impact of violence on certain communities and underscores the vulnerabilities of specific populations. These results emphasize the need for targeted interventions and community support. This research acts as a foundational step for deeper exploration and informs data-driven community safety strategies.

## License

This project is open-source. Please feel free to use, modify, and contribute to the codebase!
