# Digitally-Analytics-project-1
## Capstone topic: GLOBAL SUPERSTORE
![](https://github.com/Funmilola2025/Digitally-Analytics-project-1/blob/main/Global%20superstore/SUPERSTORE/GLOBAL_SUPERSTOREI_MAGE.png)

## Introduction
## Global Superstore Analysis
This repository contains analysis and insights derived from the Global Superstore dataset, focusing on optimizing product offerings, improving shipping efficiency, targeting high-value customers, and reviewing product subcategories. The goal is to provide data-driven recommendations to enhance profitability, customer satisfaction, and competitiveness.

## Repository Contents
- Data analysis and visualization
- Insights and recommendations
- Strategic decisions for business growth

## Objective
To leverage data analysis and business intelligence to drive informed decision-making and improve Global Superstore's performance.
## Problem Statement
## Global Superstore Challenges
Global Superstore faces challenges in optimizing its operations, product offerings, and customer targeting, leading to:

1. Inefficient product offerings: Product portfolio may not be optimized for each market, leading to reduced sales and profitability.
2. High shipping costs: Shipping costs are high in certain countries, negatively impacting profitability.
3. Inadequate customer targeting: Marketing strategies may not be effectively targeting high-value customers.
4. Suboptimal product subcategories: Certain product subcategories may not be profitable in specific regions.

## Business Objectives
To improve profitability, customer satisfaction, and competitiveness by:

1. Optimizing product offerings and shipping efficiency.
2. Targeting high-value customers effectively.
3. Reviewing and adjusting product subcategories.
4. Making data-driven decisions to drive business growth.

## Key Questions
1. What are the most profitable products and product subcategories in each market?
2. How can shipping efficiency be improved in high-cost countries?
3. Who are the most valuable customers, and how can they be targeted effectively?
4. What product subcategories should be optimized or discontinued in specific regions?

5. ## Skills Used in Global Superstore Analysis in Power BI
## Data Analysis
1. Data modeling
2. Data visualization
3. Data mining

## Power BI Skills
1. Power Query: Data cleaning, transformation, and loading
2. DAX (Data Analysis Expressions): Calculated columns, measures, and tables
3. Data visualization: Creating interactive reports and dashboards

## Business Intelligence
1. Data interpretation
2. Insight generation
3. Storytelling

## Technical Skills
1. Data manipulation
2. Data visualization tools (Power BI)
3. Business intelligence tools (Power BI)

## Soft Skills
1. Analytical thinking
2. Problem-solving
3. Communication

These skills were utilized to analyze the Global Superstore dataset, identify trends, and provide insights to inform business decisions.

## Process Involved in Global Superstore Analysis
## Steps
1. Data Import: Importing data into Power BI
2. Data Cleaning: Cleaning and transforming data using Power Query
3. Data Modeling: Creating relationships between tables
4. Measure Creation: Creating calculated measures using DAX
5. Visualization: Creating interactive visualizations (charts, tables, maps)
6. Analysis: Analyzing data to identify trends, patterns, and insights
7. Reporting: Creating reports and dashboards to present findings
8. Insight Generation: Identifying key insights and recommendations

## Tools
1. Power BI Desktop
2. Power Query
3. DAX

## Methodology
1. Exploratory data analysis
2. Data visualization
3. Business intelligence

This process helps to extract valuable insights from the Global Superstore dataset, informing business decisions and driving growth.

# Data modelling

## Auto model 
        
![](https://github.com/Funmilola2025/Digitally-Analytics-project-1/blob/main/Global%20superstore/SUPERSTORE/Auto_Model.png)  |
## Adjusted model
![](https://github.com/Funmilola2025/Digitally-Analytics-project-1/blob/main/Global%20superstore/SUPERSTORE/Adjusted_%20model.png)

## VISUALISATION
[HERE]https://app.powerbi.com/links/o7S791qDuE?ctid=01d79764-cd74-4163-924b-461e75728222&pbi_source=linkShare
![](https://github.com/Funmilola2025/Digitally-Analytics-project-1/blob/main/Global%20superstore/SUPERSTORE/Gobal_Supperstore%20_Dashboard.png)
## A single data was given and it was divided into fact and dimensional table which include the following;
##Table Analysis in power querY
![](https://github.com/Funmilola2025/Digitally-Analytics-project-1/blob/main/Global%20superstore/SUPERSTORE/Table_%20in_%20power_%20query.png)
# FACT TABLE

![](https://github.com/Funmilola2025/Digitally-Analytics-project-1/blob/main/Global%20superstore/SUPERSTORE/Global_superstore%20table.png)

##SALES TABLE
Source = Csv.Document(File.Contents("C:\Users\Oladeji Funmilola\Documents\Global-Superstore new.csv"),[Delimiter=",", Columns=24, Encoding=1252, QuoteStyle=QuoteStyle.None]),
    #"Promoted Headers" = Table.PromoteHeaders(Source, [PromoteAllScalars=true]),
    #"Changed Type" = Table.TransformColumnTypes(#"Promoted Headers",{{"Row ID", Int64.Type}, {"Order ID", type text}, {"Order Date", type date}, {"Ship Date", type date}, {"Ship Mode", type text}, {"Customer ID", type text}, {"Customer Name", type text}, {"Segment", type text}, {"City", type text}, {"State", type text}, {"Country", type text}, {"Postal Code", Int64.Type}, {"Market", type text}, {"Region", type text}, {"Product ID", type text}, {"Category", type text}, {"Sub-Category", type text}, {"Product Name", type text}, {"Sales", type number}, {"Quantity", Int64.Type}, {"Discount", type number}, {"Profit", type number}, {"Shipping Cost", type number}, {"Order Priority", type text}}),
    #"Filtered Rows" = Table.SelectRows(#"Changed Type", each ([Postal Code] <> null)),
    #"Filtered Rows1" = Table.SelectRows(#"Filtered Rows", each ([Postal Code] <> null and [Postal Code] <> "")),
    #"Removed Other Columns" = Table.SelectColumns(#"Filtered Rows1",{"Row ID", "Order ID", "Customer ID", "Product ID", "Sales", "Quantity", "Discount", "Profit", "Shipping Cost", "Order Priority"}),
    #"Changed Type1" = Table.TransformColumnTypes(#"Removed Other Columns",{{"Profit", Int64.Type}})
in

# DIMENSSIONAL TABLE
 #   Changed Type1"PRODUCTS TABLE Source =
 Csv.Document(File.Contents("C:\Users\Oladeji Funmilola\Documents\Global-Superstore new.csv"),[Delimiter=",", Columns=24, Encoding=1252, QuoteStyle=QuoteStyle.None]),
    #"Promoted Headers" = Table.PromoteHeaders(Source, [PromoteAllScalars=true]),
    #"Changed Type" = Table.TransformColumnTypes(#"Promoted Headers",{{"Row ID", Int64.Type}, {"Order ID", type text}, {"Order Date", type date}, {"Ship Date", type date}, {"Ship Mode", type text}, {"Customer ID", type text}, {"Customer Name", type text}, {"Segment", type text}, {"City", type text}, {"State", type text}, {"Country", type text}, {"Postal Code", Int64.Type}, {"Market", type text}, {"Region", type text}, {"Product ID", type text}, {"Category", type text}, {"Sub-Category", type text}, {"Product Name", type text}, {"Sales", type number}, {"Quantity", Int64.Type}, {"Discount", type number}, {"Profit", type number}, {"Shipping Cost", type number}, {"Order Priority", type text}}),
    #"Filtered Rows" = Table.SelectRows(#"Changed Type", each ([Postal Code] <> null)),
    #"Filtered Rows1" = Table.SelectRows(#"Filtered Rows", each ([Postal Code] <> null and [Postal Code] <> "")),
    #"Removed Other Columns" = Table.SelectColumns(#"Filtered Rows1",{"Product ID", "Category", "Sub-Category", "Product Name"}),
    #"Removed Duplicates" = Table.Distinct(#"Removed Other Columns")
in
    #"Removed Duplicates ## LOCATION TABLE
    Source = Csv.Document(File.Contents("C:\Users\Oladeji Funmilola\Documents\Global-Superstore new.csv"),[Delimiter=",", Columns=24, Encoding=1252, QuoteStyle=QuoteStyle.None]),
    #"Promoted Headers" = Table.PromoteHeaders(Source, [PromoteAllScalars=true]),
    #"Changed Type" = Table.TransformColumnTypes(#"Promoted Headers",{{"Row ID", Int64.Type}, {"Order ID", type text}, {"Order Date", type date}, {"Ship Date", type date}, {"Ship Mode", type text}, {"Customer ID", type text}, {"Customer Name", type text}, {"Segment", type text}, {"City", type text}, {"State", type text}, {"Country", type text}, {"Postal Code", Int64.Type}, {"Market", type text}, {"Region", type text}, {"Product ID", type text}, {"Category", type text}, {"Sub-Category", type text}, {"Product Name", type text}, {"Sales", type number}, {"Quantity", Int64.Type}, {"Discount", type number}, {"Profit", type number}, {"Shipping Cost", type number}, {"Order Priority", type text}}),
    #"Filtered Rows" = Table.SelectRows(#"Changed Type", each ([Postal Code] <> null)),
    #"Filtered Rows1" = Table.SelectRows(#"Filtered Rows", each ([Postal Code] <> null and [Postal Code] <> "")),
    #"Removed Other Columns" = Table.SelectColumns(#"Filtered Rows1",{"City", "State", "Country", "Postal Code", "Market", "Region"}),
    #"Removed Duplicates" = Table.Distinct(#"Removed Other Columns")
in
    #"Removed Duplicates ##CUSTOMER TABLE 
Source = Csv.Document(File.Contents("C:\Users\Oladeji Funmilola\Documents\Global-Superstore new.csv"),[Delimiter=",", Columns=24, Encoding=1252, QuoteStyle=QuoteStyle.None]),
    #"Promoted Headers" = Table.PromoteHeaders(Source, [PromoteAllScalars=true]),
    #"Changed Type" = Table.TransformColumnTypes(#"Promoted Headers",{{"Row ID", Int64.Type}, {"Order ID", type text}, {"Order Date", type date}, {"Ship Date", type date}, {"Ship Mode", type text}, {"Customer ID", type text}, {"Customer Name", type text}, {"Segment", type text}, {"City", type text}, {"State", type text}, {"Country", type text}, {"Postal Code", Int64.Type}, {"Market", type text}, {"Region", type text}, {"Product ID", type text}, {"Category", type text}, {"Sub-Category", type text}, {"Product Name", type text}, {"Sales", type number}, {"Quantity", Int64.Type}, {"Discount", type number}, {"Profit", type number}, {"Shipping Cost", type number}, {"Order Priority", type text}}),
    #"Filtered Rows" = Table.SelectRows(#"Changed Type", each ([Postal Code] <> null)),
    #"Filtered Rows1" = Table.SelectRows(#"Filtered Rows", each ([Postal Code] <> null and [Postal Code] <> "")),
    #"Removed Other Columns" = Table.SelectColumns(#"Filtered Rows1",{"Customer ID", "Customer Name", "Segment"}),
    #"Removed Duplicates" = Table.Distinct(#"Removed Other Columns")
in

    #"Removed Duplicates ## DATE TABLE 
Source = Csv.Document(File.Contents("C:\Users\Oladeji Funmilola\Documents\Global-Superstore new.csv"),[Delimiter=",", Columns=24, Encoding=1252, QuoteStyle=QuoteStyle.None]),
    #"Promoted Headers" = Table.PromoteHeaders(Source, [PromoteAllScalars=true]),
    #"Changed Type" = Table.TransformColumnTypes(#"Promoted Headers",{{"Row ID", Int64.Type}, {"Order ID", type text}, {"Order Date", type date}, {"Ship Date", type date}, {"Ship Mode", type text}, {"Customer ID", type text}, {"Customer Name", type text}, {"Segment", type text}, {"City", type text}, {"State", type text}, {"Country", type text}, {"Postal Code", Int64.Type}, {"Market", type text}, {"Region", type text}, {"Product ID", type text}, {"Category", type text}, {"Sub-Category", type text}, {"Product Name", type text}, {"Sales", type number}, {"Quantity", Int64.Type}, {"Discount", type number}, {"Profit", type number}, {"Shipping Cost", type number}, {"Order Priority", type text}}),
    #"Filtered Rows" = Table.SelectRows(#"Changed Type", each ([Postal Code] <> null)),
    #"Filtered Rows1" = Table.SelectRows(#"Filtered Rows", each ([Postal Code] <> null and [Postal Code] <> "")),
    #"Removed Other Columns" = Table.SelectColumns(#"Filtered Rows1",{"Order Date", "Ship Date"}),
    #"Removed Duplicates" = Table.Distinct(#"Removed Other Columns"),
    #"Inserted Year" = Table.AddColumn(#"Removed Duplicates", "Year", each Date.Year([Order Date]), Int64.Type),
    #"Inserted Month Name" = Table.AddColumn(#"Inserted Year", "Month Name", each Date.MonthName([Order Date]), type text),
    #"Inserted Quarter" = Table.AddColumn(#"Inserted Month Name", "Quarter", each Date.QuarterOfYear([Order Date]), Int64.Type),
    #"Inserted Day Name" = Table.AddColumn(#"Inserted Quarter", "Day Name", each Date.DayOfWeekName([Order Date]), type text),
    #"Renamed Columns" = Table.RenameColumns(#"Inserted Day Name",{{"Quarter", "Order quarterly"}, {"Month Name", "Order month"}, {"Day Name", "Order day"}, {"Year", "Order year"}})
in
    #"Renamed Columns"
    
# Recommendations and Insights
Based on Analysis
1. Optimize Product Offerings: Focus on top-selling and most profitable products in each country.
2. Improve Shipping Efficiency: Reduce shipping costs in high-cost countries like Nigeria.
3. Target High-Value Customers: Develop targeted marketing strategies for most valuable customers.
4. Review Product Subcategories: Consider discontinuing or optimizing least profitable subcategories in specific regions.

Strategic Decisions
1. Geographic Expansion: Consider expanding to new markets with high growth potential.
2. Product Diversification: Explore new product categories or subcategories to increase revenue.
3. Operational Efficiency: Implement cost-saving measures to improve profitability.

Data-Driven Decision Making
1. Monitor Key Performance Indicators (KPIs): Track sales, profit, shipping costs, and customer value.
2. Analyze Customer Behavior: Understand customer preferences and purchasing habits.
3. Stay Agile: Continuously review and adjust strategies based on changing market conditions.

4. # CONCLUSION

By implementing these recommendations, Global Superstore can improve its profitability, customer satisfaction, and competitiveness
    

    

    
    




