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
   
  *Create RFM Attributes*

  For Recency select the attributes Customer_id and InvoiceDate using the Select Attributes operator. I create a new attribute indicating the number of weeks that have passed since each purchase (assuming I'm on 31/12/2011) using the following formula:

```
round(date_diff(InvoiceDate,date_parse_custom("30.12.2011","dd.MM.yyyy"))/604800000,0)
```
  Finally, I aggregate the minimum recency with group by customer_id to determine how many weeks ago the customer made their last purchase (most recent purchase).

  For Frequency, select the attributes Customer_id and InvoiceNumber using the Select Attributes operator. I keep only the unique Invoice Numbers for each customer using the remove duplicates operator. Finally, I aggregate the count of Invoice Numbers with group by customer_id to find how many unique orders each customer placed within the examined timeframe.

  For Monetary,  select the attributes Customer_id, Quantity, and Unit Price using the Select Attributes operator. I create a new attribute for the total cost of the purchase using the following formula:

```
round(Quantity*UnitPrice,2)
```

  Finally, perform an aggregation using the sum function for 'monetary', grouped by 'customer_id', to determine the total amount of purchases made by each customer within the examined timeframe.

3. **Data Transformation**

    Visualization of the new table and checking for outliers in each attribute. Applying filtering if extreme values are detected. Normalizing the data if they are on different scales.

    *Outliers*

     Checking to detect any outliers. From the visualization, as seen in the image below, I observe the following:

    Recency doesn't display any outliers, and the data exhibits a certain distribution.
 
   ![Recency](images/recency.png)

    The Frequency column shows a potential outlier at 89 (as also depicted in the related box plot below). Additionally, I notice that the number of occurrences is below 43, while I have three values (89, 86, 52) significantly deviating from the 43, potentially impacting the clustering algorithm as outliers. Logically, the business is likely aware of its top customers, those who shop 89, 86, 52, 43, 40 times during the year (almost weekly), and their specific characteristics. Therefore, the analysis to be conducted will be useful for mining insights from customers with less obvious traits. Hence, we'll filter the frequency for values <40.

  ![Frequency](images/frequency.png)

     The Monetary column displays values <0, so I set a filter for values >0, as these are the valid monetary values. Additionally, I notice that the volume of values is <25,000, so I place a filter for outliers <25,000, given that, as shown in the histogram, I have some extreme values.

     ![Monetary](images/monetary.png)

5. **Clustering with k-means**

    Applying clustering using the k-means algorithm and checking the clusters upon completion. Also assigning each customer_id to the corresponding cluster (Customer segmentation).

6. **Segmentation Analysis**

    Drawing conclusions about the purchasing behavior of each cluster. Creating consumer personas based on the characteristics of each cluster. Providing recommendations to the company for each consumer persona based on the cluster they belong to.  
