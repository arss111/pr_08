# pr_08
## Цель:
определить наиболее эффективный метод загрузки данных (малых и больших объемов) из CSV-файлов в СУБД PostgreSQL, сравнивая время выполнения для методов: pandas.to_sql(), psycopg2.copy_expert() (с файлом и с io.StringIO), и пакетная вставка (psycopg2.extras.execute_values).

## Ход работы:
1.	Загрузим необходимые библиотеки
 ![image](https://github.com/user-attachments/assets/e353e07a-cf07-43ea-8f25-fbbe739dd140)

Подключимся к с заранее созданной базе данных, загрузим фрагменты файлов
 ![image](https://github.com/user-attachments/assets/604f5aea-0ee7-4dcc-9f14-3cf509bce48b)

Далее проведем анализ скорости загрузки данных разными способами, заметим, что загрузка при помощи библиотеки pandas является самым медленным вариантом, это же видно на визуализации: 
 
![image](https://github.com/user-attachments/assets/7ea7785c-0478-476d-af47-263e1cfc2343)
![image](https://github.com/user-attachments/assets/24b547ba-2a21-492a-93b8-b5bae1195a0b)


## Индивидуальные задания. Вариант 15
Определяем вспомогательные функции
![image](https://github.com/user-attachments/assets/cf5e0c65-80b9-477c-8e13-e9261716aca2)

 
Переходим к решению индивидуальных заданий:
1.	Создать таблицы sales_small, sales_big.
![image](https://github.com/user-attachments/assets/1d507e5d-db52-4c33-801e-819006720349)
![image](https://github.com/user-attachments/assets/e8818c18-b32d-4f28-a560-86fb8e0ff91b)

 
Посмотрим ERD-диаграммы:

  ![image](https://github.com/user-attachments/assets/a9de3681-144f-4467-9b3e-ad770f8d8840)
  
  ![image](https://github.com/user-attachments/assets/f36f3563-c4c3-4e2d-816d-402d78be3ebb)


2.	Метод: copy_expert (StringIO) для малых данных
 
![image](https://github.com/user-attachments/assets/0110d61e-9e95-4695-8331-c999370f2e21)

3.	Метод: copy_expert (file) для больших данных
   
 ![image](https://github.com/user-attachments/assets/d870d59b-8006-44d7-908d-b44d35654164)


4.	SQL: вычислить суммарную total_revenue в sales_small, где quantity < 10.

![image](https://github.com/user-attachments/assets/7baf5cde-d775-4aca-8780-7002d6ce2f99)

![image](https://github.com/user-attachments/assets/72ebbd25-4512-4f0d-a35a-c3510a83f991)

Посмотрим результат путем копирования результата запроса: (Decimal('4724.49'),)


5.	Python: Рассчитать корреляцию cost и total_revenue в DataFrame sales_small.
 
 ![image](https://github.com/user-attachments/assets/2e11dfd4-2d67-4269-8d55-ccc99c503a53)

 ![image](https://github.com/user-attachments/assets/72861a89-474f-4890-bf5a-aa1dcda6ce27)

## Вывод:
в ходе работы были проанализированы и выявлены самые эффективные способы загрузки данных разных размеров, их экспорт и импорт, также были решены все поставленные задачи и создана визуализация с использованием библиотеки matplotlib.pyplot

