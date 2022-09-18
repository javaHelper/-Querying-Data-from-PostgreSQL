# -Querying-Data-from-PostgreSQL
 Querying Data from PostgreSQL

----

# selecting your data

```sql
select mkt_carrier, mkt_carrier_fl_num, origin from performance p ;

select mkt_carrier as airlines, 
		mkt_carrier_fl_num as flight, 
		origin as depart_city
		from performance p ;
    
select distinct mkt_carrier 
		from performance p ;  
    
select distinct mkt_carrier, origin as depart_city
		from performance p ;
```

-----

# Limiting your results

# Specific Condition

```sql
select fl_date, 
		mkt_carrier as airline,
		mkt_carrier_fl_num as flight,
		origin,
		dest 
from performance p 
where origin = 'ORD';

select fl_date, 
		mkt_carrier as airline,
		mkt_carrier_fl_num as flight,
		origin,
		dest 
from performance p 
where dest = 'ORD'
and origin = 'BZN';
```
---

# Pattern Matching

```sql
select fl_date, 
		mkt_carrier as airline,
		mkt_carrier_fl_num as flight,
		origin,
		dest 
from performance p 
where origin_city_name like 'Fort%';


select distinct origin_city_name 
from performance p 
where origin_city_name like 'Fort%';

select distinct origin_city_name 
from performance p 
where origin_city_name like '%FL';

-- Startes with New and have any number of characters in the middle

select distinct origin_city_name 
from performance p 
where origin_city_name like 'New%LA';

select distinct origin_city_name 
from performance p 
where origin_city_name like '____, KS';

select distinct origin_city_name 
from performance p 
where origin_city_name like '____, %';
```
------

# Null Values

```sql

```
