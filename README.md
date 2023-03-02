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
