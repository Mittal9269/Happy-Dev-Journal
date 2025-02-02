# Database internal book learnings

## storage engine & DBMS
we assume DBMS as a service on top of storage engine which provide more capability like concurrency support, indexing, transactional rollback, upsert etc.. while storage engine is just a basic engine which does upate, get delete operation on database.
![Alt text](../../../images/Stoage_engine_and_DBMS.jpg?raw=true)


## database comparision key requirement points
- schema & record size for the application 
- Number of clients which will hit the DB
- Type of quires & access patterns 
- Rate of the read & write quired, along with throughput difference in both
- Expected changes rate in any of above mentioned variable 
- version upgrade requirement rate


## Trade-off while chosing DBMS
- How the data is going to be Garbage collected
- How storage engine fits into the sementics of the database system 
- we should never lose any data in any condition 


### Categories of DBMS type
- Online transaction processing databases (OLTP) :- Handles most of the user-facing request & transactions. Short lived & mostly predefined quires.
- Online analysis processing databases (OLAP) :- handles complex aggregation. Mostly used for analytics & data warehousing. Long lived quires.
- Hybrid transaction & analytical processing database (HTAP) :- combine properties of both OLTP & OLAP. (TiDB, AlloyDB are some examples)


## Architecture of DBMS
![Alt text](../../../images/DBMS_Architecture.png)

