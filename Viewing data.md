# Viewing data

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
 PassengerId  Survived  Pclass                                                 Name     Sex   Age  SibSp  Parch            Ticket     Fare Cabin Embarked
0            1       0.0       3                              Braund, Mr. Owen Harris    male  22.0      1      0         A/5 21171   7.2500   NaN        S
1            2       1.0       1  Cumings, Mrs. John Bradley (Florence Briggs Thayer)  female  38.0      1      0          PC 17599  71.2833   C85        C
2            3       1.0       3                               Heikkinen, Miss. Laina  female  26.0      0      0  STON/O2. 3101282   7.9250   NaN        S
3            4       1.0       1         Futrelle, Mrs. Jacques Heath (Lily May Peel)  female  35.0      1      0            113803  53.1000  C123        S
4            5       0.0       3                             Allen, Mr. William Henry    male  35.0      0      0            373450   8.0500   NaN        S

[5 rows x 12 columns]

## Gets statistics for the dataset
```
full_data.describe()
```

Out[13]: 
       PassengerId    Survived       Pclass          Age        SibSp        Parch         Fare
count  1309.000000  891.000000  1309.000000  1046.000000  1309.000000  1309.000000  1308.000000
mean    655.000000    0.383838     2.294882    29.881138     0.498854     0.385027    33.295479
std     378.020061    0.486592     0.837836    14.413493     1.041658     0.865560    51.758668
min       1.000000    0.000000     1.000000     0.170000     0.000000     0.000000     0.000000
25%     328.000000    0.000000     2.000000    21.000000     0.000000     0.000000     7.895800
50%     655.000000    0.000000     3.000000    28.000000     0.000000     0.000000    14.454200
75%     982.000000    1.000000     3.000000    39.000000     1.000000     0.000000    31.275000
max    1309.000000    1.000000     3.000000    80.000000     8.000000     9.000000   512.329200

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

## View the number of each value
```
full_data['Embarked'].value_counts()
```
Out[24]: 
S    916
C    270
Q    123
Name: Embarked, dtype: int64

* There are 10 columns of features, 1 column of passenger ID and 1 column of survival for training data.
* Numerical features:
   Pclass: Ticket class    1 = 1st, 2 = 2nd, 3 = 3rd <br>
   Age<br>
   Ticket: Ticket number (probably not useful)<br>
   Fare: Passenger fare<br>
   SibSp: # of siblings / spouses aboard the Titanic<br>
   Parch: # of parents / children aboard the Titanic<br>
* Object features:<br>
   Name<br>
   Sex<br>
   Cabin: Cabin number<br>
   Embarked: Port of Embarkation    C = Cherbourg, Q = Queenstown, S = Southampton<br>
   

