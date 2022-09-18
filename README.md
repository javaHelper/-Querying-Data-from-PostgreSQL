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

