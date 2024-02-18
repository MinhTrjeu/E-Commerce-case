 Case Study - E-commerce Company
🛒 Case Study - E-commerce Company
A. Data Exploration and Cleanning
Using Python - Google Colab vs Power BI

📚 Table of Contents
🔢 PYTHON - GOOGLE COLAB
Import Library and dataset
Explore, clean & transform data
📊 POWER BI
Transform Data
Dax, Measure
Create New Table
👩🏼‍💻 PYTHON - GOOGLE COLAB
🔤 IMPORT LIBRARY AND DATASET
Click to expand ⬇️
🔎 EXPLORE, CLEAN & TRANSFORM DATA
1️⃣ Customers Dataset
There are 4 things I would check in customers dataset:
The overall info
There is duplicated value of primary key or not (customer_id)
Checking unique values of city name, State.
Capitalize the first letter of city name.
The Overall Infomation
Checking duplicated values
Checking unique values of State
Capitalize the first letter of city name
2️⃣ Orders Dataset
There are 3 things I would check in Orders dataset:
Check Overall Info
Transform data type of some columns from object to datatime
Check Null values
The Overall
Transform Data Type
Check Null Values
3️⃣ Order Items Dataset
The order items dataset is clean so we don't need to adjust it.
The Overall
4️⃣ Order Payments Dataset
After The order payments dataset is clean. We don't need to adjust it.
The Overall
5️⃣ Order Reviews Dataset
There are 2 things that we are doing with this dataset:
The Overall
Transform data type from object to datetime
The Overall
Transform data type
6️⃣Products Dataset
There are 3 things that we are doing with this dataset:
The Overall
Checking Null values .
Replacing the "0 gram" of product weight to median
The Overall
Check Null Values
Check product weight column
7️⃣ Product Name Translation Dataset
There are 3 things that we are doing with this dataset:
Checking The Overall
Merge the product name of 2 table
Checking Null values of merged table and replacing Null values by new category.
The Overall
Merge product name of 2 table
Check Null values of merged table and Replace Null values
✔ Save File
Code here
📊 POWER BI
1. Transform Data
After import dataset, we need to promote header of columns and change some data type columns.

Customers dataset
Order Items dataset
Order Payments dataset
Order Reviews dataset
Orders dataset
Product Summarize Dataset
2. Dax, Measure
To support for anlysis chart, We need to create following measure and dax :

1%star - to filter 1 star review
5%star - to filter 5 star review
%Comment - to calculate % order has comment
Average_Score - Average score of orders
Comment - Count of orders has comment
Comment_Star - Calculate review score of orders having comment
Total_time_to_delivery average per customer_city
Voucher_cat - calculate orders has applied voucher
Count Product
Rank Product
3. Create New Table
To match the average score of order. I have to create new table

Average = SUMMARIZECOLUMNS(order_reviews_dataset[order_id],"Average_Score",AVERAGE(order_reviews_dataset[review_score]))
The First Few Rows
Final Model

Click Here
