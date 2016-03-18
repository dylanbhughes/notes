# Databases

* 3 Parts
  * Motivating Databases
  * SQL
  * DB Project
* Things to note
  * follow the times allotted
  * We will watch videos in the lecture hall
  * Be sure to update the town hall spreadsheet

## Database Lecture 1
  * Spreadsheets
    * they're a thing
    * I assume they're sort of like DB tables
  * Motivations
    * persistence
    * structure
    * relationships
    * organization
  * Key
    * Two kinds of keys
    * Primary key
      * unique identifier
      * usually an incremented number of some kind
    * Foreign key
      * primary key from another table that creates a relationship
  * "Give me all of the orders that customer 123 has done"
    * Select * from orders where customer=123
  * Aside
    * you can have multiple servers because each database has the same schema
    * you can use each server to track one segment of your customer base
  * Types of relationships
    * one to one
    * one to many
    * many to many - needs a join table
  * Indexes
    * A way to create an efficiency around a lookup that makes them quickly
    * SQL db's can create some automatically but when DB's get to a certain size we may need to set some ourself
  * Normalization and normal forms
    * You should always shoot for normalization
  * CRUD
    * Create
    * Read
    * Update
    * Delete

## Database Town Hall

* MapReduce
  * Kind of its own query language
* http://xkcd.com/327/ <- this is everything
* 4 Kinds of NoSQL DB
  * GraphDB
  * Key/Value Store
  * Document Store
  * ColumnStore

## Database Lecture 2: SQL

* CRUD
* SQLite
  * Doesn't understand CREATE DATABASE because it's only working with like one file.
```sql
// Implicit CREATE DATABASE foobar;
CREATE TABLE foobar (
  id INTEGER PRIMARY KEY ASC,
  name VARCHAR(100),
  age INTEGER DEFAULT 35 NOT NULL,
  bazID INTEGER,
  FOREIGN KEY (bazID) REFERENCES baz(id)
);

INSERT INTO foobar ("hello", 42);

SELECT name, age FROM foobar WHERE age > 40 OR name IS NULL ORDER BY age DESC;

UPDATE foodbar SET age = age + 1 WHERE age > 40;

DELETE FROM foobar WHERE age > 50;

/* end up with records that match up on both tables */
SELECT * FROM a INNER JOIN b;

SELECT * FROM a LEFT OUTER JOIN b ON a.foo = b.bar;

/* An inner join will only select records where the joined keys are in both specified tables. A left outer join will select all records from the first table, and any records in the second table that match the joined keys */

```
















/
