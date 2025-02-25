```python
import pandas as pd 
import seaborn as sns
import matplotlib as plt

```


```python
SalesData = pd.read_csv(r"C:\Users\F_zam\Retails Order Full Dataset\Retails Order Dataset.csv", encoding="ISO-8859-1")
```

## Explore the Data

## 1. Top 5 Rows of the Dataset



```python
SalesData.head()
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Row ID</th>
      <th>Order ID</th>
      <th>Order Date</th>
      <th>Ship Date</th>
      <th>Ship Mode</th>
      <th>Customer ID</th>
      <th>Customer Name</th>
      <th>Segment</th>
      <th>Country</th>
      <th>City</th>
      <th>...</th>
      <th>Retail Sales People</th>
      <th>Product ID</th>
      <th>Category</th>
      <th>Sub-Category</th>
      <th>Product Name</th>
      <th>Returned</th>
      <th>Sales</th>
      <th>Quantity</th>
      <th>Discount</th>
      <th>Profit</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>1</td>
      <td>CA-2016-152156</td>
      <td>8/11/2016</td>
      <td>11/11/2016</td>
      <td>Second Class</td>
      <td>CG-12520</td>
      <td>Claire Gute</td>
      <td>Consumer</td>
      <td>United States</td>
      <td>Henderson</td>
      <td>...</td>
      <td>Cassandra Brandow</td>
      <td>FUR-BO-10001798</td>
      <td>Furniture</td>
      <td>Bookcases</td>
      <td>Bush Somerset Collection Bookcase</td>
      <td>Not</td>
      <td>261.96</td>
      <td>2</td>
      <td>0.00</td>
      <td>41.91</td>
    </tr>
    <tr>
      <th>1</th>
      <td>2</td>
      <td>CA-2016-152156</td>
      <td>8/11/2016</td>
      <td>11/11/2016</td>
      <td>Second Class</td>
      <td>CG-12520</td>
      <td>Claire Gute</td>
      <td>Consumer</td>
      <td>United States</td>
      <td>Henderson</td>
      <td>...</td>
      <td>Cassandra Brandow</td>
      <td>FUR-CH-10000454</td>
      <td>Furniture</td>
      <td>Chairs</td>
      <td>Hon Deluxe Fabric Upholstered Stacking Chairs,...</td>
      <td>Not</td>
      <td>731.94</td>
      <td>3</td>
      <td>0.00</td>
      <td>219.58</td>
    </tr>
    <tr>
      <th>2</th>
      <td>3</td>
      <td>CA-2016-138688</td>
      <td>12/6/2016</td>
      <td>12/6/2016</td>
      <td>Second Class</td>
      <td>DV-13045</td>
      <td>Darrin Van Huff</td>
      <td>Corporate</td>
      <td>United States</td>
      <td>Los Angeles</td>
      <td>...</td>
      <td>Anna Andreadi</td>
      <td>OFF-LA-10000240</td>
      <td>Office Supplies</td>
      <td>Labels</td>
      <td>Self-Adhesive Address Labels for Typewriters b...</td>
      <td>Not</td>
      <td>14.62</td>
      <td>2</td>
      <td>0.00</td>
      <td>6.87</td>
    </tr>
    <tr>
      <th>3</th>
      <td>4</td>
      <td>US-2015-108966</td>
      <td>11/10/2015</td>
      <td>11/10/2015</td>
      <td>Standard Class</td>
      <td>SO-20335</td>
      <td>Sean O'Donnell</td>
      <td>Consumer</td>
      <td>United States</td>
      <td>Fort Lauderdale</td>
      <td>...</td>
      <td>Cassandra Brandow</td>
      <td>FUR-TA-10000577</td>
      <td>Furniture</td>
      <td>Tables</td>
      <td>Bretford CR4500 Series Slim Rectangular Table</td>
      <td>Not</td>
      <td>957.58</td>
      <td>5</td>
      <td>0.45</td>
      <td>-383.03</td>
    </tr>
    <tr>
      <th>4</th>
      <td>5</td>
      <td>US-2015-108966</td>
      <td>11/10/2015</td>
      <td>11/10/2015</td>
      <td>Standard Class</td>
      <td>SO-20335</td>
      <td>Sean O'Donnell</td>
      <td>Consumer</td>
      <td>United States</td>
      <td>Fort Lauderdale</td>
      <td>...</td>
      <td>Cassandra Brandow</td>
      <td>OFF-ST-10000760</td>
      <td>Office Supplies</td>
      <td>Storage</td>
      <td>Eldon Fold 'N Roll Cart System</td>
      <td>Not</td>
      <td>22.37</td>
      <td>2</td>
      <td>0.20</td>
      <td>2.52</td>
    </tr>
  </tbody>
</table>
<p>5 rows × 23 columns</p>
</div>




```python
SalesData.columns
```




    Index(['Row ID', 'Order ID', 'Order Date', 'Ship Date', 'Ship Mode',
           'Customer ID', 'Customer Name', 'Segment', 'Country', 'City', 'State',
           'Postal Code', 'Region', 'Retail Sales People', 'Product ID',
           'Category', 'Sub-Category', 'Product Name', 'Returned', 'Sales',
           'Quantity', 'Discount', 'Profit'],
          dtype='object')



## 2. The Last 5 Rows of the Dataset


```python
SalesData.tail()
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Row ID</th>
      <th>Order ID</th>
      <th>Order Date</th>
      <th>Ship Date</th>
      <th>Ship Mode</th>
      <th>Customer ID</th>
      <th>Customer Name</th>
      <th>Segment</th>
      <th>Country</th>
      <th>City</th>
      <th>...</th>
      <th>Retail Sales People</th>
      <th>Product ID</th>
      <th>Category</th>
      <th>Sub-Category</th>
      <th>Product Name</th>
      <th>Returned</th>
      <th>Sales</th>
      <th>Quantity</th>
      <th>Discount</th>
      <th>Profit</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>9989</th>
      <td>9990</td>
      <td>CA-2014-110422</td>
      <td>1/21/2014</td>
      <td>1/23/2014</td>
      <td>Second Class</td>
      <td>TB-21400</td>
      <td>Tom Boeckenhauer</td>
      <td>Consumer</td>
      <td>United States</td>
      <td>Miami</td>
      <td>...</td>
      <td>Cassandra Brandow</td>
      <td>FUR-FU-10001889</td>
      <td>Furniture</td>
      <td>Furnishings</td>
      <td>Ultra Door Pull Handle</td>
      <td>Not</td>
      <td>25.25</td>
      <td>3</td>
      <td>0.2</td>
      <td>4.10</td>
    </tr>
    <tr>
      <th>9990</th>
      <td>9991</td>
      <td>CA-2017-121258</td>
      <td>2/26/2017</td>
      <td>3/3/2017</td>
      <td>Standard Class</td>
      <td>DB-13060</td>
      <td>Dave Brooks</td>
      <td>Consumer</td>
      <td>United States</td>
      <td>Costa Mesa</td>
      <td>...</td>
      <td>Anna Andreadi</td>
      <td>FUR-FU-10000747</td>
      <td>Furniture</td>
      <td>Furnishings</td>
      <td>Tenex B1-RE Series Chair Mats for Low Pile Car...</td>
      <td>Yes</td>
      <td>91.96</td>
      <td>2</td>
      <td>0.0</td>
      <td>15.63</td>
    </tr>
    <tr>
      <th>9991</th>
      <td>9992</td>
      <td>CA-2017-121258</td>
      <td>2/26/2017</td>
      <td>3/3/2017</td>
      <td>Standard Class</td>
      <td>DB-13060</td>
      <td>Dave Brooks</td>
      <td>Consumer</td>
      <td>United States</td>
      <td>Costa Mesa</td>
      <td>...</td>
      <td>Anna Andreadi</td>
      <td>TEC-PH-10003645</td>
      <td>Technology</td>
      <td>Phones</td>
      <td>Aastra 57i VoIP phone</td>
      <td>Yes</td>
      <td>258.58</td>
      <td>2</td>
      <td>0.2</td>
      <td>19.39</td>
    </tr>
    <tr>
      <th>9992</th>
      <td>9993</td>
      <td>CA-2017-121258</td>
      <td>2/26/2017</td>
      <td>3/3/2017</td>
      <td>Standard Class</td>
      <td>DB-13060</td>
      <td>Dave Brooks</td>
      <td>Consumer</td>
      <td>United States</td>
      <td>Costa Mesa</td>
      <td>...</td>
      <td>Anna Andreadi</td>
      <td>OFF-PA-10004041</td>
      <td>Office Supplies</td>
      <td>Paper</td>
      <td>It's Hot Message Books with Stickers, 2 3/4" x 5"</td>
      <td>Yes</td>
      <td>29.60</td>
      <td>4</td>
      <td>0.0</td>
      <td>13.32</td>
    </tr>
    <tr>
      <th>9993</th>
      <td>9994</td>
      <td>CA-2017-119914</td>
      <td>4/5/2017</td>
      <td>9/5/2017</td>
      <td>Second Class</td>
      <td>CC-12220</td>
      <td>Chris Cortes</td>
      <td>Consumer</td>
      <td>United States</td>
      <td>Westminster</td>
      <td>...</td>
      <td>Anna Andreadi</td>
      <td>OFF-AP-10002684</td>
      <td>Office Supplies</td>
      <td>Appliances</td>
      <td>Acco 7-Outlet Masterpiece Power Center, Wihtou...</td>
      <td>Not</td>
      <td>243.16</td>
      <td>2</td>
      <td>0.0</td>
      <td>72.95</td>
    </tr>
  </tbody>
