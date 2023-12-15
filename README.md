## Unlock Customer Insights: RFM Segmentation & Clustering with RapidMiner

This project showcases my expertise in implementing RFM methodology and clustering using RapidMiner for dynamic customer segmentation. It highlights my proficiency in utilizing these techniques to unlock valuable customer insights, aiding businesses in targeted marketing and strategy formulation.

## Objective:

It's late 2011, and company XYZ hires us as analysts to analyze sales data from its online store. Specifically, the company is interested in segmenting its customers based on their purchasing behaviors to create distinct campaigns for each customer type. This approach aims to achieve more targeted advertising at a lower cost. 

## Key Highlights:

**RFM Methodology:** Leverage the Recency, Frequency, and Monetary framework to decode customer behavior patterns.

**RapidMiner Implementation:** Utilizing RapidMiner for seamless data processing and analysis.

**Clustering Techniques:** Use K-mean algorithm to group customers into meaningful segments for tailored strategies.

**Insightful Visualizations:** Gain actionable insights with visually compelling representations of customer segments.


## Tools Used:

   **Rapidminer Studio** for data transformation, RFM analysis using k-means algorithm and some basic visualizations

## What is RFM Analysis?

The initials RFM correspond to the values of Recency, Frequency, Monetary. RFM analysis is a way to utilize the data we have already gathered from various customer transactions to predict how a future consumer is likely to behave. An RFM model is based on **three factors**:

*Recency --> How recently a consumer made a purchase*

*Frequency --> How often the consumer makes purchases*

*Monetary --> What is the total amount the consumer spends*

## Project Overview:
1. **Data Acquisition:**

    The sales data can be found at the following link: https://www.kaggle.com/datasets/rupakroy/online-retail.

    There are 541,909 records (examples) of transactions.
  
    It covers a time period from December 1st, 2010, to December 9th, 2011, which is a span of 12 months or approximately 55 weeks.




2. **Data Engineering**

    Loading the data, proper definition of variables from the CSV file, and searching for missing values in attributes. Verifying whether missing values impact the analysis results. Also using the available data to create three new attributes (Recency, Frequency, Monetary) and constructing a new table (RFM table).
   


3. **Data Transformation**

    Visualization of the new table and checking for outliers in each attribute. Applying filtering if extreme values are detected. Normalizing the data if they are on different scales.

4. **Clustering with k-means**

    Applying clustering using the k-means algorithm and checking the clusters upon completion. Also assigning each customer_id to the corresponding cluster (Customer segmentation).

5. **Segmentation Analysis**

    Drawing conclusions about the purchasing behavior of each cluster. Creating consumer personas based on the characteristics of each cluster. Providing recommendations to the company for each consumer persona based on the cluster they belong to.  
