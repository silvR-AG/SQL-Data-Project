# Structured Query Language (SQL)

#### What is SQL? 

Structured Query Language or SQL is a standard language used for storing, manipulating or retrieving data from Database.
A Database as the name suggests is a congregation of related data and information.
SQL is a tool that is used to work with such collections. There are various database management systems that use SQL to alter and work on data like MySQL, PostgreSQL.

It has various properties and attributes that make it more efficient in manipulating data. In this paper, we will discuss the various properties and attributes of SQL.


#### ACID : Atomicity-Consistency-Isolation-Durability

###### Atomicity:
By this, we mean that either the entire transaction takes place at once or doesn’t happen at all.
Each transaction is considered as one unit and either runs to completion or is not executed at all. It involves the following two operations. 
—*Abort*: If a transaction aborts, changes made to the database are not visible. 
—*Commit*: If a transaction commits, changes made are visible. 
Atomicity is also known as the ‘All or nothing rule’. 

###### Consistency:
This means that integrity constraints must be maintained so that the database is consistent before and after the transaction. It refers to the correctness of a database. It means that after a transaction is made, the values should remain consistent with the previous values. For example, if T1 has 100 units of something and T2 has 100 units. The total number of units is 200. Now if we take 50 units from T1 and add it to T2. Both T1 and T2 should be updated with new values and the sum should be 200 i.e., T1 has 50 and T2 has 150.

###### Isolation:
Isolation is defined as a state of separation. Isolation is a property where no data from one database should impact the other and where many transactions can take place at the same time. In other words, when the operation on the first state of the database is finished, the process on the second state of the database should begin. It indicates that if two actions are conducted on two different databases, the value of one database may not be affected by the value of the other. When two or more transactions occur at the same time in the case of transactions, consistency should be maintained.

###### Durability:
The property of durability refers to the fact that if an operation is completed successfully, the database remains permanent in the disk. The database’s durability should be such that even if the system fails or crashes, the database will survive. However, if the database is lost, the recovery manager is responsible for guaranteeing the database’s long-term viability.


#### CAP Theorem:
The CAP theorem states that it is impossible for a distributed computing system to simultaneously provide all three of the following guarantees:

    - Consistency: All clients see the latest data even in the case of updates.
    - Availability: All clients can find a replica of some data even in the case of a node failure. This means that even if some part of the system goes         down, the clients can still access the data.
    - Partition tolerance: The system continues to work regardless of arbitrary message loss or failure of part of the system.


#### JOINS:
A JOIN clause is used to combine rows from two or more tables, based on a related column between them. There are four different types of the JOINs in SQL:

    - INNER JOIN: Returns records that have matching values in both tables.
    - LEFT JOIN: Returns all records from the left table, and the matched records from the right table.
    - RIGHT JOIN: Returns all records from the right table, and the matched records from the left table.
    - FULL JOIN: Returns all records when there is a match in either left or right table.
    
Left,Right and Full JOINS are considered as outer joins.


#### Aggregations, Filters in queries:

###### Aggregations:
Aggregations are queries which are used to perform calculations of multiple datas and return a single value. Like finding out the sum of a set of values. Examples of aggregations are the SUM and COUNT clause.

###### Filters
SQL allows filtering data during querying. Using various techniques of filtering in SQL, one can simplify the output of queries without having to implement any separate query. Examples of filters are, GROUP BY , HAVING and FILTER clauses.


#### Normalization:
Normalization is the process of organizing the data and the attributes of a database. It is performed to reduce the data redundancy in a database and to ensure that data is stored logically. Data redundancy means having the same data but at multiple places. It is necessary to remove data redundancy because it causes anomalies in a database which makes it very hard for a database administrator to maintain it.

There are four types of normal forms that are usually used in relational databases:
   1. 1NF: A relation is in 1NF if all its attributes have an atomic value.
   2. 2NF: A relation is in 2NF if it is in 1NF and all non-key attributes are fully functional dependent on the candidate key.
   3. 3NF: A relation is in 3NF if it is in 2NF and there is no transitive dependency.
   4. BCNF: A relation is in BCNF if it is in 3NF and for every Functional Dependency, LHS is the super key.

