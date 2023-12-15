# Домашнее задание к занятию "SQL. Часть 2 - `Согонов Алексей`"

### Задание 1

```

select concat(s2.first_name, ' ', s2.last_name) as 'name', c.city, count(c2.store_id) as 'number of users'
from store s 
join staff s2 on s2.staff_id = s.manager_staff_id 
join address a on a.address_id = s.address_id 
join city c on c.city_id = a.city_id 
join customer c2 on c2.store_id = s.store_id 
group by s2.staff_id;

```

### Задание 2

```

select count(1)
from film
where length > (select avg(length) from film);

```

### Задание 3

```

select date_format(payment_date, '%M-%Y') as 'month', count(r.rental_id) as 'number of rentals'
from payment p
join rental r on r.rental_id = p.rental_id 
group by date_format(payment_date, '%M-%Y')
order by sum(amount) desc 
limit 1;

```

---
