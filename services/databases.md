## RDS
- Postgres, MySQL, MS SQL, Mariadb, Oracle, Aurora
- Multi-AZ is an option and good for High Availability
- Data is automatically synced and will also automatically failover if master goes down
- Read replicas are good for distributing read operations but only the master will get writes
- Automatic backup must be enabled to get read replicas and there can be up to **5** read replicas
- Read replicas can also be put in other regions
- Replica can be promoted to their own master db but it will break replication
- backup data with Automated backup or manual snapshots
- the snapshot can be used to create a new db if the original master fails, but you then have to delete the old master and route traffic to the new db

## AWS Aurora
- Fully managed Postgres or MySQL instances but stated to be much faster than standard Postgres or MySQL
- default is to replicat 6 copies of db over 3 AZs
- can span multiple regions with **Aurora Global Database**
- Aurora Serverless allows start, stop, and autoscaling. and ideal for new/test projects

## Redshift
- Fully managed data warehouse w/ columnar store db (OLAP)
- managed by specifying number of nodes to run
- attempts to maintain 3 copies of the data 

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
- No-SQL supports flexible schemas with better horizontal scaling and faster "standard queries"