#### Indexes:
Indexing is used to quickly retrieve particular data from the database. Formally we can define Indexing as a technique that uses data structures to optimize the searching time of a database query. Indexing reduces the number of disks required to access a particular data by internally creating an index table.Indexing is achieved by creating Index-table or Index.Index usually consists of two columns which are a key-value pair. The two columns of the index table(i.e., the key-value pair) contain copies of selected columns of the tabular data of the database. SQL indexes are used in relational databases to retrieve data. An index in SQL acts as a pointer to data in a specific table.

#### Transactions:
A transaction is a logical unit of work that accesses and updates the contents of a database. Read and write operations are used by transactions to access data. A transaction has several states:
1. Active State: Every transaction starts out in the active state. The transaction is currently being carried out in this state.
2. Partially Committed State: A transaction has reached this state when it completes all operations but the data has not been saved to the database.
3. Failed State: The transaction is considered to be in the failed state if any of the database recovery system’s checks fail.
4. Committed State: If a transaction completes its final operation successfully, it is considered to be committed. In this state, all of the changes are written to memory and as a result, saved on the database system permanently.
5. Aborted State: If any of the tests fail, the transaction is said to go to a failed state. Upon entering this state, the database recovery system attempts to bring the database to the previous consistent state(committed state). If this doesn’t happen then the transaction would be rolled back or aborted so as to bring the database back to a consistent state. Once it has been aborted, the database recovery module will either kill the transaction or re-start the transaction.
6. Terminated State: If there is no rollback and the transaction is in the “committed state,” the system is consistent and ready for a new transaction, while the old one is terminated.


#### Locking mechanism:
Locks in SQL are used to prevent concurrent use of data during transactions. As concurrent use of datas may create inconsistency, thereby not following the ACID properties. Therefore, locking mechanisms are used to avoid such situations.

Lock mode considers various lock types that can be applied to a resource that has to be locked:

   - Exclusive (X)
   - Shared (S)
   - Update (U)
   - Intent (I)
   - Schema (Sch)
   - Bulk update (BU)

#### Database Isolation Levels:
Isolation is the property of databases that ensures their integrity. Isolation levels are levels defined within a database system, which define how much a certain transaction needs to be isolated from any modifications made in the database by other transactions. 
The SQL standard defines four isolation levels.

###### Read Uncommitted
The lowest isolation level allowed by SQL is read uncommitted. In this level, transactions can read data that is not committed by other transactions, permitting dirty read. It is safe to say that transactions are not isolated from each other in this isolation level.

###### Read Committed
This isolation level allows for the reading of data after it is committed by a transaction. This means no dirty reads are possible. This isolation is unable to prevent non-repeatable reads. This is ensured as locks are applied on the row being read. This prevents the reading, updating, and deletion of data.

###### Repeatable Read
This isolation tries to improve on the previous isolation level by preventing both dirty reads and non-repeatable reads. This prevention is done by applying locks on rows that are read and rows that perform write operations. However, this cannot prevent the addition of new entries to the database if the transaction is performing some work (not between two reads).

###### Serializable
The highest isolation level allowed is serializable. This isolation level looks like a serial execution, with almost no concurrency. All the three read phenomena are prevented in this isolation level, but it compromises concurrent execution.


#### Triggers:
Triggers are the SQL codes that are automatically executed in response to certain events on a particular table. These are used to maintain the integrity of the data. Example of a trigger creations is:

    Create Trigger Trigger_Name
    (Before | After)  [ Insert | Update | Delete]
    on [Table_Name]
    [ for each row | for each column ]
    [ trigger_body ]

The syntax is explained below: 
- Create Trigger - These two keywords are used to specify that a trigger block is going to be declared. 
- Trigger_Name - It specifies the name of the trigger. Trigger name has to be unique and shouldn’t repeat.
- ( Before | After ) - This specifies when the trigger will be executed. It tells us the time at which the trigger is initiated, i.e, either before the ongoing event or after.
- [ Insert | Update | Delete ] - These are the DML operations and we can use either of them in a given trigger.
- on [ Table_Name ] - We need to mention the table name on which the trigger is being applied. Don’t forget to use on keyword and also make sure the selected table is present in the database.
- [ for each row | for each column ] - Row-level trigger gets executed before or after any column value of a row changes
Column Level Trigger gets executed before or after the specified column changes
- [ trigger_body] - It consists of queries that need to be executed when the trigger is called.


#### References:
- [SQL tutorial](https://www.w3schools.com/sql/default.asp)
- [DBMS](https://www.geeksforgeeks.org/dbms/?ref=lbp)




