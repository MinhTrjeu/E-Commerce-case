 Data Exploration and Cleanning

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