</table>
<p>5 rows × 23 columns</p>
</div>



## 3. Find Shape of our Dataset


```python
SalesData.shape
```




    (9994, 23)



## 4. Get Information about our Dataset (Total rows, Total columns, Datatypes)



```python
SalesData.info()
```

    <class 'pandas.core.frame.DataFrame'>
    RangeIndex: 9994 entries, 0 to 9993
    Data columns (total 23 columns):
     #   Column               Non-Null Count  Dtype  
    ---  ------               --------------  -----  
     0   Row ID               9994 non-null   int64  
     1   Order ID             9994 non-null   object 
     2   Order Date           9994 non-null   object 
     3   Ship Date            9994 non-null   object 
     4   Ship Mode            9994 non-null   object 
     5   Customer ID          9994 non-null   object 
     6   Customer Name        9994 non-null   object 
     7   Segment              9994 non-null   object 
     8   Country              9994 non-null   object 
     9   City                 9994 non-null   object 
     10  State                9994 non-null   object 
     11  Postal Code          9994 non-null   int64  
     12  Region               9994 non-null   object 
     13  Retail Sales People  9994 non-null   object 
     14  Product ID           9994 non-null   object 
     15  Category             9994 non-null   object 
     16  Sub-Category         9994 non-null   object 
     17  Product Name         9994 non-null   object 
     18  Returned             9994 non-null   object 
     19  Sales                9994 non-null   float64
     20  Quantity             9994 non-null   int64  
     21  Discount             9994 non-null   float64
     22  Profit               9994 non-null   float64
    dtypes: float64(3), int64(3), object(17)
    memory usage: 1.8+ MB
    

