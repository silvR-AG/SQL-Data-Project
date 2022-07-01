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


#### CAP Theorem

#### JOINS:
A JOIN clause is used to combine rows from two or more tables, based on a related column between them. There are four different types of the JOINs in SQL:

    - INNER JOIN: Returns records that have matching values in both tables.
    - LEFT JOIN: Returns all records from the left table, and the matched records from the right table.
    - RIGHT JOIN: Returns all records from the right table, and the matched records from the left table.
    - FULL JOIN: Returns all records when there is a match in either left or right table.
    
Left,Right and Full JOINS are considered as outer joins.


#### Aggregations, Filters in queries:
#### Normalization:
#### Indexes:
#### Transactions:
A transaction is a logical unit of work that accesses and updates the contents of a database. Read and write operations are used by transactions to access data. A transaction has several states:
1. Active State: Every transaction starts out in the active state. The transaction is currently being carried out in this state.
2. Partially Committed State: A transaction has reached this state when it completes all operations but the data has not been saved to the database.
3. Failed State: The transaction is considered to be in the failed state if any of the database recovery system’s checks fail.
4. Committed State: If a transaction completes its final operation successfully, it is considered to be committed. In this state, all of the changes are written to memory and as a result, saved on the database system permanently.
5. Aborted State: If any of the tests fail, the transaction is said to go to a failed state. Upon entering this state, the database recovery system attempts to bring the database to the previous consistent state(committed state). If this doesn’t happen then the transaction would be rolled back or aborted so as to bring the database back to a consistent state. Once it has been aborted, the database recovery module will either kill the transaction or re-start the transaction.
6. Terminated State: If there is no rollback and the transaction is in the “committed state,” the system is consistent and ready for a new transaction, while the old one is terminated.






