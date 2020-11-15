<p align="center">
<img src="https://github.com/Lwhieldon/OnlineRetailCustomerSegmentation/blob/main/images/giftstore%20logo.png?raw=true" width="200" height="200" />
</p>

# Finding Giftware Shop's Customer Base

Giftware Shop needs our help to better understand its customers. Let's explore unsupervised machine learning techniques to analyze its customer segments and provide helpful conclusions about its customers with Giftware Shop's marketing team. The marketing team will use this information to improve their marketing compaigns to customers.

## Overview & Background
<br>
<p align="center">
<img src="https://github.com/Lwhieldon/OnlineRetailCustomerSegmentation/blob/main/images/Blog-Mining-CRM-Data-Segmentation.png?raw=true" height="150" />
</p>
Customer retention & engagement is key in all business ventures. But in online retail, it is critical! In this repo, I pretend that I am a data scientist hired by <b>Giftware Shop</b>'s marketing team to analyze & understand customer insights that will help enhance their marketing campaigns. The marketing team wants to increase website traffic and therefore purchases made on the online retail site.
<br>
<br>
We understand that Giftware Shop is an online retailer located in the United Kingdom. They mainly sell "unique" gifts for all occasions: Birthdays, Holidays, etc. The data provided by Giftware Shop's marketing team consists of online retail data describing the transactions and customers tagged to every customer. Their marketing team has tasked me with identifying overall customer segments and identify behaviors that these segments share so that the marketing team can tailor campaigns to these groups.
<br>
<br>

## Goals

This repo is part of the work completed within UMBC's DATA602 Course: Intro to Data Analysis and Machine Learning.

In this project, I attempt to achieve the following:
<ol>
<li> <b>Data Preparation</b>: Cleaning data & aggregating data to ensure that the data provided does not contain any nulls or outliers before adding to unsupervised learning models. </li>
<li> <b>Deriving New Features From Dataset</b>: Since this is a customer segmentation exercise, I created additional features to extrapolate on customer engagement with Giftware Shope, including aggregation and categorical labels inferring customer purchasing behaviors</li>
<li> <b>Comparing Different Unsupervised Learning Models</b>: Comparing K Means, DBSCAN, and Spectral Clustering and analyze how they differentiate cluster patterns in the dataset.</li>
</ol>

## Outcomes of this Study

After we fit our clustering algorithms to our engineered datasets, we can lower the dimensionality of the data onto a 2D plane to get a better understanding of our customer clusters. By applying dimensionality reduction techniques using PCA, we observe that most customer are clustered together, with some trailing noise to the right of the visual. We observe that KMeans broke a single cluster into 3 distinct regions; DBScan understood that most customers belong to a single cluster; Spectral Clustering identified that most customers belong to a single segment but still broke off the primary cluster into 2 larger groups to the right of the visual. 

Here are the outcomes of each clustering algorithm shown in the visuals below:

<div class="row">
  <div class="column">
    <img src="https://github.com/Lwhieldon/OnlineRetailCustomerSegmentation/blob/main/images/KMEANS.png?raw=true" alt="KMeans" >
  </div>
  <div class="column">
    <img src="https://github.com/Lwhieldon/OnlineRetailCustomerSegmentation/blob/main/images/DBSCAN.png?raw=true" alt="DBscan" >
  </div>
  <div class="column">
    <img src="https://github.com/Lwhieldon/OnlineRetailCustomerSegmentation/blob/main/images/SPECTRALCLUSTER.png?raw=true" alt="Spectral Clustering">
  </div>
</div>

KMeans & Spectral Clustering overfit the data: After we reduced the dimensionality by applying PCA and observing clusters, KMeans & Spectral Clustering was not able to detect that the majority of customers fell into a single segmentation. See side

## Data Details

<a href=https://archive.ics.uci.edu/ml/datasets/online+retail>UCI Machine Online Retail Data Set</a>

This dataset contains 541,909 transactions with 8 attributes explaining each instance. The transactions occurred for a UK-based and registered, non-store online retail between 01/12/2010 and 09/12/2011. 

<b>A few notes on the company:</b>
<ul>
<li>Mainly sells unique all-occasion gift-ware</li> 
<li>Many of its customers are wholesalers</li> 
</ul>

<b>Attribute Information:</b>
<ul>
<li>InvoiceNo: Invoice number. Nominal. A 6-digit integral number uniquely assigned to each transaction. If this code starts with the letter 'c', it indicates a cancellation.</li> 
<li>StockCode: Product (item) code. Nominal. A 5-digit integral number uniquely assigned to each distinct product.</li> 
<li>Description: Product (item) name. Nominal.</li>
<li>Quantity: The quantities of each product (item) per transaction. Numeric.</li>
<li>InvoiceDate: Invice date and time. Numeric. The day and time when a transaction was generated.</li>
<li>UnitPrice: Unit price. Numeric. Product price per unit in sterling (Â£).</li>
<li>CustomerID: Customer number. Nominal. A 5-digit integral number uniquely assigned to each customer.</li>
<li>Country: Country name. Nominal. The name of the country where a customer resides.</li>
</ul>


## Table of Contents

This assignment contains 4 areas:

<ol>
  <li><a href=https://github.com/Lwhieldon/OnlineRetailCustomerSegmentation/blob/main/online_retail_II.xlsx>Dataset in Repo</a>. Local copy of the original dataset from the ICU Machine Learning Repository.</li>
  <li><a href=https://github.com/Lwhieldon/OnlineRetailCustomerSegmentation/blob/main/summaryreport.ipynb>Summary and Report</a>: Jupyter Notebook including a detailed abstract on problems in assignment, code relevant to project, and visualizations supporting the completion of the project. </li>
  <li> <a href=https://github.com/Lwhieldon/OnlineRetailCustomerSegmentation/blob/main/code.ipynb>Code:</a> Area to perform testing of dataset, functions, and implement models before final project output. </li>
  <li> <a href=https://github.com/Lwhieldon/OnlineRetailCustomerSegmentation/blob/main/utils.py>utils.py:</a> .py file to store functions I use throughout the project to make notebooks & summary report clean. </li>
</ol>

<br>
<pre>
Contributors : <a href=https://github.com/Lwhieldon>Lee Whieldon</a>
</pre>

<pre>
Languages    : Python
Tools/IDE    : Anaconda
Libraries    : pandas, numpy, matplotlib, seaborn, sklearn
</pre>

<pre>
Assignment Submitted     : November 2020
</pre>

