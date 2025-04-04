# Module 22 (SparkSQL Challenge)

## **Overview**
The purpose of this analysis is use Apache Spark and SparkSQL to analyze a large dataset of home sales and compute key housing metrics efficiently. 

This challenge focuses on loading a real estate dataset, create temporary views, running SparkSQL queries, caching and uncaching tables, and partitioning the data for optimized performance.

* **The Dataset** - The dataset used for this analysis contains information about records of home sales with features like id, date, date_built, price, bedrooms, bathrooms, sqft_living, sqft_lot, floors, waterfront, view.

* **Stages of the SparkSQL Process** - The stages of the SparkSQL workflow are methodical and aim to leverage big data tools to efficiently process, query, and optimize performance on large datasets. If followed in order, they provide you with an accurate data insights and optimized query runtimes. The stages of the SparkSQL process are as follows: 
1. Read the data from an AWS S3 bucket into a PySpark DataFrame.
2. Create a temporary view (home_sales) to enable SQL-style queries.
3. Write and run SparkSQL queries to compute metrics like average home prices across specific features.
4. Cache the table to improve query performance and reduce computation time.
5. Partition and store the dataset using Parquet format based on date_built.
6. Read and query the partitioned dataset to analyze performance differences.
7. Uncache and verify that temporary tables are removed from memory for cleanup and memory efficiency.

## **Technologies Used**
- Python 
- Google Colab
- Pandas
- Apache Spark / PySpark
    - SparkSession
	- SparkSQL
	- catalog caching utilies
- AWS S3 (data source)
- Parquet File Format


home-sales-challenge/
│   Home_Sales.ipynb        # The main Colab Notebook containing all the code, queries, and outputs.
│	Home_Sales_revised.ipynb	# Input dataset (from AWS)
│  	p_home_sales/           # Output directory containing the partitioned parquet files.
│   README.md          					 # Project documentation (this file)

## **Setup Instructions**
1. **Clone the Repository:**
Clone the GitHub repository and navigate into the project directory

2. **Install the Dependencies:**
openjdk-11-jdk-headless, Apache Spark 3.5.5 (with Hadoop 3), findspark are installed

3. **Configure Environment Variables :**
Set the JAVA_HOME and SPARK_HOME environment variables, and initialize findspark to ensure Spark is correctly linked in your Python environment.

4. **Load the Dataset:** 
Use SparkFiles to load the home_sales_revised.csv file from the provided AWS S3 URL into a PySpark DataFrame.

5. **Create a Temporary View:**
Convert the DataFrame into a temporary view named home_sales to query using SparkSQL.

6. **Run SparkSQL Queries:**
Execute a series of SparkSQL queries to analyze average home prices using filters like number of bedrooms, bathroom, square footage, and view ratings 

7. **Cache the Temporary Table:**
Cache the home_sales table in memory using the SQL command CACHE TABLE home_sales to improve performance for repeated queries.

8. **Partition and Save Data:**
Partition the home sales data by date_built column and save it in Parquet format using .write partitionBy() for efficient storage and access

9. **Load and Query Parquet Data:**
Read the Parquet-formatted data back into a new DataFrame and register it as a temporary view for further SparkSQL analysis.

10. **Uncache and Validate:**
Uncache the home_sales temporary table and verify its removal from memory using isCached().

## Summary
The **SparkSQL Analysis** successfully demonstrated how to use PySpark and SQL-style queries to analyze a large dataset of home sales. The project showcased key techniques such as creating temporary views, filtering data with SQL queries, caching tables for performance optimization, and partitioning data using Parquet for efficient storage and retrieval.

The use of caching significantly improved query performance, while partitioning by date_built allowed for scalable and organized data analysis. Overall, the project reinforced the power and flexibility of SparkSQL for handling large-scale data processing tasks.