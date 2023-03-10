# Chapter 40 - Databases

[TODO] Start with comparison to spreadsheet, explaining 'NoSQL' Vs 'SQL' and that this is Relational vs Non-Relational

## Spreadsheets
Databases are like spreadsheets (Excel/Sheets), which is true. They both possess rows(records) and columns (fields). If you’re familiar with the hows and whys of spreadsheets, you’re part way there to having a grasp on SQL’s db’s. Actually––don’t get comfortable.
[TODO] quick comparison to the lookup methods of both and contrasts.


When you’re handling *a lot* of data, ranging from just a small business with daily foot traffic to international corporations, the amount of data that will be accessed daily;even sales from someone’s shopify/etsy page, you still need to track a lot of information.

While the structure of both databases and spreadsheets share some things in common, the spreadsheet handles simple record keeping and managing concise amounts of data. However, databases are engineered for both searching and retrieving stored data across many tables and preparing the requested data however you want it. You can *have it your way*.

While spreadsheets may be more readily approachable and even help organize data from databases for presentations, databases can hold much more by magnitudes. Their forms, queries and reports also update as their tables do with no need to redo them. Interacting with databases may not be as straightforward, but their power is incredible.

## Why databases?

Enter Sam, he’s passionate about his culinary studies, *especially* baked goods. He is aware that his area lacks readily accessible treats and a very active mall has an opening with reasonable rates for rent. Better yet, there’s no Cookie Co, Mrs Fields, or an Auntie Anne’s within miles! Sam begins to create his plan.[Probably a good segue to small business venture articles]

Jumping forward, before Sam can even set prices, he has to know what prices to set for his goods and services. Business plan aside, he already needs a spreadsheet! 

If you’re already familiar with spreadsheets, you've realized by now that we’re beyond the need of just one worksheet(spreadsheet in the general sense, table in the database sense). A workbook(database) can contain many worksheets, but running a business, especially one that accepts card payments and digital orders, requires *a lot* more than the typical workbook can handle.

Sam is busy recording every transaction manually, especially at the volume of traffic in both digital and brick/mortar, and is beyond unfeasible at this point. Especially for the sake of figuring future prices, deals, sales, when to buy more of an ingredient, how much to buy, which vendor to call, how much said orders would cost, when peak hours are, what sells best at those times, recording profits and losses for taxes, collecting emails for sending out coupons and offers and even dogearing goods between both fronts of the store for orders placed ahead of time! This is just the beginning of what a small business needs to keep track of.

Here, even Sam, with his Culinary Arts degree and daily/nightly baking, could have his book keeping stressors nearly entirely alleviated were he to pick up a database to carry the bookkeeping for him! Fortunately for him, he lives in 2023 and has access to our modern tools and databases. 



[TODO] explain CRUD

## CRUD

**Create, Read, Update, Delete**

SQL, Structured Query Language, interacts with relational databases (RDBMS), it is very powerful but also quite restrictive in that it requires schema, to create, read/retrieve, update, and delete records in its database, this is also known as CRUD (it encompasses both the actions we use to interact with the databases and how we feel about them)! Very technically, SQL and spreadsheets have this in common as well, the main differences being that RDBMS servers require Schema but they also can handle larger volumes of data and provide better security and access to spreadsheets.

[TODO] Maybe flesh this out a little bit more.

## SQL
{{< tip >}}

