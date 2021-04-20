# Feature Extraction

### Sex
```
sex_mapDic = {'male':1, 'female':0}
full_data['Sex'] = full_data['Sex'].map(sex_mapDic)
```
### Embarked and pclass
There is no significance of magnitude between the values of discrete features, so One-Hot coding is used
```
Em_df = pd.get_dummies(full_data['Embarked'], prefix = 'Embarked')
full_data = pd.concat([full_data, Em_df], axis = 1)
full_data.drop('Embarked', axis = 1, inplace = True)

pclass_df = pd.get_dummies(full_data['pclass'], prefix = 'pclass')
full_data = pd.concat([full_data, pclass_df], axis = 1)
full_data.drop('pclass', axis = 1, inplace = True)
```
### Name
The title included in 'Name' can be used as a feature.

