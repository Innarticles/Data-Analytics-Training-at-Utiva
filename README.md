# Data-Analytics-Training-at-Utiva
Training Resources and Links 
[Slides](https://docs.google.com/presentation/d/1hveKHs6rw_eU9p7Hia77B0RfjHOQiRhozguMjdvtb7o/edit?usp=sharing)

## SQL Installations (Postgres)
- Windows - https://www.enterprisedb.com/downloads/postgres-postgresql-downloads
- Mac OS - https://www.enterprisedb.com/downloads/postgres-postgresql-downloads
- Ubuntu - https://www.postgresql.org/download/linux/ubuntu/
- Others - https://www.postgresql.org/download/

## Sample Datasets 
- Film Business Data [Click to download](https://www.postgresqltutorial.com/wp-content/uploads/2019/05/dvdrental.zip)
- Extract to .tar file 
- Using PgAdmin, create a database and restore the database by pointing to the .tar file (dvdrental.tar)

## Practise online
- https://www.w3resource.com/sql-exercises/

## Instructions on getting updates for on this page
- Watch and Follow this repository (Click on the Watch and Star button at the top right corner of this page). This will enable you get email notification once there is a new update.

## Sample Tables Demostrating types of SQL Joins
```
CREATE TABLE basket_a (
    id INT PRIMARY KEY,
    fruit VARCHAR (100) NOT NULL
);
 
CREATE TABLE basket_b (
    id INT PRIMARY KEY,
    fruit VARCHAR (100) NOT NULL
);
 
INSERT INTO basket_a (id, fruit)
VALUES
    (1, 'Apple'),
    (2, 'Orange'),
    (3, 'Banana'),
    (4, 'Cucumber');
   
 
INSERT INTO basket_b (id, fruit)
VALUES
    (1, 'Orange'),
    (2, 'Apple'),
    (3, 'Watermelon'),
    (4, 'Pear');
```

## Update on in-class exercise on using `WHERE IN ()` with `INNER JOIN` 
Proposed Solution that failed
```
SELECT 
 *
FROM 
 customer
INNER JOIN payment on (payment.customer_id = customer.customer_id)
WHERE payment.customer_id IN (
	SELECT 
	Distinct payment.customer_id
	FROM payment
	WHERE payment.amount > 5.0
);
```
Working Solution - Even simpler!!
```

SELECT 
	*
FROM 
 customer
INNER JOIN payment on (payment.customer_id = customer.customer_id)
WHERE payment.amount > 5.0

```
