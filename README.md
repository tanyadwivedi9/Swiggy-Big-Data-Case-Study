Title: Case Study on Using a Dataset in Hadoop

Objective:

To demonstrate how to import, store, and process a dataset using Hadoop and execute basic commands on it to analyze data efficiently.

Dataset Details:

Source: Kaggle

File Name: FINALDATASET.csv

HDFS Directory: /dataset

Number of Rows: 100

Number of Columns: 3

Column Name	Description
ID	Unique identifier for each record
QUANTITY	Quantity of the item
ITEM	Name of the item
Steps Performed:
1. Creating the Directory in Hadoop
hdfs dfs -mkdir /dataset
hdfs dfs -put FINALDATASET.csv /dataset

2. Creating Database and Table
CREATE DATABASE mydb;
USE mydb;

CREATE TABLE dataset (
  id INT,
  quantity INT,
  item STRING
)
ROW FORMAT DELIMITED
FIELDS TERMINATED BY ','
STORED AS TEXTFILE;

3. Loading Data into the Table
LOAD DATA INPATH '/dataset/FINALDATASET.csv' INTO TABLE dataset;

4. Running Basic Commands
SELECT * FROM dataset LIMIT 10;
SELECT COUNT(*) FROM dataset;
SELECT item, SUM(quantity) AS total_quantity FROM dataset GROUP BY item;

Tools and Technologies Used:

Hadoop (HDFS)

Hive

Sqoop

Hadoop Command Line Interface
