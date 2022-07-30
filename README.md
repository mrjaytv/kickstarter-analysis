# Kickstarting with Excel

## Background
A client, Louise, is planning her own crowdfunding for her play Fever. Louise set up her incentives by first determining how much money people have pledged to 
campaigns historically. Louise’s play Fever came close to its fundraising goal in a short amount of time. Louise provided a Kickstarter dataset to perform data 
analysis of different categories 

## Overview and Purpose of Project 
To better understand how different campaigns fared in relation to their launch dates and their funding goals, an analysis and visualize was completed using the excel 
tools and historical dataset provided by Louise. Historically, theater category campaigns fundraised the most successful outcomes of all categories. Within theater 
category, plays campaigned most successful and failed outcomes in this category. Focusing on the theater category and plays subcategory to observe the trend between 
launch dates and their funding goals.  

#### Category vs Outcomes 

![This is an image](https://github.com/mrjaytv/kickstarter-analysis/blob/12bfe8d40dfcbdf1bb0ced269a4ffae48bc8064f/Resources/Category_vs_Outcomes.PNG)

#### Subcategory vs Outcomes

![This is an image](https://github.com/mrjaytv/kickstarter-analysis/blob/12bfe8d40dfcbdf1bb0ced269a4ffae48bc8064f/Resources/Subcategory_vs_Outcomes.PNG)

## Analysis and Challenges

There were two analyses completed utilizing built-in PivotTable and formulas tools in Microsoft Excel spreadsheet. 

#### PivotTable of Theater Campaigns Outcomes VS Launch

![This is an image](https://github.com/mrjaytv/kickstarter-analysis/blob/12bfe8d40dfcbdf1bb0ced269a4ffae48bc8064f/Resources/Theater_Outcomes_vs_Launch_PivotTable.PNG)

#### Chart of Play Outcomes VS Goals

![This is an image](https://github.com/mrjaytv/kickstarter-analysis/blob/12bfe8d40dfcbdf1bb0ced269a4ffae48bc8064f/Resources/Outcomes_vs_Goals_Chart.PNG)

### Analysis of Outcomes Based on Launch Date

In order to analysis the main category by its launch date, a YEAR() function needed to be added to extract the year from the Date Created Conversion column which is 
the launch date. Once the year column was added to the initial dataset, a pivot table was inserted into a new worksheet and filters were added based on main category 
and years.  In the columns, it displays the sum  of successful, failed, and canceled campaign outcomes in a descending order. A line chart with markers was then 
added to visualize the relationship between outcomes and launch month. Lastly, a Theater filter in the Pivotable main category was added.

#### Model 1: Theater Outcomes Based on Launch Date 

![This is an image](https://github.com/mrjaytv/kickstarter-analysis/blob/12bfe8d40dfcbdf1bb0ced269a4ffae48bc8064f/Resources/Theater_Outcomes_vs_Launch.PNG)

### Analysis of Outcomes Based on Goals

To analysis the goals of subcategory for plays, the goal was broken into ranges. Using the COUNTIFS() formula to pull the sum of the outcomes for plays subcategory 
for each column of successful, failed and canceled. Once COUNTIFS() parameters and criteria were set, a total projects column was added. The total projects column 
use the SUM() formula to add up the totals in successful, failed and canceled columns for each goal range in the row. Next, I calculated the percentage for each 
outcome column in each row by using the formula: successful/failed canceled outcome column divided by total projects. To display the cell in percentage, I formatted 
the cell to “Percentage” to the 0 decimal place. A line chart with markers was then added to visualize the relationship between the goal-amount ranges on the x-axis 
and the percentage of successful, failed, or canceled outcomes on the y-axis. 

#### Model 2: Outcomes Based on Goals

![This is an image](https://github.com/mrjaytv/kickstarter-analysis/blob/12bfe8d40dfcbdf1bb0ced269a4ffae48bc8064f/Resources/Outcomes_vs_Goals.PNG)

### Challenges and Difficulties Encountered

Two hurdles encountered in each of the analysis were realted to excel formulas used. In the analysis of outcomes based on launch date, I had slight difficulty in 
removing the years from the rows so only the months appear in the pivotable and PivotChart. At first glance, dragging the Date Created Conversion field into row 
caused additional Years2 and Quarters fields appeared. Initially, I reordered the Date Created Conversion field to the top and noticed the months were appearing. 
However, the years were a subset in each month. By removing Years2 and Quarters fields, only the months appeared in both Pivots.

In the analysis of outcomes based on goals, my sum for each successful, failed, and canceled columns weren’t properly pulling the parameters when using COUNTIFS() 
formula. Initially the number of total goals for each outcome were high numbers. To better understand this formula, a further look at the Microsoft documentation of 
COUNTIFS() was need to help me understand how to pull the parameters for the sum of each column and row. After reviewing the documentation, I added a third criteria 
to only include plays subcategory goals in the sum. Afterwards, the sum of failed outcomes in “Greater than 50000” row was slightly off. With assistance from a study 
group member, they explained that the first criteria were missing an equal sign include 50000 in the total. 

## Results 

Two conclusions drawn from the line chart of theater outcomes by launch date were: 

- Theater campaigns were most successful in the month of May and June. In the month of May and June, there were 111 and 100 successful outcomes, respectively. 

- There are more successful outcomes for theater campaigns than failed outcomes. 

One conclusion from the line chart of outcomes based on goals tab is that when percentage of successful outcomes increased, percentage of failed outcome decreased 
(and vice versa). Also, there were no cancelled outcomes for play subcategory goals.  

One of the limitations of this dataset was an extreme value of outliers for goals and pledges that isn’t captured in Model 1 and Model 2. A possible recommendation 
for this would be to include an additional table of descriptive statistics would display the mean and median of goals and pledges. Accompanied by this table, a graph 
will help visually identify those outliers.
