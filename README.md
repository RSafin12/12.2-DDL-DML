# 12.2.-DDL-DML

## Задание 1

#### Создаем учетную запись
`create user 'sys_temp'@'%' identified by 'netpass0';`

#### Делаем запрос на получение списко пользователей
`SELECT host, user FROM mysql.user;`
![user list](https://github.com/RSafin12/12.2-DDL-DML/blob/main/2.png)

#### Выдаем пользователю God_mode
`GRANT ALL PRIVILEGES ON *.* TO 'sys_temp'@'%' WITH GRANT OPTION;`

#### Снова делаем запрос
`show grants for 'sys_temp'@'%';`
![show grants](https://github.com/RSafin12/12.2-DDL-DML/blob/main/3.png)

#### Меняем тип аутентификации
`ALTER USER 'sys_temp'@'%' IDENTIFIED WITH mysql_native_password BY 'netpass0';`
![auth_changed](https://github.com/RSafin12/12.2-DDL-DML/blob/main/4.png)

#### ER-диаграмма
![ER-diagram](https://github.com/RSafin12/12.2-DDL-DML/blob/main/5.png)

## Задание 2
Запрос на получение первичного ключа
```
SELECT k.column_name
FROM information_schema.table_constraints t
JOIN information_schema.key_column_usage k
USING(constraint_name,table_schema,table_name)
WHERE t.constraint_type='PRIMARY KEY'
AND t.table_schema='sakila'
```
Название таблицы | Название первичного ключа
actor	           |	actor_id
address	         |	address_id
category	       |	category_id
city	           |	city_id
country	         |	country_id
customer	       |	customer_id
film	           |	film_id
film_actor	     |	film_id + actor_id
film_category	   |	film_id + category_id
film_text	       |	film_id
inventory	       |	inventory_id
language	       |	language_id
payment	         |	payment_id
rental	         |	rental_id
staff	           |	staff_id
store	           |	store_id
