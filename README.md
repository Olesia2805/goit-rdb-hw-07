# goit-rdb-hw-07

## Task 1
**Write a SQL query that retrieves the year, month, and day from the `date` attribute for the `orders` table. Display them in three separate attributes: the `id` attribute and the original `date` attribute (5 attributes in total).**

```sql
SELECT id,
       date,
       YEAR(date) AS year,
       MONTH(date) AS month,
       DAY(date) AS day
FROM orders;
```

---

## Task 2
**Write an SQL query that adds one day to the `date` attribute for the `orders` table. Display the `id` attribute, the original `date` attribute, and the addition result.**

```sql
SELECT id,
       date,
       date + INTERVAL 1 DAY AS datetime_plus
FROM orders;
```

```sql
SELECT id,
       date,
       DATE_ADD(date, INTERVAL 1 DAY) AS datetime_plus
FROM orders;
```

---

## Task 3
**Write an SQL query that displays the number of seconds from the beginning of the countdown for the `orders` table for the `date` attribute (shows its timestamp value). To do this, find and apply the necessary function. Display the `id` attribute, the original `date` attribute, and the result of the function.**

```sql
SELECT id,
       date,
       UNIX_TIMESTAMP(date) AS timestamp
FROM orders;
```

---

## Task 4
**Write a SQL query that counts the number of rows in the `orders` table with the `date` attribute between `1996-07-10 00:00:00` and `1996-10-08 00:00:00`.**

```sql
SELECT COUNT(date) AS days_between
FROM orders
WHERE date BETWEEN '1996-07-10 00:00:00' AND '1996-10-08 00:00:00';
```

---
