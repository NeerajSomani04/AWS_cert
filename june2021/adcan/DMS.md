# Database Migration Service (DMS)
- **Its very imp for exam**
- It helps you migrate databases to AWS quickly and securely.
- The source database remains fully operational during the migration, minimizing downtime to applications that rely on the database. 
- Its a managed database migration service
- runs using a replication instance (EC2), this instance can run one or more replication tasks
- configuration requires you to define source and destination endpoints which points to source and target databases
- only one condition, one of the endpoint must be running on AWS
- This service can't be used if all of your DBs are outside AWS, atleast one should be in AWS
- replication tasks types
  - full load
    - meaning, migration of all data
    - this includes creation of schema, tables, and moving all data
  - full load + CDC (change data capture)
    - move all existing data + any ongoing replication which captures changes
  - CDC only
    - this is applicable when there is requirement to use bulk DB migration using some other service
    - and you only want to handle this service for CDC activities
- **exam imp** SCT (Schema conversion tool) - can assist with schema conversion
  - **exam imp** its a standalone tool used to convert schema from one DB engine to another
  - This is even supported for DB to S3 migrations
  - **exam imp** SCT is not used when migrating between DB's of the same type
    - example, on-premises MySQL to RDS MySQL
  - SCT works with OLTP DB types (mySQL, MSSQL, Oracle)
  - SCT works with OLAP DB types (Teradata, Oracle, Vertica, Greenplum)
- There is absolutely no downtime by using this service for data migration
- DMS + SCT + snowball mostly helpful and used for large scale Data migration
  - example, snowball (muti-TB in size)
