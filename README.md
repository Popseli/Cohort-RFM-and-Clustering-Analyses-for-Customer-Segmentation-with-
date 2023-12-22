## Project Overview
Customer segmentation is the practice of grouping customers based on common characteristics. These customer segments are beneficial in marketing campaigns, in identifying potentially profitable customers, and in developing customer loyalty. A business might segment customers according to a wide range of factors including demographics (e.g age, gender, location), behaviour (e.g previous orders, responses to messaging), psychographics (e.g values, interests, lifestyles) etc. In this project, we perform customer segmentation of a retail business, based on their purchasing behaviours, to guide the business in developing targeted marketing strategies. Three segmentation analyses are applied: cohort retention rate and revenue, RFM and clustering analyses.
#### A. Cohort Retention Rate Analysis
Cohort analysis answers a business question about how a specific segment of users has interacted with a product, or is expected to interact with a product, based on their prior behaviors. Cohorts are groups of users that share specific characteristics and usage patterns over a period of time. Cohorts are useful because they help you segment your user base and collect data about the way they interact with your product throughout their lifecycle. By analyzing different cohorts of users, businesses can track lifetime value, measure long-term engagement, and identify patterns that might help in tailoring personalized marketing campaigns and product improvements. In this project, we perform cohort retention rate analysis. While acquiring new customers is crucial, it’s important not to neglect the ones you already have. Considering that retaining existing customers (and reducing churn) costs a fraction of customer acquisition cost, analyzing customer retention is important for any business. By analyzing customer retention patterns for different user segments, cohort tools reveal patterns in drop-offs. With this insight, strategies can be molded to prevent churn. In addition, we performed cohort revenue analysis to correlate with the cohort retention rate analysis.
#### B. RFM Analysis
RFM stands for Recency, Frequency, and Monetary. This analysis methodology involves evaluating customer behavior based on their transaction recency, frequency, and monetary value. The primary aim is to understand and categorize customers based on their recent purchases, transaction frequency, and overall spending, allowing businesses to implement effective marketing strategies. RFM analysis allows marketers to target specific clusters of customers with communications that are much more relevant for their particular behavior and thus generate much higher rates of response in addition to increased loyalty and customer lifetime value.
#### C. Clustering Analysis
Cluster analysis is a type of unsupervised learning, which means that it does not require predefined labels or categories for the data. Instead, it uses mathematical algorithms to find natural clusters or groups of data points that are similar to each other and different from other groups. The output of cluster analysis is a set of clusters, each with a centroid (the average or representative point of the cluster) and a boundary (the range or distance that defines the cluster). Cluster analysis can help you segment your customers based on their characteristics, preferences, behaviors, or needs; thus, allowing you to better understand your customer base and tailor your marketing efforts accordingly. For example, you can use cluster analysis to identify your most valuable customers and target them with personalized offers or rewards. Additionally, it can help you discover new or niche segments that have unmet needs or untapped potential so that you can create new products, services, or campaigns to satisfy them. Furthermore, it can be used to test different marketing strategies or messages for different segments and measure their effectiveness and response.
## Data
This project uses an e-commerce sales data of a particular online retail store selling items to customers in various countries. 541,909 transactions recorded in this dataset are those made between 1 December 2010 and 9 December 2011. The data has the following attributes:
* InvoiceNo [Nominal]: Invoice number. A 6-digit integral number uniquely assigned to each transaction.
* StockCode [Nominal]: Product (item) code. A 5-digit integral number uniquely assigned to each distinct product.
* Description [Nominal]: Product (item) name
* Quantity [Numeric]: The quantities of each product (item) per transaction. 
* InvoiceDate [Numeric]: Invoice date and time. The day and time when a transaction was generated.
* UnitPrice [Numeric]: Unit price. Product price per unit.
* CustomerID [Nominal]: Customer number. A 5-digit integral number uniquely assigned to each customer.
* Country [Nominal]: Country name. The name of the country where a customer resides.
## Methodology
* Data profiling and cleaning:
  Statistical properties of data were generated to observe characteristics of the entire dataset and each feature. Missing values and errors were observed and handled accordingly.
* Exploratory data analysis:
  Various data analysis tasks were performed to unveil various significant patterns and statistical characteristics of the dataset. These include distributions of number of orders and number of active customers per month, and top customers by purchses and country.
