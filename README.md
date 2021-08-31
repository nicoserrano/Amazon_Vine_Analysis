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

## Roadmap

The first step was to extract the dataset from an AWS S3 using PySpark in order to transform it and load it to AWS again. Please refer to [Amazon_Reviews_ETL.ipynb](https://github.com/nicoserrano/Amazon_Vine_Analysis/blob/main/Amazon_Reviews_ETL.ipynb) to see the code. Note that I downloaded it as a jupyter notebook file, but it was originally created in Google Colab for PySpark to run. There, I basically divided the whole dataframe into 4 smaller dataframes for better analysis. These dataframes were then loaded to AWS RDS using a a connection from PySpark to PostgreSQL. 

![Screen Shot 2021-08-31 at 2 43 06 PM](https://user-images.githubusercontent.com/83378141/131558534-69e6fe25-e811-49ae-97dc-bd1011f77c6c.png)
![Screen Shot 2021-08-31 at 2 43 14 PM](https://user-images.githubusercontent.com/83378141/131558546-f15f0f5b-6254-4022-8b61-2f3bfde8ea13.png)
![Screen Shot 2021-08-31 at 2 43 22 PM](https://user-images.githubusercontent.com/83378141/131558556-4a9c1b23-8db8-49f9-a7ab-f2a7c91870df.png)
![Screen Shot 2021-08-31 at 2 43 29 PM](https://user-images.githubusercontent.com/83378141/131558568-a8515ae2-b3f7-4062-9dfb-64eaf785e49e.png)

Due to the size of the dataframes it took some time to load to PostgreSQL and the RDS. I then did a few quick queries to check that everything ran smoothly. 

<img width="745" alt="Screen Shot 2021-08-29 at 10 21 45 PM" src="https://user-images.githubusercontent.com/83378141/131558905-90cc438b-fd27-476c-808f-95096f8b9dcb.png">
<img width="743" alt="Screen Shot 2021-08-29 at 10 47 21 PM" src="https://user-images.githubusercontent.com/83378141/131558907-b7ba32fc-1752-4fcb-8d4f-9da12cac9ceb.png">
<img width="740" alt="Screen Shot 2021-08-29 at 11 21 27 PM" src="https://user-images.githubusercontent.com/83378141/131558908-a2c084ee-6702-42b7-9355-22e2bab1c772.png">
<img width="741" alt="Screen Shot 2021-08-29 at 11 25 19 PM" src="https://user-images.githubusercontent.com/83378141/131558909-3b5a6ef3-c351-4824-bfcb-5d562faec371.png">

And lastly, I worked with the last table called `vine_table` to perform the Vine program analysis to filter the best reviews, and see if there were significantly more 5-star reviews in the paid and incentivized (vine) program. The best reviews were those that were highly voted as helpful. Then, I filtered to see which of those were part of the vine program and which were not. Please refer to the [Amazon_Vine_Analysis.ipynb](https://github.com/nicoserrano/Amazon_Vine_Analysis/blob/main/Vine_Review_Analysis.ipynb) 

## Results
- Paid Vine Program
  - 33 total reviews
  - 15 5-star reviews
  - ***45.5%*** of vine reviews were 5-star

- Unpaid reviews
  - 45,388 total reviews
  - 23,733 5-star reviews
  - ***52.3%*** of unpaid reviews were 5-star


## Summary

In conclusion, the vine program might just not be worth it for the apparel category. As it can be seen, there were not many helpful reviews that made part of it (total of 33), and only around half of them were 5-star rated (45%). Very similarly to the unpaid reviews which also only half of them were 5 star rated (52%). Even though the percentages may be misleading as the quantity of helpful reviews varies so much. This, itself, is a sign that the vine program is not very popular in this category. We might not want to pay for the vine program if it is not incentivizing the people to write better reviews. 

The results don't happen to show that there is any positivity bias towards the reviews in the vine program. 

