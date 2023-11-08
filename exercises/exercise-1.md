# Test of Caching by the database using EXPLAIN and ANALYZE

> **Create a table**

***Hint:***
- Name the table as *tbldummy*
- Add following columns
-- *id* as a primary key
-- *description* to store a long text. can be null.
-- *p_id*, *c_id*, and *entry_value* as nullable integers
-- *entry_time* as a nullable timestamp

> **Populate a large data-set in the table** 

***Hint:***
Use the following PL-SQL script to populate large dataset in above created table.
```
DO $$
DECLARE
 	random_value integer:= 1;
BEGIN
 	FOR p_id_ctr IN 1..10000 BY 1 LOOP               
		FOR c_id_ctr IN 1..200 BY 1 LOOP		 
			random_value = (( random() * 75 ) + 25);
			 
			INSERT INTO tblDummy (p_id,c_id,entry_time, entry_value, description )
			 
			VALUES (p_id_ctr,c_id_ctr,'now', random_value, CONCAT('Description for :',p_id_ctr, c_id_ctr));
		END LOOP ;
 
	END LOOP ;                      
 END $$;
```

> **Clear cache and analyse a query** 

***Hint:***
- Use *pg_stat_reset* command, to reset the cache
- Create a query to count the rows in the above table where the value of *c_id* is *1*
- Analyze above queries execution plan using *EXPLAIN* command with *ANALYZE* argument
- And, make note of the results

> **Check the blocks read from the disk**

***Hint:***
- Read* heap_blks_read* and *heap_blks_hit* from the *pg_statio_user_tables* table with *relname* as *tbldummy*


> **Once again, analyse the above query** 
> **Note results and compare with previous results**
> Also, check the blocks read from the disk
