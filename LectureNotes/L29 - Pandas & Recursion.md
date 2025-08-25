# Pandas


pandas is a Python package that stores and manipulates 2-dimensional datasets. pandas is built on top of the NumPy package. pandas can be downloaded and installed from https://pandas.pydata.org/docs/getting_started/install.html. To use pandas in a program, the package is often imported with the alias pd.

pandas represents datasets with a dataframe object, of data type DataFrame, which consists of rows and columns. A dataframe's columns contain the features of the dataset and the rows contain the number of instances. Ex: In a dataset containing information about different countries, columns labeled 'Name', 'Continent', and 'Population' are the features and rows numbered 0 through 4 indicate the number of instances (number of countries in the dataset).

A dataframe's row labels are known as the index and column labels are known as the columns. Usually, row labels are automatically generated integers, and column labels are manually specified strings. All values in a column must have the same type, but different columns may have different types.



### Dataframe vs. array

A pandas DataFrame is similar to an NumPy array because both:

-    Are indexed, ordered, and mutable containers
-    Represent data in multiple dimensions, or axes
-    Have a shape attribute, a tuple of integers representing the number of elements along each axis

However, dataframes and arrays also differ in several ways:

-    Dataframes are always two-dimensional. Arrays may have zero, one, or many dimensions.
-    Different dataframe columns may have different types. All array values have the same type.
-    Dataframe labels may be integers, strings, or other types. Array indices are integers only.

Dataset features usually have string names and often have different types. For all of these reasons, datasets are usually implemented as dataframes in pandas rather than NumPy arrays.



```python
# Pandas Sample Dataframe
# Load the pandas
import pandas as pd

# Create a dataframe with pandas DataFrame() constructor
sample_df = pd.DataFrame(
   data=[ ['abc', 3.3, 28, True],
          ['xyz', -.55, 0, False] ],
   columns=['Label1', 'Label2', 'Label3', 'Label4'],
   index=[0, 1] )

# Output the dataframe
print(sample_df)

# Output the dataframe's shape
print(f'\nsample_df shape: {sample_df.shape}')

```

      Label1  Label2  Label3  Label4
    0    abc    3.30      28    True
    1    xyz   -0.55       0   False
    
    sample_df shape: (2, 4)



```python
# Pandas putting csv data into a dataframe
# /content/sample_data/california_housing_train.csv

import pandas as pd

df = pd.read_csv('/content/sample_data/california_housing_train.csv')
print(df.shape)
df.head()

```

    (17000, 9)






  <div id="df-9f56224f-e34c-482f-b8d7-1404ced85051" class="colab-df-container">
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
      <th>longitude</th>
      <th>latitude</th>
      <th>housing_median_age</th>
      <th>total_rooms</th>
      <th>total_bedrooms</th>
      <th>population</th>
      <th>households</th>
      <th>median_income</th>
      <th>median_house_value</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>-114.31</td>
      <td>34.19</td>
      <td>15.0</td>
      <td>5612.0</td>
      <td>1283.0</td>
      <td>1015.0</td>
      <td>472.0</td>
      <td>1.4936</td>
      <td>66900.0</td>
    </tr>
    <tr>
      <th>1</th>
      <td>-114.47</td>
      <td>34.40</td>
      <td>19.0</td>
      <td>7650.0</td>
      <td>1901.0</td>
      <td>1129.0</td>
      <td>463.0</td>
      <td>1.8200</td>
      <td>80100.0</td>
    </tr>
    <tr>
      <th>2</th>
      <td>-114.56</td>
      <td>33.69</td>
      <td>17.0</td>
      <td>720.0</td>
      <td>174.0</td>
      <td>333.0</td>
      <td>117.0</td>
      <td>1.6509</td>
      <td>85700.0</td>
    </tr>
    <tr>
      <th>3</th>
      <td>-114.57</td>
      <td>33.64</td>
      <td>14.0</td>
      <td>1501.0</td>
      <td>337.0</td>
      <td>515.0</td>
      <td>226.0</td>
      <td>3.1917</td>
      <td>73400.0</td>
    </tr>
    <tr>
      <th>4</th>
      <td>-114.57</td>
      <td>33.57</td>
      <td>20.0</td>
      <td>1454.0</td>
      <td>326.0</td>
      <td>624.0</td>
      <td>262.0</td>
      <td>1.9250</td>
      <td>65500.0</td>
    </tr>
  </tbody>
