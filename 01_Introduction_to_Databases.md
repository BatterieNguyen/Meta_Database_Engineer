
### Database
`A database is a form of electronic storage in which data is organized systematically.`

### Different types of databases
Relational databases
- Used for storing structured data in tabular format

NoSQL (No sequel database)
- provide a flexible structure for storing and scaling data
- Ex: used by social media platforms / IoT / AI / and other applicatons than generate massive amounts
- Types: Document databases (Json) / Key-value databases / Graph databases / Wide-column databases
- Advantages: Higher scalability / distributed / lower cost / a flexible schema / no complex relationships

Big data
- Complex data that grows exponentially with time
- Combination of structured / semi-structured / unstructured data
- More powerful than traditional data when solving problems
- Provide unique insights to help improve decision making

Cloud hosting
- avoid dealing with lack of infrastructure, maintenance, and storage costs
- more affordable solution

Business Intelligence
- Analyze data and other information to make informed decisions

Flat files
- store data in a signle file or table, not multiple tables
- basically text file, where every line contains 1 record and fields either have fixed lengths or are separated y commas / whitespaces / tabs

Object-oriented databases (OO)
- work in the framework of real programming languages (Java / C++)

----------------
## Module 4 - Database Design

Schema - `Organization of information and its relatinships`

Database Schema - `Collection of data structures within a database`
- In SQLServer, Schema is a collection of individual, but related, components (tables / fields / datatypes / keys)
- In PostgresSQL, Schema is a namespace with named databse objects (views / indexes / functions)
- In Oracle, Schema is assigned to each user

Advantages of a database schema
- Management (provide logical grouping for objects)
- Accessibility (enable greater accessibility to objects)
- Security (offer a range of useful security features)
- Ownership (Permit transfer of ownership between users)

Relational Model (table relationship)
- One-to-many
- One-to-one
- Many-to-many

Database Normalization - `Process for structuring tables that minimizes challenges facing database systems`
- Challenges of Noramlization
  - Insert anomaly - Insertion of one records leads to the insertion of several more required data sets.
  - Update anomaly - Updating a record in a table column requires further updates in other columns.
  - Deletion anomaly - Deletion of one record leads to the deletion of several more required    data sets
- Fundamental normalization forms
  - First Normal Form (1NF) - enforce data atomicity and eliminate unnecessary repeating groups of data in database tables.
    - Data atomicity - `Ensuring that there is only one single instance value per column field`
  - Second Normal Form (2NF) - avoid partial dependency relationships between data
    - Partial dependency - `A table with a composite primary key`
    - Functional dependency - `The relationship between 2 attributes in a table`
  - Thrid Normal Form (3NF) - avoid transitive dependency
    - Transitive dependency - `A non-key attribute cannot be functionally dependent on another non-key attribute.`







