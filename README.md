# Customer Propensity To Purchase
## Objective
1. Design and implement a data pipeline using Apache Spark with the PySpark Library for pre-processing the raw dataset. 
2. Compare the performance of three supervised classification techniques to suggest an efficient model for predicting whether the customer placed an order

## Dataset overview
**Dataset:** [Link](https://www.kaggle.com/datasets/benpowis/customer-propensity-to-purchase-data) 

**Summary:** This data set represents a day's worth of visit to a fictional website. Each row represents a unique customer, identified by their unique `UserID`. The columns represent feature of the users visit (such as the device they were using) and things the user did on the website in that day. It’s a classic dataset to explore and expand your analytics skills and sensitive with business case in the future 

**Problem:** Predict whether the customer placed an order

**Describe:** It has 445,402 rows in train set and 161,656 rows in test set. Each have 25 columns (features) and can get some describe on the link above but in this data a few of the features we need to consider are:
+ **basket_add_detail**: Did the customer add a product to their shopping basket from the product detail page?
+ **sign_in**: Did the customer sign in to the website?
+ **saw_homepage**: Did the customer visit the website's homepage?
+ **returning_user**: Is this visitor new, or returning?
+ **ordered**: Did the customer place an order?

## Set Up
### Step 1: Configure a Spark cluster with 3 nodes
```
git clone https://github.com/nghoanglong/customer-prosensity.git

cd customer-prosensity

bash buil-image.sh

docker-compose up
```
### Step 2: Access these sites for esuring spark-cluster available
1.  hadoop cluster:  [http://localhost:50070](http://localhost:50070)
2.  hadoop cluster - resource manager:  [http://localhost:8088](http://localhost:8088)
3.  spark cluster:  [https://localhost:8080](https://localhost:8080)
4.  jupyter notebook:  [https://localhost:8888](https://localhost:8888)

### Step 3: Download all dataset from the link above and copy to hadoop-spark-master container
```
docker cp [dataset.csv] hadoop-spark-master:/root
```
### Step 4: Push all dataset to hadoop cluser
```
docker exec -it hadoop-spark-master bash

hdfs dfs -put dataset.csv [hadoop_path]
```
### Step 5: Access jupyter notebook and load data for analyzing

## Technologies
**Language:** Python

**Framework/Libary:** Apache Spark, PySpark, Pandas, Numpy

**Machine Learning Algorithms:** Decision Tree Regression

**Metrics:** Accuracy, F1-score, Recall, Precision
## Contact
Author: Nguyen Hoang Long

Facebook: https://www.facebook.com/umhummmm/

Email: nghoanglong.17december@gmail.com

