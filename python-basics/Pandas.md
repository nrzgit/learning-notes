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
