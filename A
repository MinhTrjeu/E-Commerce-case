# Data Exploration and Cleanning

Using Python - Google Colab vs Power BI 


## Table of Contents

- [PYTHON - GOOGLE COLAB](#-python---google-colab)
  - [Import Library and dataset](#-import-library-and-dataset)
  - [Explore, clean & transform data](#-import-library-and-dataset)
- [POWER BI](#-power-bi)
  - [Transform Data](#1-transform-data)
  - [Dax, Measure](#2-dax-measure)
  - [Create New Table](#3-create-new-table)

---

##  PYTHON - GOOGLE COLAB

## Import dataset
 
```python

import pandas as pd 
import numpy as np 
import matplotlib as plt
import seaborn as sns
from matplotlib import dates
import datetime
```

```python
from google.colab import drive
drive.mount('/content/drive')
```


```python
customers = pd.read_csv('/content/drive/MyDrive/customers_dataset.csv')
order_items = pd.read_csv('/content/drive/MyDrive//order_items_dataset.csv')
order_payments = pd.read_csv('/content/drive/MyDrive/order_payments_dataset.csv')
order_reviews = pd.read_csv('/content/drive/MyDrive/order_reviews_dataset.csv')
orders = pd.read_csv('/content/drive/MyDrive/orders_dataset.csv')
product_name_translation = pd.read_csv('/content/drive/MyDrive/product_category_name_translation.csv')
products = pd.read_csv('/content/drive/MyDrive/products_dataset.csv')

```
  
</details>

## EXPLORE, CLEAN & TRANSFORM DATA

### 1️. Customers Dataset

- There are 4 things I would check in customers dataset:
  - The overall info 
  - There is duplicated value of primary key or not (customer_id)
  - Checking unique values of city name, State.
  - Capitalize the first letter of city name.

 - Overall
  
```python
customer.head() 
```
![image](https://user-images.githubusercontent.com/101379141/202383092-4502607a-157e-4982-b843-d386308398e4.png)

```python
customers.info()
```
![image](https://user-images.githubusercontent.com/101379141/202383205-458cecd8-c962-4ca1-9d38-6b04d45a7fb6.png)

 
-  Check duplicated values 
  
```python

customers.nunique()   
```  
![image](https://user-images.githubusercontent.com/101379141/202384243-a902b51d-6423-41ea-9028-c40731efdddc.png)
  


 - Check unique values of State 

 ```python
customers['customer_state'].unique() 
 ```
![image](https://user-images.githubusercontent.com/101379141/202384543-036fe5fb-9a9b-48fb-abfb-ca6837b96d6e.png)

### 2️. Orders Dataset

- There are 3 things I would check in Orders dataset:
  - Check Overall Info
  - Transform data type of some columns from object to datatime
  - Check Null values

- Overall  
  
```python
orders.head() 
```
![image](https://user-images.githubusercontent.com/101379141/202590328-96673499-1c64-4a7b-a446-84457184fddc.png)

```python
orders.info()
```
![image](https://user-images.githubusercontent.com/101379141/202590347-7419779c-917a-47c9-81c3-bc94df5c63e6.png)
  


- Transform Data Type  
  
```python
#Transforming the data type from object to datetime 
orders['order_purchase_timestamp'] = pd.to_datetime(orders['order_purchase_timestamp'], format = '%Y-%m-%d %H:%M:%S')
orders['order_approved_at'] = pd.to_datetime(orders['order_approved_at'], format = '%Y-%m-%d %H:%M:%S')
orders['order_delivered_carrier_date'] = pd.to_datetime(orders['order_delivered_carrier_date'], format = '%Y-%m-%d %H:%M:%S')
orders['order_delivered_customer_date'] = pd.to_datetime(orders['order_delivered_customer_date'], format = '%Y-%m-%d %H:%M:%S')
orders['order_estimated_delivery_date'] = pd.to_datetime(orders['order_estimated_delivery_date'], format = '%Y-%m-%d %H:%M:%S')

orders.info()
```
![image](https://user-images.githubusercontent.com/101379141/202590474-5722e629-b482-4c4e-8065-f1e7b2b266f6.png)
  

- Check Null Values 

```python
orders.isnull().sum()
```

```python
orders.isnull().mean() * 100

```
![image](https://user-images.githubusercontent.com/101379141/202590671-f64db3e4-4fa4-49d6-9c68-908cea61fee4.png)


---
### 3️. Order Items Dataset

- The  Overall  

 ```python
 order_items.head() 
 ```
 ![image](https://user-images.githubusercontent.com/101379141/202591464-b8cd4a4a-91f9-401c-9c75-e2c33a6235e3.png)

 ```python
 order_items.describe() 
 ```
 ![image](https://user-images.githubusercontent.com/101379141/202591488-d3e2293e-cd45-4865-ac51-c0e7d548658d.png)

 ```python
 order_items.info() 
 ```
 
 ![image](https://user-images.githubusercontent.com/101379141/202591523-23610480-51e9-401c-9ca9-3b462101b617.png)
 
  

 
---
### 4️. Order Payments Dataset

- Overall 

 ```python
 order_payments.head() 
 ```
![image](https://user-images.githubusercontent.com/101379141/202591939-ccd8d81a-2a52-4cab-affc-efded8b4b934.png)

```python
order_payments.info() 
```
![image](https://user-images.githubusercontent.com/101379141/202591974-428d8f50-9fd3-4ce2-b206-8dbbd40c60e1.png)

  
```python
order_payments['payment_type'].unique() 
```
![image](https://user-images.githubusercontent.com/101379141/202591995-81284279-97c3-49a2-a953-f3b0b3bab9cb.png)
  


---
### 5️. Order Reviews Dataset

- There are 2 things that we are doing with this dataset:
  - The Overall
  - Transform data type from object to datetime 

- Overall  

 ```python
 order_reviews.head() 
 ```
![image](https://user-images.githubusercontent.com/101379141/202593250-30d0b6e6-fd98-4413-98ac-93772b75b8d7.png)
  
```python
order_reviews.info() 
```
![image](https://user-images.githubusercontent.com/101379141/202593274-eb0ce20e-5c1e-4b96-8936-ed3a2d43536a.png)
  
```python
order_reviews['review_score'].value_counts()
```
![image](https://user-images.githubusercontent.com/101379141/202593298-38b5ceb6-5e8d-4695-93c6-8d624c479258.png)
 


- Transform data type  

```python
 order_reviews['review_creation_date'] = pd.to_datetime(order_reviews['review_creation_date'])
order_reviews['review_answer_timestamp'] = pd.to_datetime(order_reviews['review_answer_timestamp'])

order_reviews['review_creation_date'] = order_reviews.review_creation_date.dt.strftime('%m/%d/%Y')
order_reviews['review_answer_timestamp'] = order_reviews.review_answer_timestamp.dt.strftime('%m/%d/%Y')
order_reviews.head(5)
 ```
  
![image](https://user-images.githubusercontent.com/101379141/202593442-736774bf-875a-4ff0-a273-bb31b2958a31.png)
 

---  
###  6️. Products Dataset
  
- There are 3 things that we are doing with this dataset:
  - The Overall
  - Checking Null values .
  - Replacing the "0 gram" of product weight to median

- Overall 
  
 ```python
 products.head() 
 ```
![image](https://user-images.githubusercontent.com/101379141/202595562-89179cb5-d1b8-4503-ac9b-908cc286c44a.png)
  
```python
products.info() 
```
![image](https://user-images.githubusercontent.com/101379141/202595592-4a82a95a-9136-48ed-bba7-2fa4bc89777c.png)

  
```python
products.describe()
``` 
![image](https://user-images.githubusercontent.com/101379141/202595632-653f740c-1449-4279-a542-d9d506b269bf.png)

```python
products[products['product_weight_g']== 0]  
```
  
 ![image](https://user-images.githubusercontent.com/101379141/202595685-8a7e6a1c-c51d-4c21-a6b4-779cce86637b.png)


- Check Null Values 

```python
  products.isnull().sum()
  ```
  ![image](https://user-images.githubusercontent.com/101379141/202596089-660af9b9-c2b1-4f9b-b894-945d6c388aba.png)


```python  
products[products['product_category_name'].isnull() == True]
```
![image](https://user-images.githubusercontent.com/101379141/202596188-5f0c384f-8126-4b1e-b4b6-fc80c8d0841b.png)

```python
products[products['product_weight_g'].isnull() == True]
```
  
![image](https://user-images.githubusercontent.com/101379141/202596235-c4e5dffb-90cf-4c80-97a0-3d14e83ba554.png)  

 ```python
  #Drop all 610 Null value rows , because they are not significant ( 610  rows compare to 32951 total entries )
  products = products.dropna()  
  products.isnull().sum()  
 ```
 ![image](https://user-images.githubusercontent.com/101379141/202596277-466fbd1b-d48b-4621-87a7-de256a357f78.png)
                                                                                       

- Check product weight column 

  ```python
  sns.distplot(products['product_weight_g'])
  ```
  ![image](https://user-images.githubusercontent.com/101379141/202597280-5893fdcf-addb-40af-8b80-13b6561c8070.png)
  
  ```python
  products['product_weight_g']= products['product_weight_g'].replace(0, products['product_weight_g'].median())  
  ```
  
  ```python
  products.describe()
  ```
  ![image](https://user-images.githubusercontent.com/101379141/202597233-2e49fc07-7420-4dad-98a2-39934266b62a.png)
  
---  
### 7️. Product Name Translation Dataset
  
- There are 3 things that we are doing with this dataset:
  - Checking The Overall  
  - Merge the product name of 2 table  
  - Checking Null values of merged table and replacing Null values by new category. 

- Overall 

```python
product_name_translation.head()
```
![image](https://user-images.githubusercontent.com/101379141/202599864-11041880-bf87-475b-b51e-2fb433797183.png)

```python
product_name_translation.info()
```
  
![image](https://user-images.githubusercontent.com/101379141/202599948-948b1539-f4af-48cd-b166-b622589b4209.png)
  
- Merge product name of 2 table 

```python
print(product_name_translation['product_category_name'].nunique())
print(products['product_category_name'].nunique()) 
```
![image](https://user-images.githubusercontent.com/101379141/202600071-0df0c1bc-816a-48df-8eef-aa62d1f147b6.png)

```python
product_summarize = products.merge(product_name_translation,how ='left', on = 'product_category_name' )  
```
  
- Check Null values of merged table and Replace Null values 
  
```python
#Check Null values
product_summarize.isnull().sum()  
```
![image](https://user-images.githubusercontent.com/101379141/202600293-a3e49db7-04e0-4845-8eb0-f3ee59b72501.png)

```python
product_summarize[product_summarize['product_category_name_english'].isnull() == True]  
```
![image](https://user-images.githubusercontent.com/101379141/202600383-93313b22-bed2-4d2c-836b-27bf91d69c18.png)

```python
#Replace Null Value by Unspecified

product_summarize['product_category_name_english'] = product_summarize['product_category_name_english'].fillna(value ='Unspecified')  
product_summarize.isnull().sum()  

```
![image](https://user-images.githubusercontent.com/101379141/202600501-2c762e90-fa24-4e68-a958-ca4564de51c6.png)
    

---
### Save File 

```python
#File customers
customers.to_csv('/content/drive/MyDrive/Final/De 1/customers_dataset.csv',index=False)

#File orders dataset
orders.to_csv('/content/drive/MyDrive/Final/De 1/orders_dataset.csv',index=False)

#File orders items
order_items.to_csv('/content/drive/MyDrive/Final/De 1/order_items_dataset.csv',index=False)

#File order payments
order_payments.to_csv('/content/drive/MyDrive/Final/De 1/order_payments_dataset.csv',index=False)

#File order review
order_reviews.to_csv('/content/drive/MyDrive/Final/De 1/order_reviews_dataset.csv',index=False)

#Merged file of product & produc_translation 
product_summarize.to_csv('/content/drive/MyDrive/Final/De 1/product_summarize_dataset.csv',index=False)