</table>
</div>
    <div class="colab-df-buttons">

  <div class="colab-df-container">
    <button class="colab-df-convert" onclick="convertToInteractive('df-9f56224f-e34c-482f-b8d7-1404ced85051')"
            title="Convert this dataframe to an interactive table."
            style="display:none;">

  <svg xmlns="http://www.w3.org/2000/svg" height="24px" viewBox="0 -960 960 960">
    <path d="M120-120v-720h720v720H120Zm60-500h600v-160H180v160Zm220 220h160v-160H400v160Zm0 220h160v-160H400v160ZM180-400h160v-160H180v160Zm440 0h160v-160H620v160ZM180-180h160v-160H180v160Zm440 0h160v-160H620v160Z"/>
  </svg>
    </button>

  <style>
    .colab-df-container {
      display:flex;
      gap: 12px;
    }

    .colab-df-convert {
      background-color: #E8F0FE;
      border: none;
      border-radius: 50%;
      cursor: pointer;
      display: none;
      fill: #1967D2;
      height: 32px;
      padding: 0 0 0 0;
      width: 32px;
    }

    .colab-df-convert:hover {
      background-color: #E2EBFA;
      box-shadow: 0px 1px 2px rgba(60, 64, 67, 0.3), 0px 1px 3px 1px rgba(60, 64, 67, 0.15);
      fill: #174EA6;
    }

    .colab-df-buttons div {
      margin-bottom: 4px;
    }

    [theme=dark] .colab-df-convert {
      background-color: #3B4455;
      fill: #D2E3FC;
    }

    [theme=dark] .colab-df-convert:hover {
      background-color: #434B5C;
      box-shadow: 0px 1px 3px 1px rgba(0, 0, 0, 0.15);
      filter: drop-shadow(0px 1px 2px rgba(0, 0, 0, 0.3));
      fill: #FFFFFF;
    }
  </style>

    <script>
      const buttonEl =
        document.querySelector('#df-9f56224f-e34c-482f-b8d7-1404ced85051 button.colab-df-convert');
      buttonEl.style.display =
        google.colab.kernel.accessAllowed ? 'block' : 'none';

      async function convertToInteractive(key) {
        const element = document.querySelector('#df-9f56224f-e34c-482f-b8d7-1404ced85051');
        const dataTable =
          await google.colab.kernel.invokeFunction('convertToInteractive',
                                                    [key], {});
        if (!dataTable) return;

        const docLinkHtml = 'Like what you see? Visit the ' +
          '<a target="_blank" href=https://colab.research.google.com/notebooks/data_table.ipynb>data table notebook</a>'
          + ' to learn more about interactive tables.';
        element.innerHTML = '';
        dataTable['output_type'] = 'display_data';
        await google.colab.output.renderOutput(dataTable, element);
        const docLink = document.createElement('div');
        docLink.innerHTML = docLinkHtml;
        element.appendChild(docLink);
      }
    </script>
  </div>


    <div id="df-27aead98-339b-4dbc-a252-9ae85fb17cee">
      <button class="colab-df-quickchart" onclick="quickchart('df-27aead98-339b-4dbc-a252-9ae85fb17cee')"
                title="Suggest charts"
                style="display:none;">

<svg xmlns="http://www.w3.org/2000/svg" height="24px"viewBox="0 0 24 24"
     width="24px">
    <g>
        <path d="M19 3H5c-1.1 0-2 .9-2 2v14c0 1.1.9 2 2 2h14c1.1 0 2-.9 2-2V5c0-1.1-.9-2-2-2zM9 17H7v-7h2v7zm4 0h-2V7h2v10zm4 0h-2v-4h2v4z"/>
    </g>
