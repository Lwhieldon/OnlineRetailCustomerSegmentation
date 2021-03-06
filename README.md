<p align="center">
<img src="https://github.com/Lwhieldon/OnlineRetailCustomerSegmentation/blob/main/images/giftstore%20logo.png?raw=true" width="200" height="200" />
</p>

# Understanding Giftstore Shop's Customer Base

## Abstract 

Giftstore Shop needs our help to better understand its customers. Let's explore unsupervised machine learning techniques to analyze its customer segments and provide helpful conclusions about its customers with Giftstore Shop's marketing team. The marketing team will use this information to improve their marketing campaigns to customers.
We clean the data and aggregate the data to a customer level, we apply scaling to ensure that our features do not negatively affect the models. Lastly, we compare KMeans, DBSCAN, and Spectral Clustering models to see what model best fits the data. We uncover that DBSCAN performed the best at detecting customer segmentation than the other models.

## Overview & Background
<br>
<p align="center">
<img src="https://github.com/Lwhieldon/OnlineRetailCustomerSegmentation/blob/main/images/Blog-Mining-CRM-Data-Segmentation.png?raw=true" height="150" />
</p>
Customer retention & engagement is key in all business ventures. But in online retail, it is critical! In this repo, I pretend that I am a data scientist hired by UK-based <b>Giftstore Shop</b>'s marketing team to analyze & understand customer insights that will help enhance their marketing campaigns. The marketing team wants to increase website traffic and by proxy purchases made on the online retail site.
<br>
<br>
We understand that Giftstore Shop is an online retailer located in the United Kingdom. They mainly sell "unique" gifts for all occasions: Birthdays, Holidays, etc. The data provided by Giftstore Shop's marketing team consists of online retail data describing the transactions and customers tagged to every customer. Their marketing team has tasked me with identifying overall customer segments and behaviors that these groups share so that the marketing team can tailor campaigns to their customers.
<br>
<br>

## Goals

This repo is part of the work completed within UMBC's DATA602 Course: Intro to Data Analysis and Machine Learning.

In this project, I attempt to achieve the following:
<ol>
<li> <b>Data Preparation</b>: Cleaning & aggregating data to ensure that the data provided does not contain any nulls or outliers before adding to unsupervised learning models. </li>
<li> <b>Deriving New Features From Dataset</b>: Since this is a customer segmentation exercise, I created additional features to extrapolate on customer engagement with Giftstore Shop, including aggregation & creation of categorical labels inferring customer purchasing behaviors.</li>
<li> <b>Comparing Different Unsupervised Learning Models</b>: Comparing K Means, DBSCAN, and Spectral Clustering and analyzing how each model differentiates cluster patterns in the dataset.</li>
</ol>

## Data Details

<a href=https://archive.ics.uci.edu/ml/datasets/online+retail>UCI Machine Online Retail Data Set</a>

This dataset contains 541,909 transactions with 8 attributes explaining each instance. For a UK-based and registered, online-only retail company, the transactions occurred  between 01/12/2010 and 09/12/2011. 

<b>A few notes on the company:</b>
<ul>
<li>Mainly sells unique all-occasion gift-store</li> 
<li>Many of its customers are wholesalers</li> 
</ul>

<b>Attribute Information:</b>
<ul>
<li>InvoiceNo: Invoice number. Nominal. A 6-digit integral number uniquely assigned to each transaction. If this code starts with the letter 'c', it indicates a cancellation.</li> 
<li>StockCode: Product (item) code. Nominal. A 5-digit integral number uniquely assigned to each distinct product.</li> 
<li>Description: Product (item) name. Nominal.</li>
<li>Quantity: The quantities of each product (item) per transaction. Numeric.</li>
<li>InvoiceDate: Invice date and time. Numeric. The day and time when a transaction was generated.</li>
<li>UnitPrice: Unit price. Numeric. Product price per unit in sterling pounds (£).</li>
<li>CustomerID: Customer number. Nominal. A 5-digit integral number uniquely assigned to each customer.</li>
<li>Country: Country name. Nominal. The name of the country where a customer resides.</li>
</ul>

## Outcomes and Conclusions of this Study

