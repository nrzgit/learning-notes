# It is introduction to Pandas 🐼
[Click](https://skillbox.ru/media/code/rabotaem-s-pandas-osnovnye-ponyatiya-i-realnye-dannye/)
## Use
    import pandas as pd
## Series
It is object, which look simillar on one-demission array and can have any datas
---
    pd.Series(list)
---
 Output:
---
    0  4
    1  7
    2 -5 
    3  3
    dtype: int64
---
## DataFrame
Basic dtype in Pandas, it can be just table with any count of row and col. It have index row, col.
---
    import pandas as pd # Импортируем библиотеку Pandas.

    city = {'Город': ['Москва', 'Санкт-Петербург', 'Новосибирск', 'Екатеринбург'],
        'Год основания': [1147, 1703, 1893, 1723], 
        'Население': [11.9, 4.9, 1.5, 1.4]} # Создаём словарь с нужной информацией о городах.

    df = pd.DataFrame(city) # Превращаем словарь в DataFrame, используя стандартный метод         библиотеки.

    df # Выводим DataFrame на экран.
---