</svg>
      </button>

<style>
  .colab-df-quickchart {
      --bg-color: #E8F0FE;
      --fill-color: #1967D2;
      --hover-bg-color: #E2EBFA;
      --hover-fill-color: #174EA6;
      --disabled-fill-color: #AAA;
      --disabled-bg-color: #DDD;
  }

  [theme=dark] .colab-df-quickchart {
      --bg-color: #3B4455;
      --fill-color: #D2E3FC;
      --hover-bg-color: #434B5C;
      --hover-fill-color: #FFFFFF;
      --disabled-bg-color: #3B4455;
      --disabled-fill-color: #666;
  }

  .colab-df-quickchart {
    background-color: var(--bg-color);
    border: none;
    border-radius: 50%;
    cursor: pointer;
    display: none;
    fill: var(--fill-color);
    height: 32px;
    padding: 0;
    width: 32px;
  }

  .colab-df-quickchart:hover {
    background-color: var(--hover-bg-color);
    box-shadow: 0 1px 2px rgba(60, 64, 67, 0.3), 0 1px 3px 1px rgba(60, 64, 67, 0.15);
    fill: var(--button-hover-fill-color);
  }

  .colab-df-quickchart-complete:disabled,
  .colab-df-quickchart-complete:disabled:hover {
    background-color: var(--disabled-bg-color);
    fill: var(--disabled-fill-color);
    box-shadow: none;
  }

  .colab-df-spinner {
    border: 2px solid var(--fill-color);
    border-color: transparent;
    border-bottom-color: var(--fill-color);
    animation:
      spin 1s steps(1) infinite;
  }

  @keyframes spin {
    0% {
      border-color: transparent;
      border-bottom-color: var(--fill-color);
      border-left-color: var(--fill-color);
    }
    20% {
      border-color: transparent;
      border-left-color: var(--fill-color);
      border-top-color: var(--fill-color);
    }
    30% {
      border-color: transparent;
      border-left-color: var(--fill-color);
      border-top-color: var(--fill-color);
      border-right-color: var(--fill-color);
    }
    40% {
      border-color: transparent;
      border-right-color: var(--fill-color);
      border-top-color: var(--fill-color);
    }
    60% {
      border-color: transparent;
      border-right-color: var(--fill-color);
    }
    80% {
      border-color: transparent;
      border-right-color: var(--fill-color);
      border-bottom-color: var(--fill-color);
    }
    90% {
      border-color: transparent;
      border-bottom-color: var(--fill-color);
    }
  }
</style>

      <script>
        async function quickchart(key) {
          const quickchartButtonEl =
            document.querySelector('#' + key + ' button');
          quickchartButtonEl.disabled = true;  // To prevent multiple clicks.
          quickchartButtonEl.classList.add('colab-df-spinner');
          try {
            const charts = await google.colab.kernel.invokeFunction(
                'suggestCharts', [key], {});
          } catch (error) {
            console.error('Error during call to suggestCharts:', error);
          }
          quickchartButtonEl.classList.remove('colab-df-spinner');
          quickchartButtonEl.classList.add('colab-df-quickchart-complete');
        }
        (() => {
          let quickchartButtonEl =
            document.querySelector('#df-27aead98-339b-4dbc-a252-9ae85fb17cee button');
          quickchartButtonEl.style.display =
            google.colab.kernel.accessAllowed ? 'block' : 'none';
        })();
      </script>
    </div>

    </div>
  </div>





