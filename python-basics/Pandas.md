# It is introduction to Pandas 🐼
[Click](https://skillbox.ru/media/code/rabotaem-s-pandas-osnovnye-ponyatiya-i-realnye-dannye/)
## Use
    import pandas as pd
## Series

***Series***-it is object, which look simillar on one-demission array and can have any datas

```
    pd.Series(list)
```

Output:

```
    0  4
    1  7
    2 -5 
    3  3
    dtype: int64
```
## DataFrame

***DataFrame***-basic dtype in Pandas, it can be just table with any count of row and col. It have index row, col.

```
    import pandas as pd # Импортируем библиотеку Pandas.

    city = {'Город': ['Москва', 'Санкт-Петербург', 'Новосибирск', 'Екатеринбург'],
        'Год основания': [1147, 1703, 1893, 1723], 
        'Население': [11.9, 4.9, 1.5, 1.4]} # Создаём словарь с нужной информацией о городах.

    df = pd.DataFrame(city) # Превращаем словарь в DataFrame, используя стандартный метод         библиотеки.

    df # Выводим DataFrame на экран.
```
Output:
![Output2](https://github.com/nrzgit/learning-notes/blob/3aab3497ea6e59d6f10964a4ff628e280f756f0b/python-basics/%D0%A1%D0%BD%D0%B8%D0%BC%D0%BE%D0%BA%20%D1%8D%D0%BA%D1%80%D0%B0%D0%BD%D0%B0%202025-09-14%20000459.png)

## Data import

Most popular cause - work with `.csv`. Import command: `pd.read_csv()`
`read_csv` settings:
+`sep`, `,` basic
+`dtype` datatype in col
```
df = pd.read_csv('/content/Internet Speed 2022.csv')
```

***df.head(), df.tail()***-print first 5 and last 5, 5 basic

***df.dtypes()***-print dtype of csv
`object`-string and mixed types

***df.describe()***-print:  
+`count`-it filled row in each col  
+`mean`-it avarage value  
+`std`-standart deviation  
+`min` and `max`  
+`25%`, `50%`, `70%`-percentile  

***df.sort_values(name of col, ascending=(from big to small - False, from small to big - True))***

`NaN` - no datas

***df.dropna()***-delete rows which fill NaN

***df.shape()**-return count of rows and cols

***df.columns***-return names of cols

***df.head(count)***-output first count of df

***df.loc(row[it can be name of row col], return value)***-one of the primary ways to select data from a DataFrame. It is label-based, which means you have to specify the name of the rows or columns to select data. loc is label-based.

```students.loc[students['student_id'] == 101, ['name', 'age']]```

Output:

name	| age

Ulysses	 | 13

***df[name of col]** - to contact with col 

```employees['bonus'] = employees['salary'] * 2``` - adding new col with value

***df..drop_duplicates()***-remove duplicate rows from a DataFrame.  
    Certain columns: **df.drop_duplicates(subset=[name of col])**.  
    **Keep**: df.drop_duplicates(keep='last'). 'last'-delete last duplicate, 'first'-first duplicate, "False"-drop all items  
    ***df.drop_duplicates(inplace=True)***

***df.dropna()***-axis: axis=0 -> drop rows(default), axis=1 -> drop cols.  
**df.dropna(how='all')**-Drop rows only if all values are missing.  
**df.dropna(subset=['A'])**-Drop rows if certain columns have missing values.  
**df.dropna(inplace=True)**-Drop missing values in place.  
**df_clean = df.dropna(thresh=2)**-You can specify a threshold of non-null values required to keep a row:


***df.fillna()***-replace missing values (NaN or None).  
```df_ffill = df.fillna(method='ffill')```-This fills missing values with the previous non-null value in the column.  
```df_bfill = df.fillna(method='bfill')```-This fills missing values with the next non-null value.
```df.fillna(method='ffill', limit=1)```-→ Only fills one consecutive NaN per column.
```
df['A'] = df['A'].fillna(df['A'].mean())   # mean
# or
df['A'] = df['A'].fillna(df['A'].median()) # median
# or
df['A'] = df['A'].fillna(df['A'].mode()[0]) # mode
```

***df.rename(columns={'A': 'B', 'D': 'C'})***
***df_renamed = df.rename(index={0: 'first', 1: 'second'})***  
```
# Add prefix to all column names
df = df.rename(columns=lambda x: 'col_' + x)

# Uppercase all column names
df = df.rename(columns=str.upper)
```
```
df.columns = ['X', 'Y']  # direct assignment
# or equivalently
df = df.set_axis(['X', 'Y'], axis=1)
```