* Customer retention rate cohort analysis:
  Three metrics (cohort month, cohort index and customer counts for each cohort month and index) were computed. A pivot matrix of the metrics was produced and visualized using heatmap, with customer counts presented as fraction of the number of customers for index 1 and for each month (retention matrix). The interpretation of the retention heatmap is given. We also performed revenues cohort analysis to map with the retention analysis to understand any correlations between them.
* RFM analysis:
  Here, recency, frequency and monetary scores of each customer were computed from which RFM segments were generated using a binning approach. Scores of the segments were then computed to classify customers into three clusters namely low, mid and high tier customers. The analysis of the distribution of the customer clusters is provided.
* Clustering analysis:
  A machine learning based clustering technique was applied on the recency, frequency and monetary scores to develop clusters of customers. First, skewness of the dataset was observed and handled in attempt to make the data distribution normal. Using an elbow method with KMeans algorithm, the best number of clusters was determined. Then, five different clustering algorithms were used to evaluate the dataset from which the one that produced the highest silhouette score was identified as the best performing algorithm for the task. The algorithm was then used to develop three customer clusters. Two and three dimensional visualizations of the clusters and the analysis were provided.
## Results
#### A. Cohort Retention Rate Analysis
![](https://github.com/Popseli/Customer-Segmentation-Using-Cohort-RFM-and-Clustering-Analyses/blob/main/Customer_Retention_Rate%208.bmp)

Several observations can be drawn from the heatmap of cohort customer retention rate:
1. The first month (Dec 2010) has exceptionally high recurring customers, up to 50% of customers acquired in this month are still active 12 month later after their acquisition.
2. The retention rate has drastically dropped in the month of Feb, Mar and Nov of 2011, dropping approximately by 80%.
3. Generally, in each month, the number of customers keep coming back to purchase more after a period of time slightly increases, indicating their loyalty or due to improvement of products. However, the behaviour suddenly drops after varying period for each month. For example, customer retention for customers acquired in Jan 2011 was dropped by 10% after 12 months.
#### B. RFM Analysis
![](https://github.com/Popseli/Customer-Segmentation-Using-Cohort-RFM-and-Clustering-Analyses/blob/main/Distribution_of_RFM_Segments.png)

Key observations:
1) We have all types of classes of customers ranging from the best customers to the churned customers. The best customers, who are transacted recently, do so often and spend more than other customers (here classified as 4-4-4) represents a small percentage of the entire customers set (there are only 10 customers). To retain these customers, marketing communications with this group should make them feel valued and appreciated. Keeping them happy should be a top priority.
2) We also see a significant representation of high-spending new customers. This group consists of those customers in 4-1-4 and 4-1-3. These are customers who transacted only once, but very recently and they spent a lot. In this case we have 50 customers.A marketing strategy with this group is to make them feel valued and appreciated and to give them terrific incentives to continue interacting with the brand. 
3) A small number of lowest-spending active loyal customers are observed. This group consists of those customers in segments 4-4-1 and 4-4-2 (they transacted recently and do so often, but spend the least). Here, we have only 3 customers. Marketers should create campaigns for this group that make them feel valued and incentivize them to increase their spend levels. As loyal customers, it often also pays to reward them with special offers if they spread the word about the brand to their friends, e.g., via social networks. 
4) We observe one of the largest classes of customers, churned best customers. This segment consists of those customers in groups 1-4-4, 1-4-3, 1-3-4 and 1-3-3 (they transacted frequently and spent a lot, but it’s been a long time since they have transacted). In this case we have 778 customers. While it’s often challenging to re-engage churned customers, the high value of these customers makes it worthwhile trying. Like with the Best Customers group, it’s important to communicate with them on the basis of their specific preferences, as known from earlier transaction data.
   
![](https://github.com/Popseli/Customer-Segmentation-Using-Cohort-RFM-and-Clustering-Analyses/blob/main/Distribution_of_Customers_in_RFM_Clusters%202.bmp)


#### C. Clustering Analysis
![](https://github.com/Popseli/Customer-Segmentation-Using-Cohort-RFM-and-Clustering-Analyses/blob/main/KMeans_Clustering_of_RFM_Scores%205.jpg)



