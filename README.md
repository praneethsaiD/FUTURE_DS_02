# Social Media Campaign Performance Tracker - Task 2

## Project Overview
This repository contains the solution for **Future Interns Data Science & Analytics Task 2: Social Media Campaign Performance Tracker**. The core objective of this project was to analyze customer demographics and purchasing behavior from a marketing dataset to derive insights that can inform and optimize future social media ad campaigns. The interactive dashboard built from this analysis aims to help businesses understand:
* How customer demographics (age, education, marital status) influence purchasing.
* Total spending across different product categories.
* Customer engagement with marketing campaigns (acceptance rate, complaints).
* Spending habits across different purchase channels.
* Key performance indicators (KPIs) related to customer value.

## Key Deliverables

* Cleaned Marketing Data (CSV format)
* Detailed Data Analysis and Key Performance Indicator (KPI) Calculations
* Interactive Marketing Performance Dashboard (Power BI .pbix file)
* Summary of Insights and Actionable Recommendations for future marketing strategies.

## Data Source
The analysis was performed on the `marketing_data.csv` dataset, which includes customer demographic information, historical spending across various product categories, purchase channel data, and campaign response indicators.
The cleaned version of this data, `cleaned_marketing_data.csv`, is available in this repository.

## Understanding Key Metrics & Derived Features

This project involved working with and deriving several key metrics:
* **Income (`Income`):** Annual household income of the customer.
* **Customer Demographics:** `Year_Birth` (used to derive `Age`), `Education`, `Marital_Status`, `Kidhome` (number of small children), `Teenhome` (number of teenagers at home).
* **Date Customer (`Dt_Customer`):** Date of customer's enrollment with the company.
* **Recency (`Recency`):** Number of days since customer's last purchase.
* **Spending Habits (e.g., `MntWines`, `MntFruits`, `MntMeatProducts`, `MntFishProducts`, `MntSweetProducts`, `MntGoldProds`):** Amounts spent on various product categories.
* **Purchase Channels (e.g., `NumDealsPurchases`, `NumWebPurchases`, `NumCatalogPurchases`, `NumStorePurchases`):** Number of purchases made through different channels.
* **Web Visits (`NumWebVisitsMonth`):** Number of visits to the company’s website in the last month.
* **Campaign Response (`AcceptedCmp1` to `AcceptedCmp5`, `Response`):** Binary indicators if the customer accepted a specific campaign.
* **Complaints (`Complain`):** Binary indicator if the customer complained in the last 2 years.
* **Country (`Country`):** Customer's country.

**Derived Features:**

* **Age (`Age`):** Calculated from `Year_Birth` to understand customer age distribution.
* **Total Spending (`Total_Spending`):** Sum of all `Mnt` (amount spent) columns, representing overall customer expenditure.
* **Total Purchases (`Total_Purchases`):** Sum of all `NumPurchases` columns, indicating overall purchasing frequency.

## Data Cleaning and Preparation

The raw `marketing_data.csv` dataset underwent the following cleaning and transformation steps using Python (Pandas library) to ensure data quality and create analytical features:

* **`Income` Column Cleaning:** Removed '$' and ',' characters, then converted the column to a numeric (`float`) data type.
* **Handling Missing `Income` Values:** Rows with missing income values were dropped to maintain data integrity for financial analysis.
* **`Dt_Customer` Conversion:** The customer enrollment date was converted from an object type to a proper datetime format for time-based analysis.
* **`Age` Calculation:** A new `Age` column was derived by subtracting `Year_Birth` from a reference year (2014, consistent with the latest `Dt_Customer` entry). Outlier `Age` values (e.g., above 100) were filtered out.
* **`Total_Spending` Calculation:** A new column representing the sum of all spending across product categories was created.
* **`Total_Purchases` Calculation:** A new column representing the sum of purchases across all channels was created.

The cleaned and enriched dataset is saved as `cleaned_marketing_data.csv` in this repository.

## Analysis Performed & Key Insights

The interactive Power BI dashboard provides insights across several dimensions:

1.  **Customer Demographics & Profile:**
    * Visualizations of `Age` distribution, `Education` levels, and `Marital_Status` breakdown to understand the primary customer segments.
    * Analysis of `Kidhome` and `Teenhome` to identify family structure impacts on behavior.
    * *Example Insight: Customers in the [Age Range] group, particularly those with [Education Level] and [Marital Status], represent a significant portion of our customer base.*

2.  **Spending Habits & Product Preferences:**
    * Breakdown of `Total_Spending` by individual product categories (Wines, Fruits, Meat, Fish, Sweet, Gold Products) to highlight popular items.
    * Correlation between `Income` and `Total_Spending` to identify high-value customer segments.
    * *Example Insight: There's a strong positive correlation between higher income and increased total spending, particularly on [Specific Product Category].*

3.  **Purchasing Channel Preferences:**
    * Comparison of `NumWebPurchases`, `NumCatalogPurchases`, and `NumStorePurchases` to understand preferred buying methods.
    * *Example Insight: While web purchases are frequent, customers tend to spend more per transaction via catalog purchases.*

4.  **Campaign Performance & Customer Engagement:**
    * Analysis of `Response` rates for the last campaign and acceptance rates for individual campaigns (`AcceptedCmp1` to `AcceptedCmp5`).
    * Insights into `Recency` (days since last purchase) to identify active vs. dormant customers.
    * *Example Insight: Campaign 3 had the highest acceptance rate among customers with lower income, suggesting targeted appeal.*

5.  **Geographical Distribution:**
    * Mapping of customers by `Country` to visualize regional customer density and spending.
    * *Example Insight: The majority of our customers are from [Specific Country], which also accounts for the highest total spending.*

## Tools Used

* **Python:** For comprehensive data cleaning, feature engineering, and preliminary analysis (Libraries: Pandas, NumPy).
* **Microsoft Excel:** Potentially used for initial data review.
* **Power BI Desktop:** Utilized for data modeling, creating advanced measures (DAX), and designing the interactive dashboard.

## How to Access and Use the Dashboard

1.  **Clone the Repository:**
    ```bash
    git clone (https://github.com/praneethsaiD/FUTURE_DS_02/blob/main/TASK%202.pbix)


2.  **Open Power BI Dashboard:**
    * Ensure you have Power BI Desktop installed (download from [Power BI website](https://powerbi.microsoft.com/en-us/downloads/)).
    * Open the `.pbix` file (e.g., `Social_Media_Marketing_Dashboard.pbix`) located in this repository using Power BI Desktop.

3.  **Explore the Dashboard:**
    * The dashboard features interactive filters (slicers) for `Education`, `Marital_Status`, `Country`, `Age` range, and `Dt_Customer` range, allowing for dynamic data exploration.
    * Hover over visuals for detailed tooltips and deeper insights.

## Future Enhancements

* **Customer Segmentation:** Implement advanced clustering techniques (e.g., K-Means) to identify distinct customer segments based on their behavior and demographics.
* **Predictive Modeling:** Build models to predict campaign response likelihood or future spending.
* **Time-Series Analysis:** Further analyze `Dt_Customer` and spending patterns over time to identify seasonal trends or customer lifecycle stages.
* **Integration with Ad Spend Data:** If available, integrate actual ad spend data to calculate more precise ROI and optimize budget allocation per campaign/ad set.

## Contact

Feel free to reach out if you have any questions or feedback!

* **Your Name:** Donthireddy Praneeth Sai Durga Reddy
* **LinkedIn:** www.linkedin.com/in/donthireddy-praneeth-sai-durga-reddy
* **Email:** praneethsaidurgareddy@gmail.com