## 5. Check Null Values 


```python
SalesData.isnull().sum()
```




    Row ID                 0
    Order ID               0
    Order Date             0
    Ship Date              0
    Ship Mode              0
    Customer ID            0
    Customer Name          0
    Segment                0
    Country                0
    City                   0
    State                  0
    Postal Code            0
    Region                 0
    Retail Sales People    0
    Product ID             0
    Category               0
    Sub-Category           0
    Product Name           0
    Returned               0
    Sales                  0
    Quantity               0
    Discount               0
    Profit                 0
    dtype: int64



## 6. Check for Duplicate Data and Drop them


```python
SalesData.duplicated().any()
```




    False



## 7. Get Overall Statistics about the Dataset


```python
SalesData.describe()
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Row ID</th>
      <th>Postal Code</th>
      <th>Sales</th>
      <th>Quantity</th>
      <th>Discount</th>
      <th>Profit</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>count</th>
      <td>9994.000000</td>
      <td>9994.000000</td>
      <td>9994.000000</td>
      <td>9994.000000</td>
      <td>9994.000000</td>
      <td>9994.000000</td>
    </tr>
    <tr>
      <th>mean</th>
      <td>4997.500000</td>
      <td>55190.379428</td>
      <td>229.858022</td>
      <td>3.789574</td>
      <td>0.156203</td>
      <td>28.656973</td>
    </tr>
    <tr>
      <th>std</th>
      <td>2885.163629</td>
      <td>32063.693350</td>
      <td>623.245131</td>
      <td>2.225110</td>
      <td>0.206452</td>
      <td>234.260203</td>
    </tr>
    <tr>
      <th>min</th>
      <td>1.000000</td>
      <td>1040.000000</td>
      <td>0.440000</td>
      <td>1.000000</td>
      <td>0.000000</td>
      <td>-6599.980000</td>
    </tr>
    <tr>
      <th>25%</th>
      <td>2499.250000</td>
      <td>23223.000000</td>
      <td>17.280000</td>
      <td>2.000000</td>
      <td>0.000000</td>
      <td>1.730000</td>
    </tr>
    <tr>
      <th>50%</th>
      <td>4997.500000</td>
      <td>56430.500000</td>
      <td>54.490000</td>
      <td>3.000000</td>
      <td>0.200000</td>
      <td>8.665000</td>
    </tr>
    <tr>
      <th>75%</th>
      <td>7495.750000</td>
      <td>90008.000000</td>
      <td>209.940000</td>
      <td>5.000000</td>
      <td>0.200000</td>
      <td>29.360000</td>
    </tr>
    <tr>
      <th>max</th>
      <td>9994.000000</td>
      <td>99301.000000</td>
      <td>22638.480000</td>
      <td>14.000000</td>
      <td>0.800000</td>
      <td>8399.980000</td>
    </tr>
  </tbody>
</table>
</div>



## 8. Drop unnecessary columns 


```python
SalesData.columns
```




    Index(['Row ID', 'Order ID', 'Order Date', 'Ship Date', 'Ship Mode',
           'Customer ID', 'Customer Name', 'Segment', 'Country', 'City', 'State',
           'Postal Code', 'Region', 'Retail Sales People', 'Product ID',
           'Category', 'Sub-Category', 'Product Name', 'Returned', 'Sales',
           'Quantity', 'Discount', 'Profit'],
          dtype='object')




```python
SalesData = SalesData.drop(['Row ID','Order ID','Customer ID','Postal Code'],axis=1)
```


```python
SalesData.columns
```




    Index(['Order Date', 'Ship Date', 'Ship Mode', 'Customer Name', 'Segment',
           'Country', 'City', 'State', 'Region', 'Retail Sales People',
           'Product ID', 'Category', 'Sub-Category', 'Product Name', 'Returned',
           'Sales', 'Quantity', 'Discount', 'Profit'],
          dtype='object')



## Data Visualizations 

## 1. Which product category has the highest profit margin?


```python
SalesData.columns
```




    Index(['Order Date', 'Ship Date', 'Ship Mode', 'Customer Name', 'Segment',
           'Country', 'City', 'State', 'Region', 'Retail Sales People',
           'Product ID', 'Category', 'Sub-Category', 'Product Name', 'Returned',
           'Sales', 'Quantity', 'Discount', 'Profit'],
          dtype='object')




```python
import matplotlib.pyplot as plt
import seaborn as sns

