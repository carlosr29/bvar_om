# BVAR



### Рабочая цепочка:


1. Скачиваем данные

2. Удаляем сезонность в Eviews. 

На выходе:

- `/data/adjusted_data_x.xlsx`

3. Устанавливаем необходимые пакеты R, запускаем `/R/100_install_packages.R`

4. Делаем перевод данных в R, запускаем `/R/200_load_after_eviews.R`.

На входе: 

- `/data/adjusted_data_x.xlsx`

На выходе:

- `/data/df_2015_final.csv`, Отфильтованы данные начиная с 1995 года, взяты логарифмы
    
- `/data/data_2015_after_eviews.csv`, Просто конверт исходного `xlsx`-файла
  
5. 


### Нерабочие цепочки

#### Попытка удалять сезонность в R

1. Переводим данные из Excel в R: `/R/200_load.R`

На входе: 

- `data/data_bvar_2015.xlsx`

На выходе:

- `/data/data_2015.csv`

2. Удаляем сезонность в R `/R/300_clean.R`:

На входе:

- `/data/data_2015.csv`

На выходе:

- `/data/df_2015_final.csv`

- `/data/df_2015_sa.csv`


#### Для загрузки ряда gas на www.seasonal.website

1. Отбираем нужное, `R/301_gas_problem.R`

На входе:

- `/data/data_2015.csv`

На выходе:

- `/data/gas_only.csv`

#### Попытка сравнения с carriero

1. Оцениваем нашим способом. Похоже параметры не те, `/R/350_matlab_carriero_test.R`

На входе:

- `/data/usa_data.mat`

