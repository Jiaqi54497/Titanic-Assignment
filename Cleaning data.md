# Cleaning data

### Columns with missing values:
*   Age: missing 1309-1046=263
*   Fare: missing 1
*   Embarked: missing 2
*   Cabin: missing 1309-295=1014

## Filling empty value
For age and fare, fill with the average value
```
full_data['Age'] = full_data['Age'].fillna(full_data['Age'].mean())
full_data['Fare'] = full_data['Fare'].fillna(full_data['Fare'].mean())
```
For 'Embarked', fill with the majority (see .value_counts() in Viewing_data.md)
```
full_data['Embarked'] = full_data['Embarked'].fillna('S')
full_data['Cabin'] = full_data['Cabin'].fillna('U')
```
