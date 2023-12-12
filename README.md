# Домашнее задание к занятию "SQL. Часть 1 - `Согонов Алексей`"

### Задание 1

```

select distinct district 
from address a 
where district like 'K%a'and district not like '% %';

```

### Задание 2

```

select payment_id, amount, cast(payment_date as DATE) 
from payment p 
where amount > 10 and payment_date between '2005-06-15 00:00:01' and '2005-06-18 23:59:59';

```

### Задание 3

```

select *
from rental r 
order by rental_date desc
limit 5;

```


### Задание 4

```

select lower(first_name), lower(last_name), replace(first_name, 'LL', 'PP')
from customer c 
where active > 0 and first_name like 'Kelly' or first_name like 'Willie';


```
---