category_profit=SalesData.groupby('Category')['Profit'].sum()
category_profit.plot(kind='bar')
plt.title("Profit by Category")
plt.xlabel("Category")
plt.ylabel("Total Profit")
plt.show()
# Insights: Technology is the most profitable category, followed by Office Supplies. Furniture has the lowest profit.  

```


    
![png](output_23_0.png)
    


## 2. Which region has the highest sales?


```python
SalesData.columns 
```




    Index(['Order Date', 'Ship Date', 'Ship Mode', 'Customer Name', 'Segment',
           'Country', 'City', 'State', 'Region', 'Retail Sales People',
           'Product ID', 'Category', 'Sub-Category', 'Product Name', 'Returned',
           'Sales', 'Quantity', 'Discount', 'Profit'],
          dtype='object')




```python
High_sales= SalesData.groupby('Region')['Sales'].sum()
High_sales.plot(kind="bar")
plt.title("Total Sales by Region")
plt.xlabel("Region")
plt.ylabel("Total Sales")
plt.show()
# Insights: West region has the highest total sales, followed by the East region. South region has the lowest sales. Central region performs moderately but lags behind East and West.
```


    
![png](output_26_0.png)
    


## 3. How do sales vary across different months of the year?


```python
SalesData.columns
```




    Index(['Order Date', 'Ship Date', 'Ship Mode', 'Customer Name', 'Segment',
           'Country', 'City', 'State', 'Region', 'Retail Sales People',
           'Product ID', 'Category', 'Sub-Category', 'Product Name', 'Returned',
           'Sales', 'Quantity', 'Discount', 'Profit'],
          dtype='object')




```python
SalesData['Order Month']=pd.DatetimeIndex(SalesData['Order Date']).month

