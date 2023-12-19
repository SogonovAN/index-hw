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

Limit: 200 row(s)  (cost=0..0 rows=0) (actual time=13985..13985 rows=200 loops=1)
Table scan on <temporary>  (cost=2.5..2.5 rows=0) (actual time=13985..13985 rows=200 loops=1)
Temporary table with deduplication  (cost=0..0 rows=0) (actual time=13985..13985 rows=391 loops=1)
Single-row index lookup on c using PRIMARY (customer_id=r.customer_id)  (cost=250e-6 rows=1) (actual time=406e-6..440e-6 rows=1 loops=642000)
-> Single-row covering index lookup on i using PRIMARY (inventory_id=r.inventory_id)  (cost=250e-6 rows=1) (actual time=279e-6..315e-6 rows=1 loops=642000)

Оптимизация:

create index lang_year on payment(payment_date);

select distinct concat(c.last_name, ' ', c.first_name), sum(p.amount) over (partition by c.customer_id)
from payment p, rental r, customer c, film f
where date(p.payment_date) = '2005-07-30' and p.payment_date = r.rental_date and r.customer_id = c.customer_id;;

```

---