This is Opinionated Guides, so let me be clear, I really, **really** hate SQL. I don't like OOP in general, and SQL is sorta like object orientation taken further. Add onto this a mostly shit syntax, like, **JOIN**s are objectively weird to read, write, and understand. I'm not saying SQL doesn't have its place: It's reasonably good for ensuring data fits a strict structure and does make sense in cases where using OOP also makes sense. It's just that OOP itself is over-used, leading to SQL being overused. This is probably in part due to education mostly teaching SQL and it being the only type of database many students ever learn. This might make some sense if it were honestly better, but I suspect that it's in large part taught for the same reason Java is:  Sun Microsystem paid a [fuck ton](https://www.theregister.com/2003/06/09/sun_preps_500m_java_brand/#:~:text=Sun%20is%20to%20lead%20a,world's%20best-known%20technology%20brands.) of money to push it- hence the **"3 Billion Devices Run Java"** Thing. Then, Oracle bought Java from Sun Microsystems and made the first commercially available implementation of SQL. I'm hopeful (albeit probably naively) that Oracle making Java a mess of licensing as the 'main' Java Virtual Machine goes [paid (Read on Wikipedia)](https://en.wikipedia.org/wiki/Java_(programming_language)) and [suing Google](https://en.wikipedia.org/wiki/Google_LLC_v._Oracle_America,_Inc.) will be the nail in the coffin for education using it- and that SQL will be demoted to being taught alongside other options along with that. Regardless of the reasons, though, you should still learn it because everything uses it.

{{< /tip >}}
[TODO] SQL, full CRUD, joins, the works

Relational databases are actually not a new thing! They have been in use since the 70’s and didn’t really see any competition until the 2000’s with the appearance of non-relational databases as an answer to one of the weaknesses of RDBMS (Relational Database Management System), the struggle of scalability as we moved to the cloud with services required to serve users from all over the Earth, thousands at a time.

The relation between the tables of a relational database can best be imagined as the overlap of two or more circles in a complex venn diagram; the overlap being what would be duplicate data! The use of certain markers, particularly the Primary and Foreign keys, establish relationships between many tables––these relations are part of what makes RDBMS database functions so powerful! The Primary Key of a table is the unique ID of records(should be, anyways), when referenced from a separate table, it is known as a Foreign Key to the additional tables.

{{< hint style="info" >}}
**Many to one** 

Let's say we have table1 here, let's call it **users**
| UserID | Name  | email |
| :---   | :---: | ---: |
| IDs | names | emails |

UserID is the **Primary Key** for users.
Our second table, table2, how about **tickets**.
| TicketID | UserID | Problem | Urgency |
| :---   | :---: | :---: | ---: |
| ticketIDs | userIDs | problems | criticalities |

Here, UserID is a **Foreign Key** while the Primary Key of tickets is TicketID.
{{< /hint >}}

| One | to | Many |
| --- | --- | --- |
| A user has one UserID but likely many items associated with it. |  | This is also known as an **N-ary Relationship**
|Many | to | Many |
| A **Binary Relationship** |  | Most students enroll in multiple courses while courses have many students. |
| One | to | One |
| Also known as a **Unary Relationship** | | Only one set of entities, one to one, such as UserID and StateID.|

 Separate Tables can be joined in reports, filter by dates and return a report featuring nothing but one column from each table! We have various organizations of this method.

This probably doesn’t sound like anything but it’s so much better to have a table of unique order numbers, dates, and user IDs related to a general users table than somehow cramming a long list of order numbers into some fields in the Users Table. This allows for a relation to exist between the tables (User ID’s) and query all the info of a user when they ask about their order from the Orders table with just a JOIN function(more on that in a bit)! No duplicate data, all data present has a place to be.



## SQL Language overview

For those of you that are familiar with spreadsheets and writing functions, this will feel somewhat similar! For everyone else, I have some brief advice that has helped my friends and the students I’ve taught.

Think about what you want to do, what you’re going to have the database do with the data, and remember, capitalizing the SQL keywords just makes it easier to read, it has become the convention to write them capitalized-SQL keywords are not case sensitive.
All good devs try to follow conventions, such as the PEP-8 for Python, because we don’t fancy being 86’ed while taking a nap after a twelve hour day.
“I want to get data” : SELECT
“I want to put new data into the db”:INSERT INTO
“I want to make a new database!”: CREATE DATABASE
“I want to update a record!”: UPDATE
“I want to delete a record.”:DELETE
“I want to change the database.”: ALTER DATABASE
“I want to make search criteria.”: CREATE INDEX
“I want to delete criteria I no longer need.”:DROP INDEX
“I want to make a new table.”: CREATE TABLE
“I don’t need this table anymore, let’s delete it.”: DROP TABLE
“I want to get all the data from the users table.”:
```sql
SELECT * FROM users
```
“I want to get the emails of our users (in this case, email).”: 
```sql
SELECT email FROM users
```
Or how the convention goes:
```sql
SELECT email
FROM users;
```

Decide on the information you need, and choose the corresponding column, or columns if you don’t need it all, if you do, then you’ll use * as I did above.

Now we’re thinking with portals.

What if you only want certain data from specified columns?
Let’s say your site has been running a promotion for the last month and you want to reach out/ send a gift to the new members of your community? Sounds like we need at least:
Name (preferred or set nickname to be friendly), email, and date of account creation and we’ll use the day before the promotion as the condition for filtering!
 
```sql
SELECT name, email, accountDate AS "Join Date"
FROM users
WHERE accountDate < dd/mm/yyyy
```

Oh yeah, that AS keyword, it’s great, especially for when you want something to be a bit easier to read if not look a bit more *presentable* on a report, these are known as *aliases*.


Now we can start to get spicy.
We can get even more specific with our conditions! This is excellent when you have a few different ways to differentiate your records from each other.

You want to advertise education licenses to your users that are students or just single person teams (*please zbrush*):

```sql
SELECT name, email, accountType
FROM users
WHERE accountType = indie OR accountType = student OR accountType = educator
```

You want to see your student and educator users from Toronto for a convention your team wants to plan:

```sql
SELECT name, email, country, city, accountType
FROM users
WHERE country = ‘Canada’ AND city = ‘Toronto’ AND accountType = ‘student’ OR accountType = ‘educator’
```

Joins are really powerful but also a bit more tricky than what we’ve covered so far, W3 Schools actually has some really helpful diagrams here, representing the various types of JOINS at the bottom, before the exercises.
The INNER JOIN example they provided is actually pretty decent, it may seem visually overwhelming at first, but it’s really just being more specific.


```sql
SELECT Orders.orderID, Customers.CustomerName, Orders.OrderDate
FROM Orders
INNER JOIN Customers ON
Orders.CustomerID=Customer.CustomerID;
```

{{< hint style="info" >}}
The ON keyword is used to specify the condition for the join. In this case, we're joining the tables based on their CustomerID columns.
{{< /hint >}}

This is actually one of the first solid examples of the power of relational databases.
The INNER of the INNER JOIN just describes the overlap of a Venn Diagram, what both tables have in common as W3’s diagrams illustrate, JOINS are very much like Venn Diagrams.

We know our output is three columns wide from the above but you probably haven’t seen the dot operators in SQL yet! If it looks like table names are being referenced in the column space, it’s because they are, actually. This is how we differentiate between columns of separate tables and JOIN keywords give us the ability to return data together from separate but ‘related’ tables!

In W3’s example, we get to incorporate data from customer names next to their Order ID’s and Order dates,this creates a very useful view for reports, data that wouldn’t make sense to share a table together completely can be pulled together to better illustrate your data and this doesn’t destabilize your tables at all! 


There's a lot of joins in SQL, including:
* inner joins (which only include rows where the join condition is met in both tables)
* outer joins (which include all rows from one table and matching rows from the other table)
* cross joins (which combine every row from one table with every row from the other table)


[TODO], like, all of it. Need SQL vs Non-Relational too




There is a lot of dogma in tech, however, even Venkat has gone on record to say that there is no best programming language and that they are tools one should use best suited for the occasion.

[Venkat tool quote](https://twitter.com/venkat_s/status/1291120644218744832?s=20)

[TODO] add screenshot of tweet

I share the same philosophy with both my languages and paradigms.


ACID and BASE

Some of the key properties of Relational databases are represented by the acronym ACID (Atomicity, Consistency, Isolation, and Durability) and conversely BASE (Basic Availability, Soft state, and Eventual consistency) represents the properties of the Non-relational databases.


| **Atomicity**: No actions are half-complete, if one part of an action cannot be done, no changes are made, definite success or failure. | **Basic Availability**: The focus is not 100% data consistency at once; rather it ensures that the data is always accessible. |
| --- | --- |
| **Consistency**:The database cannot change while performing a transaction and any data entering the database is made to be consistent with the set mechanisms and rules. This protects datas’ integrity. | **Soft State**:The system’s state is mutable, it doesn’t require write-consistency. 
| **Isolation**: Regardless of how it may seem, no matter how many operations are being performed on the database, each operation is contained to itself, atomic and executes sequentially. No transaction can affect another one in progress.  This is vital to remember when making SQL queries and scripts. |**Eventual consistency**: The BASE model ensures constant (or near-as-possible) availability, the sacrifice to achieve this means that while the data in a system may not always be consistent, its eventual consistency is ensured. 
| **Durability**: Even should there be a system failure, the changes are finalized and will persist upon completing an operation. The ACID model properties define reliable and secure databases and scales vertically. Key disadvantages are that they can’t really scale horizontally and vertical scaling becomes *extremely* expensive fast, requiring more and more powerful machines. | BASE model properties strictly prioritize availability of data, adaptable and dynamic database schema, and the ability to scale horizontally, very easily. Key disadvantage is that they, by their nature, cannot alone ensure the integrity and consistency of data. |

Ultimately, the choice depends on the requirements of the system in question. ACID is often used in traditional RDBMS systems that require immediate consistency, while BASE is commonly used in distributed systems and NoSQL databases that require high availability and scalability. Pick the best tool for the job.

[TODO] Getgud at my formatting and fix this.

Now we introduce NoSQL (which stands for "not only SQL") is a type of database that is designed to handle large amounts of unstructured or semi-structured data. It's often used in applications where data is generated at a high rate and needs to be stored and processed quickly. NoSQL databases can be highly scalable, which means they can handle a large number of users and data inputs without slowing down.

The main difference between NoSQL and SQL is the way they handle data. SQL databases are highly structured, with data organized into tables ordered by specific blueprints (schema), which must be created before data can be stored. Whereas NoSQL databases, can handle unstructured or semi-structured data, and the schema can be flexible, allowing for changes in data structure over time.

Also, while SQL databases use a standardized language called SQL to access data, which provides a powerful and flexible way to retrieve and manipulate data. NoSQL databases use different query languages depending on the database, but these languages often lack the strengths of SQL, notably flexibility and having a general standard to adhere to.

Notable NoSQL databases are Cassandra HDFS(Hadoop File System),  they have some similarities and differences when compared to SQL databases.

Cassandra, a highly scalable, distributed NoSQL database that is designed for high availability and fault tolerance. It is made to handle high velocity traffic, both for accessing and writing data. Cassandra does not have a fixed schema, it can handle dynamic and changing data structures and is often used for applications that require high scalability, such as social media and IoT.

HDFS, on the other hand, is a distributed file system that is part of the Hadoop ecosystem. It is designed for storing and processing large datasets across multiple nodes(essentially machines/ single systems) in a cluster(multiple networked nodes). HDFS is optimized for batch processing and can handle both structured and unstructured data. It is often used for big data analytics, machine learning, and other data-intensive applications. I implemented a HDFS pilot system in 2015 as a test device for a several petabyte DC. The client that wanted it was very pleased but we had an interesting time getting it running; I'm very glad to see how it has matured over the years and serves data communities well.

Compared to SQL databases, Cassandra and HDFS offer advantages such as high scalability and flexibility, which make them well-suited for handling large and complex datasets. However, they also have some limitations, such as less powerful query languages and less support for transactional consistency.

Cassandra and HDFS are well-suited for scalability and flexible in more than one way, SQL's architecture does make it extremely reliable and consistent, as ACID should be. They are often used for applications that require complex queries and data manipulation, such as financial institutions and e-commerce.

Again, pick the right tool for the job.

Cassandra and HDFS:
* Ideal for handling large and complex datasets that require high scalability and flexibility
SQL:
* Better suited for applications that require strong consistency and complex query operations.


[TODO] Need to finish this outline into a proper paragaph
xNoSQL versus SQL
xCassandra, HDFS (NoSQL) vs. SQL
xScalability versus non-scalable
new tech versus traditional and ubiquitous
Node failure tolerance and disruption prevention versus missing xlimited indexes joins and functions



[Generating SQL Code with Blocks](https://www.dbinf.informatik.uni-wuerzburg.de/google-blockly-4efa0da/sql/index.html) - Scratch Like Programming for SQL



### SQL Servers (MySQL)

## Sanitizing Inputs

![XKCD Drop Tables](/eng/xkcddrop.webp)

{{< attribution >}}

[TODO] need image source

{{< /attribution >}}

## Key-Value (Memcached, Redis)

## Graph Databases (Neo4j, GraphQL?)

[Why not use GraphQL?](https://wundergraph.com/blog/why_not_use_graphql)

## GraphQL

[TODO]I need to reword this but:
Unlike traditional SQL databases that enforce ACID properties, GraphQL provides more flexibility to developers in terms of how they can retrieve and modify data. GraphQL allows developers to define a flexible schema that can handle a wide range of queries, which can be both good and bad in terms of consistency and data integrity.

GraphQL is designed to work with a wide range of data sources, including both SQL and NoSQL databases, and allows for eventual consistency between different data sources. This means that data may not be consistent at all times, but will eventually converge to a consistent state.

Overall, GraphQL provides a more flexible approach to data querying and manipulation, but requires careful consideration of the trade-offs between consistency and performance.

-Maybe a GraphQL article? I like it in MERN.

## Document-Oriented Database (Couchbase)

## Other Resources

[List of Some Open Source Database Options](https://www.goodfirms.co/blog/top-10-free-and-open-source-database-management-software-solutions)