After we fit our clustering algorithms to our engineered datasets, we can lower the dimensionality of the data onto a 2D plane to get a better understanding of our customer clusters.
<br>
<br>
By applying dimensionality reduction techniques using PCA (note we use PCA <b>AFTER</b> the data is fit to the model so that it does not affect the model's interpretation of the data), we observe that most customers are clustered together, with some trailing noise to the right of the visual. This could possibly be interpreted as two separate perpendicular clusters but in this analysis we will infer that it is one single cluster (for future analysis, we might want to look at other clustering algorithms that can detect perpedicular clusters):
<ul>
<li> We observe that <b>KMeans</b> broke the single cluster into 3 distinct regions, splitting the primary cluster into 3 equal parts;</li> 
<li><b>DBScan</b> understood that most customers belong to a single cluster (great job, DBScan!);</li> 
<li><b>Spectral Clustering</b> identified that most customers belong to a single segment but still broke off the primary cluster into 2 larger groups to the right of the visual. I consider this the 'happy medium' between Kmeans & DBScan where there is still some presence of smaller clusters but not as much as KMeans. </li>
</ul>
   
Here are the outcomes of each clustering algorithm shown in the visuals below:

<div class="row">
  <div class="column">
    <img src="https://github.com/Lwhieldon/OnlineRetailCustomerSegmentation/blob/main/images/KMEANS.png?raw=true" alt="KMeans" width="75%" height="75%" >
  </div>
  <div class="column">
    <img src="https://github.com/Lwhieldon/OnlineRetailCustomerSegmentation/blob/main/images/DBSCAN.png?raw=true" alt="DBscan" width="75%" height="75%" >
  </div>
  <div class="column">
    <img src="https://github.com/Lwhieldon/OnlineRetailCustomerSegmentation/blob/main/images/SPECTRALCLUSTER.png?raw=true" alt="Spectral Clustering" width="75%" height="75%">
  </div>
</div>

As we observe, KMeans & Spectral Clustering tried to split the large cluster of customers based on customers who are new, who bought few products, and who made a minimal purchases on the site. DBScan detected that most customers generally have the same spending patterns and lumped most all customers into a single cluster, which aligns to the visuals where we observe one distinct cluster. This also aligns with the general observation that most customers are wholesalers.

We can observe each cluster's behavior against our continuous features, demonstrating how each model interpreted customer segmentation. As stated above, KMeans & Spectral Clustering favored customers who did not buy a lot from the site & who were newer; DBScan determined that generally the spending patterns of customers are the same, which aligns with the primary customer cluster:


  <img src="https://github.com/Lwhieldon/OnlineRetailCustomerSegmentation/blob/main/images/KMEANSHistograms.png?raw=true" alt="KMeans" width="75%" height="75%" >
  <img src="https://github.com/Lwhieldon/OnlineRetailCustomerSegmentation/blob/main/images/DBSCANHistograms.png?raw=true" alt="DBscan" width="75%" height="75%">
  <img src="https://github.com/Lwhieldon/OnlineRetailCustomerSegmentation/blob/main/images/SCHistograms.png?raw=true" alt="Spectral Clustering"width="75%" height="75%">

<b>DBScan</b> is recommended for further analysis; I would like to compare DBScan to other clustering algorithms that can detect clusters that are perpendicular to one another on a 2D plane.

<b>So what's next?</b> While we explored KMeans, I suggest that the marketing team conduct a campaign to draw more attention to the online retail site in general so that they can continue to attract new customers and additional revenue streams. However, the clusters indicate that retention could be improved so I recommend an additional campaign that markets to their long term wholesale customers. Perhaps provide discounts for these continued customers so that they come back to purchase again? 

The marketing team is now equipped with information to help drive new campaigns that will hopefully meet their primary customer targets! This way, Giftstore Shop can continue to find new customers while also focusing on current customer retention (since these folks spend a ton!)


## Table of Contents

This assignment contains 3 primary areas:

<ol>
  <li><a href=https://github.com/Lwhieldon/OnlineRetailCustomerSegmentation/blob/main/online_retail_II.xlsx>Dataset in Repo</a>. Local copy of the original dataset from the ICU Machine Learning Repository.</li>
  <li><a href=https://github.com/Lwhieldon/OnlineRetailCustomerSegmentation/blob/main/summaryreport.ipynb>Summary and Report</a>: Jupyter Notebook including a detailed abstract on problems in assignment, code relevant to project, and visualizations supporting the completion of the project. </li>
  <li> <a href=https://github.com/Lwhieldon/OnlineRetailCustomerSegmentation/blob/main/code.ipynb>Code:</a> Area to perform testing of dataset, functions, and implement models before final project output. </li>
 </ol>

<br>
<pre>
Contributors : <a href=https://github.com/Lwhieldon>Lee Whieldon</a>
</pre>

<pre>
Languages    : Python
Tools/IDE    : Anaconda
Libraries    : pandas, numpy, matplotlib, seaborn, sklearn, yellowbrick, os
</pre>

<pre>
Assignment Submitted     : November 2020
</pre>