month_sales= SalesData.groupby('Order Month')['Sales'].sum()
month_sales.plot(kind='line')
plt.title("Total Sales by Month")
plt.xlabel("Month")
plt.ylabel("Total Sales")
plt.show()
# Insights: Sales increase towards the end of the year, peaking in December. Fluctuations are shown throughout the year, with noticeable dips and spikes.
```


    
![png](output_29_0.png)
    


## 4. How does the return rate vary across different shipping modes?


```python
SalesData.columns
```




    Index(['Order Date', 'Ship Date', 'Ship Mode', 'Customer Name', 'Segment',
           'Country', 'City', 'State', 'Region', 'Retail Sales People',
           'Product ID', 'Category', 'Sub-Category', 'Product Name', 'Returned',
           'Sales', 'Quantity', 'Discount', 'Profit', 'Order Month'],
          dtype='object')




```python
orders_by_ship_mode= SalesData.groupby('Ship Mode').size()

returned_orders_by_ship_mode= SalesData[SalesData['Profit']<0].groupby('Ship Mode').size()

returned_per_ship_mode= (returned_orders_by_ship_mode/orders_by_ship_mode)*100
print(returned_per_ship_mode)
returned_per_ship_mode.plot(kind="bar")
plt.title("Return Per Shipping Mode")
plt.xlabel("Shipping Mode")
plt.ylabel("Return Per")
plt.show()
# Insights: Second Class shipping has the lowest return rate, indicating better customer satisfaction. Standard Class has the highest return rate and Same Day shipping shows a relatively lower return rate.

```

    Ship Mode
    First Class       19.050715
    Same Day          18.047882
    Second Class      15.784062
    Standard Class    19.654826
    dtype: float64
    


    
![png](output_32_1.png)
    


## 5. How does the company's profit vary between weekdays and weekends?


```python
SalesData.columns
```




    Index(['Order Date', 'Ship Date', 'Ship Mode', 'Customer Name', 'Segment',
           'Country', 'City', 'State', 'Region', 'Retail Sales People',
           'Product ID', 'Category', 'Sub-Category', 'Product Name', 'Returned',
           'Sales', 'Quantity', 'Discount', 'Profit', 'Order Month'],
          dtype='object')




```python
SalesData['Order Day']=pd.DatetimeIndex(SalesData['Order Date']).day_name()

day_profit= SalesData.groupby('Order Day')['Profit'].sum()
day_profit.plot(kind="bar")
plt.title("Total Profit by Day of the Week")
plt.xlabel("Day of the Week")
plt.ylabel("Total Profit")
plt.show()
# Insights: Monday and Friday show the highest profits, showing strong weekday sales. Weekends have moderate profits, but lower than peak weekdays. Wednesday has the lowest profit.
```


    
![png](output_35_0.png)
    



```python

```
