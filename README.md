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
select fl_date, 
		mkt_carrier as airline,
		mkt_carrier_fl_num as flight,
		cancellation_code 
from performance p 
where cancellation_code != '';


select fl_date, 
		mkt_carrier as airline,
		mkt_carrier_fl_num as flight,
		cancellation_code 
from performance p 
where cancellation_code = '';
```
----

# Joining For Future Insight

```sql
CREATE TABLE codes_cancellation
(
	cancellation_code character varying(2),
           cancel_desc character varying(45)
);

INSERT INTO codes_cancellation (cancellation_code, cancel_desc)
VALUES
	('A','Carrier'),
	('B','Weather'),
	('C','National Air System'),
	('D','Security');
	
CREATE TABLE codes_carrier
(
	carrier_code character varying(2),
	carrier_desc character varying(45)
);

INSERT INTO codes_carrier (carrier_code, carrier_desc)
VALUES
	('AA','American Airlines'),
	('AS','Alaska Airlines'),
	('B6','JetBlue Airways'),
	('DL','Delta Air Lines'),
	('F9','Frontier Airlines'),
	('G4','Allegiant Air'),
	('HA','Hawaiian Airlines'),
	('NK','Spirit Air Lines'),
	('UA','United Air Lines'),
	('VX','Virgin America'),
	('WN','Southwest Airlines');	
```
```
