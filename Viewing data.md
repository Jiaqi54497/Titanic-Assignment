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
* Dataset size
```
train.shape
```
Out[7]: (891, 12)
```
test.shape
```
Out[9]: (418, 11)

* Combine the datasets
```
full_data=train.append(test, ignore_index=True)
```
* Print the first 5 rows of data
```
full_data.head()
```
Out[12]: 
   PassengerId  Survived  Pclass  ...     Fare Cabin  Embarked
0            1       0.0       3  ...   7.2500   NaN         S
1            2       1.0       1  ...  71.2833   C85         C
2            3       1.0       3  ...   7.9250   NaN         S
3            4       1.0       1  ...  53.1000  C123         S
4            5       0.0       3  ...   8.0500   NaN         S

[5 rows x 12 columns]

* Gets statistics for the dataset
```full_data.describe()```

Out[13]: 
       PassengerId    Survived  ...        Parch         Fare
count  1309.000000  891.000000  ...  1309.000000  1308.000000
mean    655.000000    0.383838  ...     0.385027    33.295479
std     378.020061    0.486592  ...     0.865560    51.758668
min       1.000000    0.000000  ...     0.000000     0.000000
25%     328.000000    0.000000  ...     0.000000     7.895800
50%     655.000000    0.000000  ...     0.000000    14.454200
75%     982.000000    1.000000  ...     0.000000    31.275000
max    1309.000000    1.000000  ...     9.000000   512.329200

[8 rows x 7 columns]

* View the data type and total number of data for each column
