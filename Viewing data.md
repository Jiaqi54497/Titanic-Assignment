* Import library

```
import pandas as pd
import numpy as np
```

* Read data
```
train = pd.read_csv("train.csv")
test = pd.read_csv("test.csv")
```
* Check what kind of data this is, and what I need to do about it

* Checking dataset
## Dataset size
```
train.shape
```
Out[7]: (891, 12)
```
test.shape
```
Out[9]: (418, 11)

## Combine the datasets
```
full_data=train.append(test, ignore_index=True)
```
## Print the first 5 rows of data
```
full_data.head()
```
Out[12]: 
   PassengerId  Survived  Pclass  ...     Fare Cabin  Embarked<br>
0            1       0.0       3  ...   7.2500   NaN         S<br>
1            2       1.0       1  ...  71.2833   C85         C<br>
2            3       1.0       3  ...   7.9250   NaN         S<br>
3            4       1.0       1  ...  53.1000  C123         S<br>
4            5       0.0       3  ...   8.0500   NaN         S<br>

[5 rows x 12 columns]

## Gets statistics for the dataset
```
full_data.describe()
```

Out[13]: 
       PassengerId    Survived  ...        Parch         Fare<br>
count  1309.000000  891.000000  ...  1309.000000  1308.000000<br>
mean    655.000000    0.383838  ...     0.385027    33.295479<br>
std     378.020061    0.486592  ...     0.865560    51.758668<br>
min       1.000000    0.000000  ...     0.000000     0.000000<br>
25%     328.000000    0.000000  ...     0.000000     7.895800<br>
50%     655.000000    0.000000  ...     0.000000    14.454200<br>
75%     982.000000    1.000000  ...     0.000000    31.275000<br>
max    1309.000000    1.000000  ...     9.000000   512.329200<br>

[8 rows x 7 columns]

## View the data type and total number of data for each column
```
full_data.info()
```
<class 'pandas.core.frame.DataFrame'>
RangeIndex: 1309 entries, 0 to 1308
Data columns (total 12 columns):
    Column       Non-Null Count  Dtype  <br>
---  ------       --------------  -----  <br>
 0   PassengerId  1309 non-null   int64  <br>
 1   Survived     891 non-null    float64<br>
 2   Pclass       1309 non-null   int64  <br>
 3   Name         1309 non-null   object <br>
 4   Sex          1309 non-null   object <br>
 5   Age          1046 non-null   float64<br>
 6   SibSp        1309 non-null   int64  <br>
 7   Parch        1309 non-null   int64  <br>
 8   Ticket       1309 non-null   object <br>
 9   Fare         1308 non-null   float64<br>
 10  Cabin        295 non-null    object <br>
 11  Embarked     1307 non-null   object <br>
dtypes: float64(3), int64(4), object(5)  <br>
memory usage: 122.8+ KB


