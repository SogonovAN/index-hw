# Домашнее задание к занятию "Индексы - `Согонов Алексей`"

### Задание 1

```

SELECT  sum(index_length) / sum(data_length) * 100 'процентное отношение'
FROM INFORMATION_SCHEMA.TABLES
WHERE table_schema = 'sakila';

```

### Задание 2

```

Узкие места:

перебираение всех строк таблицы, отсутствие индексов, некорректное присоединение таблиц, которые увеличивает время обработки запроса
(partition by c.customer_id, f.title)
ненужные таблицы f.title, film f

Оптимизация:

create index lang_year on payment(payment_date);

select distinct concat(c.last_name, ' ', c.first_name), sum(p.amount)
from customer c 
join rental r on r.customer_id = c.customer_id
join payment p on p.payment_date = r.rental_date 
join inventory i on i.inventory_id = r.inventory_id 
where p.payment_date >= '2005-07-30' and date_add('2005-07-30', interval 1 day) and p.payment_date = r.rental_date and r.customer_id = c.customer_id and i.inventory_id = r.inventory_id
group by concat(c.last_name, ' ', c.first_name);

```
![Название скриншота 1](https://github.com/SogonovAN/index-hw/blob/main/2.JPG)`

---
