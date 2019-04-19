---
layout: post
title:  "Teradata Fundamentals"
date:   2019-01-06 0:18:00
categories: SQL

---

###### Tags: `Teradata` `Fundamentals`
### Objective
- Identify components of the Teradata Database architecture.
- Identify the differences between Primary Index and Primary Key.
- Identify the types, levels, and functionality of locking provided by Teradata.
- Recognize the functions and types of authentication in the Teradata Database.
- Identify tools and utilities used for data integration.

### Module-1 : Teradata Architecture and Components
#### The Teradata Data Warehouse
The teradata data warehouse stores current as well as historical data in one location this enables effective data analysis and reporting , because it is a central repository of integrated data it is considered as core component of bussiness intelligence.

#### The Teradata database
The Teradata database is designed to support high performance diverse queries as well as in database analytics and has sophosticated workload management so that data warehouse can  adjust to the changing needs of the bussiness. In addition it supports and enables all teradata warehouse solutions.

> [color=#f45333] Teradatas built in parallelism enables faster processing of queries.


#### How You Can Connect to Teradata

![](https://i.imgur.com/H5PuAa6.png)


The client application submits an SQL request to the Teradata Database, receives the response, and submits the response to the user.

The **`Channel-attached`** system connects via a mainframe, where the **`Network-attached`** system connects via pc, tablet, phone, etc.

#### How is Teradata Database used
 Companies can use Teradata database for the following:
- Tackle business problems.
- Achieve high-impact business outcomes.
- Leverage data and analytics.
- Accelerate their time-to-value.
- Streamline operations.
- Improve processes.
- Manage marketing and promotions.
- Prepare shipping labels.
- Manage employee records.
- Track production, inventory, and distribution.

#### Features and Benefits of the Teradata Database
- **Highly Scalable**
   System is expandable as the business grows.
- **Unlimited Parallelism**
   Allows enormous volumes of data to be processed very quickly.
- **Single Version of Business**
   Single data store implemented through heterogenious client access.
- **High Availability**
   Both hardware and software provide fault tolerance
- **Teradata Everywhere**
   Migration across different deployment options. Supports hybrid architectures
   
#### Objects within the Teradata Database
>[color=#f45337]Partitioning: A database process where very large tables are divided into multiple smaller parts.

- ==++Fallback++== [color=#f45337]
   The concept of fallback is about protecting the customers’ data against AMP failure. The data is protected by storing the second copy of each row of the table on an alternate AMP called a Fallback AMP.
- ==++Data Types++== [color=#f45337] 
   Data types specify the kind of values that will be stored in the column.Each column in a table is associated with a datatype.
- ==++Partitioned Table++== [color=#f45337] 
    A column, or vertical, partitioned table is a physical design implementation option that allows sets of columns or a single column of a table to be stored in separate partitions. This can improves performance for some types of queries and also allow reduction on the I/O.

- ==++Set Tables++== [color=#f45337] 
    Set Tables does not allow duplicate rows in the table and are default in the Teradata Database. However,Multiset tables however allow duplicate rows.
- ==++Views++== [color=#f45337] 
    For any database, there are a number of possible views that may be specified. Often referred to as a virtual table, the view doesn't actually store information itself, but just displays it from one or more existing or underlying tables. Views are used to control access to the underlying tables and simplify access to data. Some columns in a view do not exist in the underlying table. For example, it is possible to present calculations or data summaries that you cannot obtain from the table.
- ==++Macro++== [color=#f45337]
    Macros reduce the number of keystrokes needed to perform a complex task. A familiar example is one or more sequel statements that can be executed at a single request 
- ==++Trigger++== [color=#f45337] 
    A trigger defines events that happens when an event occurs, such as a set of Structured Query Language (SQL) statements automatically "firing off" an action when an operation modifies a specified column or columns.
- ==++Stored Procedure++== [color=#f45337] 
    Stored procedures are a combination of pre-defined procedural statements, control declarations and sql statements that is a program that are stored in, and execute within, the Teradata Database.
- ==++Secondary Index++== [color=#f45337]
    A Secondary Index allows optional ways for the system to access the rows of a table. It is unlike a Primary Index in that it has no influence on the way rows are distributed across the AMPs. 
- ==++Join Index++== [color=#f45337] 
    A Join Index is defined to enable join queries to be resolved without accessing or joining the actual tables. They can be beneficial when queries frequently request a particular join.
- ==++Users++== [color=#f45337] 
    A user can be thought of as a collection of Tables, Views, Macros, Triggers, Stored Procedure, Join indexes and access rights. Users are an entity that can log on to Teradata with a password and establish a session.
    
#### Object Management 
In order to manage the data base objects, Teradata needs to store information about all of the objects. This info is referred to as metadata.

Metadata can include:
- Means of creation of the data.
- Purpose of the data.
- Time and date of creation.
- Creator or author of the data.
- Locations on a computer network where the data was created.
- Standards used.
- File size.

==Data Dictionary==
The data dictionary is owned by system user DBC. The data dictionary is composed of  tables and views. Data dictionary views provide access to the information in the tables.

Tables and views are  reserved for use by the system which contains the metadata about the database objects such as privileges, system events, and system usage. For example,

==Tables store:==

- Indexes
- Constraints
- table creation (date and time). 

==Views store:==

- View or macros text
- creation time details
- access priveleges

#### Components

Major components that make up the database:
- ==++Node++== [color= #137738] 
A node serves as the hardware platform upon which the database software operates. The basic building block for a Teradata system, the node is where the processing occurs for the database.

- ==++Clique++== [color=#137738] 
A clique is a set of Teradata nodes that share a common set of disk arrays. Cabling a subset of nodes to the same disk arrays creates a clique.

- ==++Virtual Storage++== [color=#137738] 
Teradata Virtual Storage (TVS) is designed to allow the Teradata Database to make use of new storage technologies (specifically SSD or Solid State Drives). Teradata virtual storage is software that automatically looks at access patterns and will store data that is accessed more frequently on the faster devices (i.e., SSD) and data that is accessed less frequently on slower disk drives (e.g., HDD – Hard Disk Drives).

- ==++Hot Standby Node++== [color=#137738]
A hot standby node is included in the customers data warehouse to improve availability and maintain performance in case of a node failure. As a member of a clique, it does not normally participate in Teradata operations but can be brought in to compensate for the loss of a node in the clique.

- ==++BYNET++== [color=#137738] 
BYNET handles the internal communication of the Teradata Database. All communication between Parsing Engines and AMPs are done via the BYNET.

In addition to normal database opersation there are options to ensure data integrity and protection you also have an option for back up and recovery.
- ==++Archive/Recovery (Teradata ARC)++== [color=#137738] 
This is a means of archiving data to tape and disk and restoring data to the Teradata Database.

- ==++Teradata Data-Stream Architecture (DSA)++== [color=#137738] 
This has similar functionality to ARC, but generally provides improved performance.

#### Virtual Components
The following items would be considered virtual components which simply means that they eliminate dependency on specialized physical components (virtual processors-Vprocs). The virtual components are a set of software processes that run on a node under Teradata.

- ==++Parsing Engine (PE)++== [color=blue] 
The Parsing Engine, or PE, performs session control, query parsing, security validation, query optimization, and query dispatch. The PE interprets SQL requests and sends the execution plan to the amp through the message passing layer.

- ==++Message Parsing Layer++== [color=blue] 
The Message Passing Layer, MPL, handles the internal communication of the Teradata Database. The MPL is a combination of hardware and software. All communication between Parsing Engines and AMPs is done via the Message Passing Layer.
![](https://i.imgur.com/8wHsQn9.png =300x300)
 The message parsing layer or communications layer is responsible for carrying messages between amps, and PEs, making Teradata parallelism possible, and merging answer sets back to the PE. It is a combination of the PDE, BYNET software, and BYNET Hardware for MPP systems.

- ==++Access Module Processor (AMP)++== [color=blue] 
The Access Module Processor, or AMP, is responsible for managing a portion of the database. Each AMP controls some portion of each table on the system and additionally owns a portion of the overall database storage. AMPs do all of the physical work associated with generating an answer set including, sorting, aggregating, formatting, and converting.

- ==++Virtual Disk Space++== [color=blue] 
Virtual Disk Space is disk space associated with an AMP. Tables/data rows are stored in this space. A virtual disk is usually assigned to two or more disk drives in a disk array.

- ==++Parallel Database Extensions (PDE)++== [color=blue] 
PDE is a software interface layer that lies between the operating system and Teradata Database. PDE supports the parallelism that gives Teradata Database its speed and linear scalability. PDE provides Teradata Database with the ability to:
    - Run in a parallel environment
    - Execute vprocs
    - Manage and proritize Teradata Database workloads
    - Consistently manage memory, I/O, and messaging system interface across multiple OS platforms
    
#### How Teradata uses Space
![](https://i.imgur.com/HNUOfYK.png)
The way the teradata database perform space management is different from most of the database implementations before defining application users and databases the database administrator creates a special administrative user 
and commonly assigns most of the space in the system to that user as administrator user creates additional users and databases, space assigned to those object will be subtracted from the administrator users space as this users and database creates their own objects they will give up some of their space to these new users and databases.Most databases do not handles data this way once space is allocated to a table it cannot be made available again without the database administrator have to do reorganisation and reallocate the space and partition the data
> [color=red]Teradata's approach to space management is flexible, dynamic and requires minimal involvement of the Database Administrator. 

#### Types of spaces
There are three types of space within the Teradata database:

==PERMANENT SPACE (PERM SPACE)==
>- Used for storing the data rows of tables.[color=black]
>- Maximum storage assigned to a user/database.[color=black]
>- Available on-demand.[color=black]
>- Deducted from the owner's perm space.[color=black]

==SPOOL SPACE==
> - Unused perm space.[color=black]
> - Used to hold intermediate query results.[color=black]
> - All databases have an upper limit of spool space.[color=black]

==TEMPORARY SPACE (TEMP SPACE)==
> - Used for global temporary tables.[color=black]
> - Tables created in temp space remain available to the user until their session is terminated.[color=black]

> ==**NOTE:**== [color=red] A database space is the total amount of space available in the database to create and store objects that need permanent space all space assigned to the user/database is equally divided among the AMPs in the system.For Example - If a database was created with 100GB of permanent space and we had 10 AMPs in our system, each AMP would get a limit of 10GB.

### Module-2 : Data Distribution and Access
#### Data Distribution
- The Teradata Database uses hashing to dynamically distribute data across all AMPs. 
- Hashing is the transformation of a string of characters into a usually shorter fixed length value or key which represents the original string. 
- A row hash is result of an algorithm which determines which amp gets the row.

The Teradata databases hash data distribution scheme provide optimised performance with minimal tunning and no manual reorganistaion resulting in lower administration costs and reduced development time.

> ==**NOTE:**== [color=red] For PIs, Teradata Database generates a row hash by hashing the values of the PI columns. The row hash and a sequence number, which is assigned to distinguish between rows with the same row hash within a table, are collectively called a row identifier and uniquely identify each row in a table.

#### Data Access
Teradata can access analytical intelligence quickly and consistently in support of operational bussiness process.
As companies move towards hybrid cloud architectures teradata provides customers database compatibility accross deployment nodes.
The two features that facilitates the ability of end users to access the teradata database:

- ==`Teradata Everywhere`== delivers the flexibility to implement a hybrid architecture with a common database that enables shifting of workloads between environments as bussiness needs evolve supporting the companies changing deployment strategic and economic needs.
- ==`Teradata qery grid`== provides seemless high performance data access processing and moving accross one or more systems in header genius analytical environments.

#### Metadata
Metadata is stored in tables that belong to user **`DBC`** and are reserved for use by the system this information is stored in the data dictionary. The data dictionary contains metadata about the objects in the system like privileges, system events and system usage.Views provides access to the information in the table
> ==**NOTE:**== [color=red] Metadata is the information about the data and objects created by the users.

#### What an Index is and How it is Used
The teradata database has several types of indexes depending on the type of indexe teradata may use it to distribute data or retrieve data to enhance performance 
![](https://i.imgur.com/R7Igv4p.png)

- ==**Primary Index (PI)**==
  Defined when the table is created and is there for two major reasons
  1. To determine data distribution.
  2. Enhance performance.
 
- ==**No Primary Index (NOPI)**==
  A NoPI Table is simply a table without a primary index. NoPI tables are typically used as staging tables for the initial data load.
  
- ==**Secondary Index (SI)**==
  Can be used to enforce uniqueness on a column. The SI also provides an alternate path to access data.
  
- ==**Join Index (JI)**==
  A Join Index is an optional index which may be created by the user to improve performance of complex queries.
  
#### Relationships between Primary Indexes and Primary Keys
|PRIMARY KEY|PRIMARY INDEX|
|-----------|-------------|
|Relational modeling convention which ensures each row to be uniquely identified.|Teradata convention which determines how the row will be stored and accessed.|
|Consists of more or more columns|Consists of more or more columns|
|May not be null and must be unique.|May be unique or non-unique.|
|Logical concept of data modeling.|Provides a physical access path and is also a mechanism for determining where the data is stored.|
> ==**NOTE:**== [color=red] A primary key is a logical database concept. It may not be the best column, or columns, to choose as a primary index for a table.

#### How the Teradata Database Uses Indexes
![](https://i.imgur.com/TsbFAid.png)

==**To improve performance :**== Accessing data with equality on PI will result in **`one-AMP`** operation which is extremely fast and efficient. Similar improvement can be seen but the use of other indexes. Indexes can provide an easier and faster way of accessing and locating data and thus reducing unwanted inputs and outputs.
> ==**NOTE:**== [color=red] A good choice of primary index will ensure even data distribution.

#### Index Types


- ==++FUPI (Unique Primary Index)++== [color=blue]
Guarantees uniform distribution of rows, has no duplicate values, and is made up of one or more columns.

- ==++NUPI (non unique primary index)++== [color=blue]
Can cause skewed data, may have duplicate values, and is made up of one or more columns.

- ==++USI (Unique Secondary Index)++== [color=blue]
Not involved in data diststribution, has no duplicate values, enables data access via an alternate path.

- ==++NUSI ( non unique secondary index)++== [color=blue]
One or more columns, may have duplicate values and is used to improve access.

- ==++PPI (Partition Primary Index)++== [color=blue]
Can dramatically improve the performance of complex Range-based queries. Partitioned Primary Index (PPI) is an indexing mechanism that is useful in improving the performance of certain queries. When rows are inserted into a table, they are stored in an AMP and arranged by their row hash order. When a table is defined with PPI, the rows are sorted by their partition number. Within each partition, they are arranged by their row hash. Rows are assigned to a partition based on the partition expression defined.

- ==++NOPI++== [color=blue]
No Primary Index: Support faster loads and inserts into tables with no primary index defined.

#### Types, Levels and Functionality of Locking
Locking prevents multiple users who are trying to change the same data at the same time from violating the data's integrity. Locks are automatically acquired during the processing of a request and released at the termination of the request.
In addition user can specify locks, with appropriate privileges the users can upgarde or downgrade the system assigned lock by using a locking request modifier.
There are four types of Locks in Teradata:
- ==++Exclusive locks++:-== Exclusive locks are only applied to databases or tables never to rows and they are the most restrictive type of lock, rarely used exclusive locks are the most often used when structural changes are being made to the database.
   >prevents any other type of concurrent access
- ==++Write locks++:-== Write locks enable users to modify data while locking all other users except access lock readers.
   >prevents other Reads, Writes, and Exclusives
- ==++Read locks++:-== Read lock ensures consistency during read operations, several users may held concurrent read locks on the same data during which time no modification of the data can occur.
   >prevents other Writes and Exclusives
- ==++Access locks++:-== The use of an access lock access allows reading data while modifications are being made. Access locks are sometimes called dirty read locks.
  >prevents Exclusive only

Locks may be applies at four levels:

- `Database level` applies to all Tables/Views in the Database
- `Table/View level` applies to all Rows in the Table/View
- `Partition level` applies to all rows within the specified partition(s)
- `Row hash level`  the result of an algorithm which determines which AMP gets the row

### Module-3 : Security and Privacy

- **==++Privileges++ :==** Privileges sometimes referred to as access rights define the type of activities you can perform during a session. Users can access only database objects for which they have privileges.
    
    There are four types of privileges:
    - **++Automatic Privileges++ :**  Privileges which are privileges provided by the system to the creator of a database or a newly created user or database. 
    - **++Explicit privileges++ :**  Privileges are privileges granted explicitly to a user or database or to a role, then that role to one or more users. 
    - **++Implicit (ownership) privileges++ :** Privileges are granted by the database to the owner of the space in which database objects are created. 
    - **++Inherited privileges++ :** Privileges are passed on indirectly to a user based on its relationship to another user or role to which the privileges were granted directly.

- **==++Role++ :==** A Role is an administration/security concept which can help simplify database administration. Roles are simply used to define access rights and privileges on database objects.
  
  When multiple users require access rights to the same database objects, a “fictitious” user can be set up and be assigned access rights to those objects. Then that role can be assigned to the multiple users.
  
- **==++User++ :==** A user is almost the same as a database except that a user can actually log on to the Teradata Database. To accomplish this, a user must have a password. A user can log onto the system using an id and password whereas a database cannot.

- **==++Middle-tier applications++ :==** Middle-tier applications may stand between end users and Teradata Database, accepting requests from users, processing them and eventually returning results to the users. The middle-tier application logs on to the database, is authenticated as a permanent database user, and establishes a connection pool. The application is then responsible for authenticating the individual application end users.


- **==++Security Features++ :==** In life we have so many passwords to keep track of, and probably a lot of us keep them on a spreadsheet or other document. However this, as we know, is really not secure. Teradata wallet storage is beneficial for easy retrieval of passwords on application servers or other shared computers that host multiple users and connect to multiple databases.


- **==++External Roles++ :==** External roles are different from internal roles. External roles are mapped to users on the directory server. For example LDAP.


- **==++Profiles++ :==** Profiles define system attributes such as account (ids), default database, spool space allocation, temporary space allocation, password attributes, and QueryBand.
 
  A profile is a set of common user attributes that can be applied to a group of users. Using profiles is very helpful for the Database Administrator (DBA) since profiles make changing parameters for a group of users a single step. Change the profile and all users assigned that profile will be changed! Without the profile, each user in the group would need to be changed individually.


- **==++Authentication++ :==** Authentication is the process by which the user identity in the login is verified. There are two categories of authentication that are available. Authentication by Teradata Database requires that the user and its privileges are defined in the database and external Authentication which allows Teradata Database users to be authenticated by an agent running on the same network as Teradata Database and its clients.

#### Privacy Mechanisms
The Teradata Secure Zones feature allows you to create one or more exclusive database hierarchies called Zones put in a single Teradata database system . Access to data in each zone and the database administration is handled seperately from the overall teradata database system and from other zones.

**++Secure Zones++** are useful in situations where the access to data must be tightly controlled and restricted.

**++Row Level Security (RLS)++** is used to control user access by table row and by SQL operation which results in the user only being able to view certain rows in a table.

### Module 4 - Teradata Tools and Utilities
#### Data Integration Tools
Teradata load and unload utilities:
- Manage data load requirements from batch to real-time.
- Parallel architecture helps in providing optimal and scalable performance.
- Allow import and export of data to and from host-based and client-resident data sources.

Teradata Parallel Transporter (TPT) is client software that performs:
- `Data extractions`
- `Data transformations`
- `Data loading functions`
 
Jobs in TPT are one using operators which define the type of activity to be performed. For Example - It can read informaton from an excel spreadsheet and using the TPT update operator loaded into a table in the database.

The two key operator types in TPT are : 
- **==Producer operators==** extract data from a data source by reading the data and writing it to the data stream.
  - The **++Export operator++** is a producer type operator that is designed to extract large volumes of data at high speed from teradata tables and write them to an external targets.
- **==Consumer operators==** read the data from the data stream and writes or loads it to the target which may be teradata tables or an external data store.
   -  The **++load operator++** is a consumer type operator that is typically used for initial loading of teradata tables. The load operator inserts the data it consumes from the data streams into individual roles of the target table. Inserting is the only operation supported by load operator.
   -  The **++update operator++** is consumer type operator that can be used to insert new rows into the database unlike the load operator it can also perform  updates, deletes and inserts to the target tables its primary function is to perform high volume maintenance transaction against multiple teradata tables.
   -  The **++Stream operator++** is a consumer operator which performs a high speed parallel inserts, updates and deletes in near real time to one or more empty or pre existing teradata database tables without locking the target tables.

![](https://i.imgur.com/dhYRHKK.png)

> ==**NOTE:**== [color=red] Batch/Basic Teradata Query Language, BTEQ is a general-purpose command-based utility for submitting SQLrequests to the Teradata Database and deliver the response in the format required. BTEQ can be used for both exporting and importing data.

#### UDA Tools
|Listener|
|---------|
|Listener is an enterprise wide platform for ingesting high volume real-time streams of data. It is used to capture and control large volumes of real-time streams from any source such as websites, social feeds, systems and application logs.|

#### Legacy Tools
|FastLoad (TPT - Load Operator)|
|--------|
|This utitlity provides high-performance data loading from client files into empty tables.|

|MultiLoad (TPT - Update Operator)|
|---------|------|
|The multiload utility provides high-performance data maintenance, including inserts, updates, and deletions to existing tables.|

|TPump- Parallel Data Pump (TPT - Strean Operator)|
|--------------------------|
|Provides continuous updates of tables; performs insert, update, and delete operations or a combination of those operations on multiple tables using the same source feed.|


#### Administration and Monitoring Tools

- ==Teradata Viewpoint== [color= red]
   - Allows users to view systems information such as query process, performance data and system saturation and health through preconfigured portlets displayed from within the teradata viewpoint portal.
   - Allows monitoring and managing of Teradata Database systems from anywhere using a standard web browser. It is intended to provide customers with a single operational view of all teradata, teradata aster and teradata hadoop systems.
- ==Teradata Studio Family== [color=red]
  - Consists of two client tools: Teradata Studio, and Teradata Studio Express.
     + **++Studio:++** Targeted for DBAs,is a client base GUI for performing databases administration, query development and management task on teradata databases, teradata aster databases and hadoop systems. Some of the most common uses are to load, extract and export results to Excel, XML, or text files.
     + **++Express:++** Base level product for business Users and Sequel Developers, used as an information discovery tool for retrieving and displaying data from teradata databse systems. Its main use is for running SQL statements and displaying results set data and storing SQL execution history
   - In addition to those already mentioned, Teradata Studio allows you to:
      - Build and edit SQL requests visually using SQL Query Builder
      - Generate and run COLLECT STATISTICS requests
      - Copy database objects to another database or system
      - Move space between databases

- ==TASM (Teradata Active Systems Management)== [color=red]
 TASM is a set of products that interact with each other to facilitate automation in four key areas:
    - Workload management
    - Performance tuning
    - Capacity planning
    - Performance monitoring
- ==Teradata Unity== [color=red]
 Unity's powerful features directly address and overcome the challenges organizations face in a multi-system environment. It automates and simplifies tasks enabling corporations to manage multiple active Teradata systems so they appear as one ecosytem.
 
 #### Quiz

1. Macros reduce your number of keystrokes.
   - [x] True
   - [ ] False
2. The Access Module Processor, is responsible for managing the entire database.
   - [ ]True
   - [x]False
3. The ________ is designed to support in-database analytics.
    - [ ]Teradata Warehouse
    - [x]Teradata Database
    - [ ]scheme
    - [ ]primary key