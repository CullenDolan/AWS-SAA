## RDS
- Postgres, MySQL, MS SQL, Mariadb

## AWS Aurora

## Redshift
- 
## DynamoDB
- Key value and document db (NOSQL) which guarantees consisten reand an write at any scale
- stored across multiple regions 
- good for applications with large amounts of data but requires predictable read/write performance while scaling 
- **Eventually Consistent** by default meaning that data will be returned immediately but it might not be consistent
- You can also select **Stron Consistent Reads** meaning data won't be returned as fast but it will be consistent.


## ACID
- Atomicity: each transaction is treated as a single unit and the whole transaction will either succeed or fail and not update the db
- Consistency: Transactions can only bring dbs from one valid state to another (but does not guaruntee that the data is correct)
- Isolation: Transactions can execute concurrenlty but the db updates as if they occured sequentially
- Durability: Once transaction occurs, its stays in place even if there is a system crash or power outage
  
## SQL vs No-SQL
- No-SQL doesnt support ACID
- SQL's rigid structure reduces data duplication
- No SQL supports flexible schemas with better horizontal scaling and faster "standard queries:
