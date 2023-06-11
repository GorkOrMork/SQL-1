# Домашнее задание к занятию "SQL. Часть 1" - Вебер Сергей


### Задание 1

Получите уникальные названия районов из таблицы с адресами, которые начинаются на “K” и заканчиваются на “a” и не содержат пробелов.

select distinct district

from address

where district like 'k%a' and district not like '% %';

![image](https://github.com/GorkOrMork/SQL-1/assets/109193124/dd574034-a541-4bae-a253-a2c282d12c78)


### Задание 2

Получите из таблицы платежей за прокат фильмов информацию по платежам, которые выполнялись в промежуток с 15 июня 2005 года по 18 июня 2005 года включительно и стоимость которых превышает 10.00.

select *

from payment

where payment_date between cast('2005-06-15' as date) and cast('2005-06-19' as date)

and amount > 10;

![image](https://github.com/GorkOrMork/SQL-1/assets/109193124/20564e3f-be22-46fe-8e47-2e5aeae0cb4b)


### Задание 3

Получите последние пять аренд фильмов.

select *

from rental

order by  rental_date desc
limit 5


![image](https://github.com/GorkOrMork/SQL-1/assets/109193124/e803abf1-4fba-4221-9a58-f77dfb08116f)


### Задание 4

Одним запросом получите активных покупателей, имена которых Kelly или Willie.

Сформируйте вывод в результат таким образом:

все буквы в фамилии и имени из верхнего регистра переведите в нижний регистр,
замените буквы 'll' в именах на 'pp'.

select replace(lower( first_name), 'll', 'pp') nam, replace(lower( last_name), 'll', 'pp') , active

from customer 

where (first_name = 'Kelly' or first_name = 'Willie') and active = 1

order by nam

![image](https://github.com/GorkOrMork/SQL-1/assets/109193124/c8f819d5-3343-4065-9d1e-c4eb70550f5f)


