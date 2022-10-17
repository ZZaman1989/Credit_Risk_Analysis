# Video Games - Amazon Vine Analysis

## Overview of Project
Since your work with Jennifer on the SellBy project was so successful, you’ve been tasked with another, larger project: analyzing Amazon reviews written by members of the paid Amazon Vine program. The Amazon Vine program is a service that allows manufacturers and publishers to receive reviews for their products. Companies like SellBy pay a small fee to Amazon and provide products to Amazon Vine members, who are then required to publish a review.

In this project, you’ll have access to approximately 50 datasets. Each one contains reviews of a specific product, from clothing apparel to wireless products. You’ll need to pick one of these datasets and use PySpark to perform the ETL process to extract the dataset, transform the data, connect to an AWS RDS instance, and load the transformed data into pgAdmin. Next, you’ll use PySpark, Pandas, or SQL to determine if there is any bias toward favorable reviews from Vine members in your dataset. Then, you’ll write a summary of the analysis for Jennifer to submit to the SellBy stakeholders.

## Deliverables:
This new assignment consists of two technical analysis deliverables and a written report.

1. ***Deliverable 1:*** Perform ETL on Amazon Product Reviews
2. ***Deliverable 2:*** Determine Bias of Vine Reviews
3. ***Deliverable 3:*** A Written Report on the Analysis [README.md]

## Deliverable 1:  
## Perform ETL on Amazon Product Reviews 
### Deliverable Requirements:

Using the cloud ETL process, you’ll create an AWS RDS database with tables in pgAdmin, pick a dataset from the [Amazon Review datasets](https://s3.amazonaws.com/amazon-reviews-pds/tsv/index.txt), and extract the dataset into a DataFrame. You'll transform the DataFrame into four separate DataFrames that match the table schema in pgAdmin. Then, you'll upload the transformed data into the appropriate tables and run queries in pgAdmin to confirm that the data has been uploaded.

> To Deliver. 

**Follow the instructions below:**

1. From the following [Amazon Review datasets](https://s3.amazonaws.com/amazon-reviews-pds/tsv/index.txt), pick a dataset that you would like to analyze. All the datasets have the same schemata, as shown in this image:

2. Create a new database with Amazon RDS just as you did in this module.

3. In pgAdmin, create a new database in your Amazon RDS server that you just create.

4. Download the `challenge_schema.sql` file to your computer.

5. In pgAdmin, run a new query to create the tables for your new database using the code from the `challenge_schema.sql` file.

- After you run the query, you should have the following four tables in your database: customers_table, products_table, review_id_table, and vine_table.

6. Download the `Amazon_Reviews_ETL_starter_code.ipynb` file, then upload the file as a Google Colab Notebook, and rename it `Amazon_Reviews_ETL`.

**NOTE**
> If you try to open the `Amazon_Reviews_ETL_starter_code.ipynb` with jupyter notebook it will give you an error.

7. First **extract** one of the review datasets, then create a new DataFrame.
8. Next, follow the steps below to **transform** the dataset into four DataFrames that will match the schema in the pgAdmin tables:

**NOTE**
> Some datasets have a large number of rows, which will affect the time it takes to complete the following steps.

**The customers_table DataFrame**
To create the `customers_table`, use the code in the `Amazon_Reviews_ETL_starter_code.ipynb` file and follow the steps below to aggregate the reviews by `customer_id`.

* Use the `groupby()` function on the customer_id column of the DataFrame you created in Step 6.
* Count all the customer ids using the `agg()` function by chaining it to the `groupby()` function. After you use this function, a new column will be created, `count(customer_id)`.
* Rename the `count(customer_id)` column using the `withColumnRenamed()` function so it matches the schema for the `customers_table` in pgAdmin.
* The final `customers_table` DataFrame should look like this:

![d1](https://github.com/ZZaman1989/Amazon_Vine_Analysis/blob/main/Resources/D.1.1.png)


**The products_table DataFrame**
To create the `products_table`, use the `select()` function to select the `product_id` and `product_title`, then drop duplicates with the `drop_duplicates()` function to retrieve only unique `product_ids`. Refer to the code snippet provided in the `Amazon_Reviews_ETL_starter_code.ipynb` file for assistance.

The final `products_table` DataFrame should look like this:

![d1](https://github.com/ZZaman1989/Amazon_Vine_Analysis/blob/main/Resources/D.1.2.png)

**The review_id_table DataFrame**
To create the `review_id_table`, use the `select()` function to select the columns that are in the `review_id_table` in [pgAdmin], and convert the review_date column to a date using the code snippet provided in the `Amazon_Reviews_ETL_starter_code.ipynb` file.

The final `review_id_table` DataFrame should look like this:

![d1](https://github.com/ZZaman1989/Amazon_Vine_Analysis/blob/main/Resources/D.1.3.png)

**The vine_table DataFrame**
To create the `vine_table`, use the `select()` function to select only the columns that are in the `vine_table` in [pgAdmin].

The final `vine_table` DataFrame should look like this:

![d1](https://github.com/ZZaman1989/Amazon_Vine_Analysis/blob/main/Resources/D.1.4.png)

**Load the DataFrames into pgAdmin**
1. Make the connection to your AWS RDS instance.
2. Load the DataFrames that correspond to tables in pgAdmin.
3. In pgAdmin, run a query to check that the tables have been populated.


#### Deliverable 1 Requirements
You will earn a perfect score for Deliverable 1 by completing all requirements below:

* The `Amazon_Reviews_ETL.ipynb` file does the following:
    * An Amazon Review dataset is extracted as a DataFrame
    * The extracted dataset is transformed into four DataFrames with the correct columns
    * All four DataFrames are loaded into their respective tables in pgAdmin

#### Deliverable 2 Requirements
You will earn a perfect score for Deliverable 2 by completing all requirements below:

* The `Amazon_Reviews_ETL.ipynb` file does the following:
    * There is a DataFrame or table for the vine_table data using one of three methods above
    * The data is filtered to create a DataFrame or table where there are 20 or more total votes
    * The data is filtered to create a DataFrame or table where the percentage of helpful_votes is equal to or greater than 50%
    * The data is filtered to create a DataFrame or table where there is a Vine review
    * The data is filtered to create a DataFrame or table where there isn’t a Vine review
    * The total number of reviews, the number of 5-star reviews, and the percentage 5-star reviews are calculated for all Vine and non-Vine reviews  

#### Deliverable 3 Requirements

For this part of the Challenge, you’ll write a report that summarizes the analysis you performed in Deliverable 2.

## Results: 
- How many Vine Reviews and non-Vine reviews were there?
  - Total Vine Reviews: 94
  - Total non-Vine Reviews: 48

- How many Vine reviews were 5 stars? How many non-Vine reviews were 5 stars?
  - 5-star Vine reviews: 40,471
  - 5-star non-Vine reviews: 15,663

- What percentage of Vine reviews were 5 stars? What percentage of non-Vine reviews were 5 stars?
  - Percentage of 5-star Vine Reviews: 51%
  - Percentage of 5-star non-Vine Reviews: 38%

## Summary: 
From the results, the Vine Program is sucucessful for video games. Out of the total helpful reviews, more than 50% of them were 5-star rated.  One recommendation that can be implemented to support this statement is calculating the mean of each star ratings on each program's review and see if there are any trends or significant incentives.
