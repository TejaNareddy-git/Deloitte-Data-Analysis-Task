# Deloitte-Data-Analysis-Task
Data Visualization using Tableau

# Deloitte Data Analytics Virtual Experience

This repository contains the completed tasks from the **Deloitte Data Analytics Virtual Experience Program** offered by Forage.

## 📌 Overview

The virtual internship simulates a real-world data analytics project at Deloitte. It involves data cleaning, visualization, and interpretation to support strategic business decisions. This experience helped reinforce skills in Excel, SQL, and data storytelling.

##  Key Tasks

1. **Data Cleaning & Preparation**
   - Identified and handled missing or inconsistent data
   - Reformatted datasets for analysis

2. **Data Analysis**
   - Analyzed sales and customer datasets using Excel and SQL
   - Generated insights on customer behavior and business performance

3. **Data Visualization**
   - Created dashboards and visual reports using Excel and Tableau
   - Communicated key business insights with charts and KPIs

4. **Recommendation**
   - Delivered actionable insights to support stakeholder decision-making
   - Prepared a final presentation summarizing findings and suggestions

## 🛠️ Tools & Skills Used

- **Excel** – Data cleaning, pivot tables, dashboarding  
- **SQL** – Querying customer and sales data  
- **Tableau** – Visualizing key performance indicators and trends  
- **Critical Thinking** – Drawing insights from raw data  
- **Data Communication** – Summarizing results for a non-technical audience

## 📂 Files in This Repository

- `/data/` – Raw and cleaned datasets (anonymized or sample data)
- `/notebooks/` – SQL queries and Excel screenshots or workbooks
- `/visualizations/` – Tableau dashboards or reports (PDF or image)
- `final_summary.pdf` – Business insight report or slide deck

## 🏆 Certification

Completed the **Deloitte Data Analytics Virtual Experience Program** through Forage.  

**Disclaimer**: This project is a simulated experience provided by Deloitte via Forage. It does not represent real client data or proprietary business processes.


Task 1: Data analysis
 
Here is the background information on your task
Using a data unification algorithm, the tech team at our client, Daikibo, has converted all telemetry data collected from its 4 factories:

Daikibo Factory Meiyo (Tokyo, Japan)
Daikibo Factory Seiko (Osaka, Japan)
Daikibo Berlin (Berlin, Germany)
Daikibo Shenzhen (Shenzhen, China)
Each location has 9 types of machines, sending a message every 10 mins. Daikibo has been collecting this data for one month (May 2021) and they've shared this data in the form of a single JSON file.

The reason the client wanted to collect telemetry was to answer 2 questions:

In which location did machines break the most?
What are the machines that broke most often in that location?

Task-2 
Create a calculated measure field called "Unhealthy" with a value of 10 for every unhealthy status (representing 10 mins of potential down time since the previous message).
Create a bar chart called “Down Time per Factory”.
Create a new sheet with a new bar chart called “Down Time per Device Type”.
Create a Dashboard with the 2 previous sheets and set the first chart to be used as a filter (selecting a factory in the first chart shows only the down time of the machines in this factory in the second chart).
Tried the given steps, but not getting these values in the chart

Solution
Step 1: Check the Calculated Field Logic
Double-check your Unhealthy calculated field:

Right-click in the Data pane → Edit Calculated Field

Make sure the formula is exactly:

IF [Status] = "Unhealthy" THEN 10 ELSE 0 END
Check the actual values in [Status]:

Drag Status into Rows in a new sheet to view the values.

You might find it's actually "unhealthy" (lowercase), "UNHEALTHY" (uppercase), or has leading/trailing spaces.
Fix by updating the formula to something like:

IF LOWER(TRIM([Status])) = "unhealthy" THEN 10 ELSE 0 END

Step 2: Validate Output
Drag the calculated Unhealthy field into the Text mark in a new sheet to see if any value is 10.

If you still see only zeros, it means none of the conditions are met — again, likely due to mismatched text in Status.

Step 3: Confirm There’s Data
Create a simple table with:

Rows: Factory

Columns: Status

Text: Number of Records

This will show if your dataset actually contains Unhealthy statuses for any factory.



