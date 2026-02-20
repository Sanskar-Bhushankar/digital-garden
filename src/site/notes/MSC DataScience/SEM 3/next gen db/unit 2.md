---
{"dg-publish":true,"permalink":"/MSC DataScience/SEM 3/next gen db/unit 2/","created":"2026-02-17T06:43:12.925+05:30"}
---


UNIT II: NoSQL & MongoDB

1. Trace the history and evolution of NoSQL databases.  
    Answer:
    

- In early days 1970s–1990s relational databases like MySQL and Oracle were dominant.
    
- They worked well for structured data and small to medium scale systems.
    
- Around 2000s, internet companies like Google, Amazon, Facebook started handling massive data and high user traffic.
    
- Traditional RDBMS failed to scale horizontally and became expensive.
    
- Google introduced Bigtable, Amazon introduced Dynamo which inspired modern NoSQL systems.
    
- Around 2009, the term NoSQL became popular meaning Not Only SQL.
    
- NoSQL databases were designed for distributed systems, big data and flexible schema.
    

2. Explain the limitations of relational databases that led to the emergence of NoSQL.  
    Answer:
    

- Fixed schema: Difficult to change structure frequently.
    
- Vertical scaling: Requires powerful hardware instead of adding multiple machines.
    
- Join operations: Slow performance with very large datasets.
    
- Poor handling of unstructured or semi-structured data.
    
- High cost for scaling and licensing.
    

3. Discuss ACID properties and BASE properties with suitable examples.  
    Answer:
    

- ACID stands for Atomicity, Consistency, Isolation, Durability.
    
- Atomicity: Transaction either fully completes or fails. Example: Bank transfer.
    
- Consistency: Database remains valid before and after transaction.
    
- Isolation: Parallel transactions do not affect each other.
    
- Durability: Once committed, data is permanently stored.
    
- BASE stands for Basically Available, Soft state, Eventually consistent.
    
- Basically Available: System always responds.
    
- Soft state: Data may change over time.
    
- Eventually consistent: Data becomes consistent after some time.
    
- Example: Social media likes count.
    

4. Explain the CAP theorem and its implications in distributed databases.  
    Answer:
    

- CAP stands for Consistency, Availability, Partition tolerance.
    
- In distributed systems, only two out of three can be achieved at the same time.
    
- Consistency: All nodes return same data.
    
- Availability: Every request gets a response.
    
- Partition tolerance: System works despite network failure.
    
- Example: In network partition, system must choose between consistency or availability.
    

5. Compare SQL and NoSQL databases in terms of scalability, schema, and performance.  
    Answer:
    

- Scalability: SQL scales vertically, NoSQL scales horizontally.
    
- Schema: SQL has fixed schema, NoSQL has flexible schema.
    
- Performance: SQL better for complex joins, NoSQL better for large scale distributed reads/writes.
    

6. Discuss advantages and disadvantages of NoSQL databases.  
    Answer:  
    Advantages:
    

- Horizontal scalability.
    
- Flexible schema.
    
- High performance for big data.
    
- Suitable for unstructured data.  
    Disadvantages:
    
- Limited support for complex joins.
    
- Eventual consistency issues.
    
- Less standardized query language.
    

7. Explain different categories of NoSQL databases with examples.  
    Answer:
    

- Key-Value: Redis, DynamoDB.
    
- Document: MongoDB, CouchDB.
    
- Column family: Cassandra, HBase.
    
- Graph: Neo4j.
    

8. Describe key-value and columnar databases in detail.  
    Answer:
    

- Key-Value stores data as key and value pair.
    
- Fast retrieval using key.
    
- Used for caching and sessions.
    
- Columnar databases store data in columns instead of rows.
    
- Suitable for analytics and large datasets.
    

9. Explain document-oriented and graph databases with use cases.  
    Answer:
    

- Document databases store data in JSON-like documents.
    
- Flexible schema.
    
- Used in content management and e-commerce.
    
- Graph databases store nodes and relationships.
    
- Used in social networks and recommendation systems.
    

10. Discuss MongoDB design philosophy and non-relational approach.  
    Answer:
    

- MongoDB is a document-oriented NoSQL database.
    
- Stores data in BSON documents.
    
- Schema-less design.
    
- Designed for horizontal scalability and high performance.
    
- Avoids complex joins using embedded documents.
    

11. Explain JSON-based document storage and its advantages.  
    Answer:
    

- Data stored in JSON-like format.
    
- Human readable and easy to understand.
    
- Flexible schema allows different structure per document.
    
- Easy integration with web applications.
    

12. Compare JSON and BSON formats used in MongoDB.  
    Answer:
    

- JSON is text-based format.
    
- BSON is binary JSON used internally by MongoDB.
    
- BSON supports additional data types like Date and ObjectId.
    
- BSON is faster for parsing and storage.
    

13. Explain MongoDB data model and document-based architecture.  
    Answer:
    

- Data stored as collections.
    
- Each collection contains documents.
    
- Document is key-value pair structure.
    
- Supports embedded documents and arrays.
    

14. Describe the role of the _id field and indexing in MongoDB.  
    Answer:
    

- _id is primary key of document.
    
- Automatically created if not provided.
    
- Ensures uniqueness.
    
- Indexing improves query performance.
    
- MongoDB creates default index on _id.
    

15. Explain CRUD operations in MongoDB with examples.  
    Answer:
    

- Create: insertOne({name:"A", age:20})
    
- Read: find({age:20})
    
- Update: updateOne({name:"A"}, {$set:{age:21}})
    
- Delete: deleteOne({name:"A"})
    

16. Discuss conditional operators and regular expressions in MongoDB queries.  
    Answer:
    

- Conditional operators: $gt, $lt, $gte, $lte, $ne.
    
- Example: find({age: {$gt:18}})
    
- Regular expressions used for pattern matching.
    
- Example: find({name: /sam/i})
    

17. Explain aggregation framework and aggregate() function in MongoDB.  
    Answer:
    

- Used for data processing and analysis.
    
- Works using pipeline stages.
    
- Example stages: $match, $group, $sort.
    
- aggregate() function performs operations on collection.
    

18. Describe MapReduce in MongoDB and its working mechanism.  
    Answer:
    

- Used for large data processing.
    
- Map function processes data and emits key-value pairs.
    
- Reduce function combines values.
    
- Suitable for batch processing.
    

19. Explain performance vs features trade-offs in MongoDB.  
    Answer:
    

- MongoDB provides high performance by reducing joins.
    
- Flexible schema increases speed of development.
    
- However lacks strict ACID transactions in distributed mode.
    
- Trade-off between strong consistency and scalability.
    

20. Discuss MongoDB document data model approach with a real-world application.  
    Answer:
    

- Data stored as documents similar to application objects.
    
- Reduces need for joins.
    
- Example: E-commerce application.
    
- Order document contains user info, product details and payment info in single document.
    
- Improves read performance and scalability.