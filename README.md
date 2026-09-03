# ESPN-Cricket-Data-Analysis

## 📊 Project Overview

**ESPN Cricket Data Analysis** is a Power BI project created to analyze cricket performance data collected from the **ESPNcricinfo** website using **Web Scraping, Power Query, DAX, and Data Visualization**.

The project focuses mainly on **Batting and Bowling analysis of India and South Africa**. The scraped data was cleaned and transformed in Power Query and then analyzed using DAX calculations and interactive Power BI visuals.

## 🎯 Project Objective

The main objective of this project is to:

- Extract cricket data from ESPNcricinfo using web scraping.
- Import multiple web pages into Power BI.
- Clean and transform the scraped data using Power Query.
- Analyze batting and bowling performance.
- Compare India and South Africa.
- Calculate player rankings based on Strike Rate.
- Analyze player performance using statistical calculations.
- Create an interactive Power BI dashboard.
- Present cricket insights through charts, cards, tables, and slicers.

## 🌐 Data Source

The data for this project was collected from:

**ESPNcricinfo**

The data includes cricket-related information for **India and South Africa**, including batting and bowling statistics.

## 🛠️ Tools & Technologies

- Power BI Desktop
- Power Query
- DAX
- Web Scraping
- ESPNcricinfo
- Data Cleaning
- Data Transformation
- Data Visualization
- Statistical Analysis

## 🔄 Data Collection & Web Scraping

The first step of the project was to collect cricket data from the ESPNcricinfo website.

A custom Power Query function was created using:

```powerquery
(ps as text) =>
```
This function was used to dynamically access different web pages.

A new Blank Query was then created.

A list of page numbers was generated using:

```powerquery
{1..3}
```

The list was converted into a table and the data type was changed to Text.

After that, an Invoke Custom Function column was created to execute the web-scraping function for each page.

This process allowed multiple pages from ESPNcricinfo to be imported into Power BI.

🧹 Data Cleaning & Transformation
After importing the scraped data, several data-cleaning steps were performed in Power Query.

The main transformations included:

- Cleaning column names.
- Renaming columns.
- Removing unnecessary columns.
- Removing unwanted rows.
- Using First Row as Headers.
- Appending multiple queries.
- Changing data types.
- Handling blank values.
- Handling null values.
- Replacing missing numerical values with 0 where required.
- Converting numerical fields into appropriate data types.
- Preparing the final dataset for analysis.
  
🏏 Batting Data Analysis
A separate scraping process was performed for India and South Africa batting data.

The same Power Query process was followed:

1. Create custom function.
2. Create page list.
3. Convert list to table.
4. Change data type to Text.
5. Invoke custom function.
6. Extract web data.
7. Clean column names.
8. Use first row as headers.
9. Append queries.
10. Clean and transform the data.
11. Load the final batting dataset into Power BI.

The batting analysis includes important fields such as:

- Player
- Runs
- Strike Rate
- Batting statistics
- Performance categories
 
🎯 Bowling Data Analysis
A similar web-scraping process was used to collect India and South Africa bowling data.

The bowling dataset was processed using Power Query by:

- Extracting web data.
- Cleaning column names.
- Removing unnecessary data.
- Promoting the first row as headers.
- Appending queries.
- Changing data types.
- Handling missing values.
- Replacing missing numerical values where required.
The final bowling dataset was then used for Power BI analysis.

📐 DAX Calculations
After completing data cleaning and transformation, DAX calculations were created to perform statistical analysis.

1. Deviation
Deviation calculates the difference between a player's runs and the average runs.
```powerquery
Deviation = Batting[Runs] - AVERAGE(Batting[Runs])

```

A positive value indicates performance above the average, while a negative value indicates performance below the average.

2. Absolute Deviation
Absolute deviation calculates the magnitude of the difference from the average.

```powerquery
Absolute Deviation = ABS(Batting[Deviation])

```


3. Squared Deviation
Squared deviation gives more importance to larger deviations.

```powerquery
Squared Deviation = POWER(Batting[Deviation],2)

```


4. Player Rank
Players were ranked according to their Strike Rate.


```powerquery
Rank = RANKX(ALL(Batting),Batting[SR],,DESC,Dense)

```


Players with higher Strike Rates receive better rankings.

5. Strike Rate Category
Strike Rate categories were assigned using the LOOKUPVALUE function.

```powerquery
Category = LOOKUPVALUE(
    'Strike Rate Table'[Category],
    'Strike Rate Table'[Strike Rate],
    Batting[SR]
)
```

📊 Dashboard
An interactive Power BI dashboard was created after completing the data preparation and DAX calculations.

The dashboard contains:

- 🏏 Batting Analysis
- 🎯 Bowling Analysis
- 📈 Strike Rate Analysis
- 🏆 Player Ranking
- 🇮🇳 India Analysis
- 🇿🇦 South Africa Analysis
- 📉 Deviation Analysis
- 📊 Statistical Analysis
- 🎛️ Interactive Slicers
- 📋 Detailed Player Tables
🎛️ Interactive Filters
Slicers were added to make the dashboard interactive.

Users can filter the analysis based on available fields such as:

- Team
- Player
- Strike Rate
- Performance Category
- Batting Statistics
- Bowling Statistics
  
All dashboard visuals dynamically update when filters are selected.


📈 Visualizations Used

The dashboard can be used to analyze:

- Top run scorers.
- Highest Strike Rate.
- Player rankings.
- Batting performance.
- Bowling performance.
- Strike Rate categories.
- Deviation from average.
- Absolute deviation.
- Squared deviation.

 ## 📊 Interactive Dashboard

<p align="center">

🔗 **[🚀 View Interactive Power BI Dashboard](https://app.powerbi.com/groups/me/reports/f2791269-eebd-4dbe-9dee-d1b2822b00fe?ctid=fa19b9df-6609-4051-89e2-8018d6fb81b4&pbi_source=linkShare)**

</p>



## 📊 Dashboard Preview

<p align="center">
  <img src="dashboard.png" alt="ESPN Cricket Dashboard" width="900">
</p>

<p align="center">

🔗 **[🚀 Open Interactive Power BI Dashboard](YOUR-POWER-BI-LINK)**

</p>


  
