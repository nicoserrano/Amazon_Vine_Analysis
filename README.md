# Amazon_Vine_Analysis
#### *Analysis on Amazon's vine review program using PySpark and AWS RDS with PostgreSQL*

## Overview

In this project I used *US Apparel product reviews* from Amazon. The goal was to analyze if it would be worth it to subscribe to a Vine program if we were to sell similar products through their platform. The vine review program is an incentive model in which customers are gifted free stuff when they write good reviews. I was able to use PySpark to extract, transform, and load (ETL) the data to a AWS *RDS* I created and connected to my PostgreSQL server to be able to query it and extract my finished tables from there. Part of the data transformation was made using pandas as well. 

The objective of this project was to familiarize myself with Spark. Apache Spark is a unified analytics engine for large-sacale data processing. This means that when working with big data, Spark is one of the best technologies out there to use because of its in-memory computation instead of disk-based solution. It allows for lazy evaluation and delaying expressions or commands until its needed. 

## Resources
- Datasets:
  - [US Apparel dataset](https://s3.amazonaws.com/amazon-reviews-pds/tsv/index.txt)

- Technologies used:
  - Google Colab (to run PySpark)
  - Jupyter Notebook
  - AWS S3 and RDS 
  - PostgreSQL

## Results