```python
# Example Accessing data in dataframes
import pandas as pd

df = pd.read_csv('/content/sample_data/california_housing_train.csv')

print('List of latitudes in dataframe. The latitude column')
print(df['latitude'])


print('\n\nList of the total rooms data. The total_rooms column')
print(df['total_rooms'])


# Example find all housing data rows where
# the housing median age is less than or equal to 15.0
print('\n\nFinding rows that contain data for median age less than 15.0')
print(df[df['housing_median_age'] <= 15.0], '\n')


```

    List of latitudes in dataframe. The latitude column
    0        34.19
    1        34.40
    2        33.69
    3        33.64
    4        33.57
             ...  
    16995    40.58
    16996    40.69
    16997    41.84
    16998    41.80
    16999    40.54
    Name: latitude, Length: 17000, dtype: float64
    
    
    List of the total rooms data. The total_rooms column
    0        5612.0
    1        7650.0
    2         720.0
    3        1501.0
    4        1454.0
              ...  
    16995    2217.0
    16996    2349.0
    16997    2677.0
    16998    2672.0
    16999    1820.0
    Name: total_rooms, Length: 17000, dtype: float64
    
    
    Finding rows that contain data for median age less than 15.0
           longitude  latitude  housing_median_age  total_rooms  total_bedrooms  \
    0        -114.31     34.19                15.0       5612.0          1283.0   
    3        -114.57     33.64                14.0       1501.0           337.0   
    14       -114.63     32.76                15.0       1448.0           378.0   
    23       -114.98     33.82                15.0        644.0           129.0   
    27       -115.37     32.82                14.0       1276.0           270.0   
    ...          ...       ...                 ...          ...             ...   
    16914    -124.09     40.92                12.0       2497.0           491.0   
    16957    -124.16     41.74                15.0       2715.0           569.0   
    16976    -124.17     40.75                13.0       2171.0           339.0   
    16983    -124.19     41.78                15.0       3140.0           714.0   
    16991    -124.23     41.75                11.0       3159.0           616.0   
    
           population  households  median_income  median_house_value  
    0          1015.0       472.0         1.4936             66900.0  
    3           515.0       226.0         3.1917             73400.0  
    14          949.0       300.0         0.8585             45000.0  
    23          137.0        52.0         3.2097             71300.0  
    27          867.0       261.0         1.9375             80900.0  
    ...           ...         ...            ...                 ...  
    16914      1153.0       462.0         2.8182            126900.0  
    16957      1532.0       530.0         2.1829             69500.0  
    16976       951.0       353.0         4.8516            116100.0  
    16983      1645.0       640.0         1.6654             74600.0  
    16991      1343.0       479.0         2.4805             73200.0  
    
    [2725 rows x 9 columns] 
    


# Recursion
This is when a function calls itself


```python
# First recursion Example
# Build a function that prints all integers from n to 0. The function is
# the integer n. n is guaranteed to be postive. the prints should all be on the
# same row. Ingegers are separated by spaces

# normal python function
def Countdown(n):
  for i in range(n,-1, -1):
    print(i, end = ' ')
# recursion function
def Countdown2(n):
  if n == 0:
    print(0)
    return
  else:
    print(n, end = ' ')
    Countdown2(n-1)


if __name__ == '__main__':
  print('Normal Python Function:')
  Countdown(3)
  print('\nRecursion:')
  Countdown2(3)




```

    Normal Python Function:
    3 2 1 0 
    Recursion:
    3 2 1 0



```python
# factorial using normal python code
def Factorial1(n):
  result = 1
  for i in range(2,n+1):
    result *= i
  return result
  '''
    if n==0:
      return 1
    result = n
    while n > 1:
      n -= 1
      result *= n
    return result
  '''

print(Factorial1(3))
print(Factorial1(4))
print(Factorial1(5))
print(Factorial1(0))
```

    6
    24
    120
    1



```python
# Factorial using recursion
def Factorial2(n):
  if n == 0 or n==1:
    return 1
  return n*Factorial2(n-1)
  # if n is 3
  # return 3 * Factorial(3-1)
  #            2 * Factorial(2-1)
  #                1
  # putting all together 3*2*1

print(Factorial2(3))

```

# Fib numbers
# 0,1,1,2,3,5,8,13,21


```python
def fib(n):
  if n == 0:
    return 0
  if n == 1:
    return 1
  return fib(n-1) + fib(n-2)

for i in range(10):
  print(fib(i))

```

    0
    1
    1
    2
    3
    5
    8
    13
    21
    34


# Extra Time in the Lecture - Hints on Final Project Problems




```python

```
