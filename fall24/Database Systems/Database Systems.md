---
Created: 2024-09-03T14:31
Class: CSCI 3100
---
**Database** - server that stores data

**Server** - thing that provides a service (awful definition)

**DBMS** - database management system

### Big Wigs

- MySQL
- SQL Server
- Oracle
- DBII
- Postgres
- SQLite
- SAP

  

**ERP** - enterprise resource planning; built on top of a DBMS

- made up of integrated modules or business applications that talk to each other and share common a database

  

## DBMS

Software on your computer which provides:

- Network access
- Storage and organization of data
- Security of data
- Management of users
- Clusterification

SQL (Structured Query Language) is the standard language for managing and manipulating relational databases. It provides a set of commands for various database operations, including:

- Data retrieval and filtering
- Data insertion, updating, and deletion
- Database schema creation and modification

DML (Data Manipulation Language) - used for querying and modifying data

DDL (Data Definition Language) - used for defining and managing database structures

> [!important]  
> Both DML and DDL are subsets of SQL, each serving distinct purposes in database management.  

  

Users access a **web server** which contacts the **database** to return results.

When there are enough users to overload the web server, you can just create another copy of the web server for users to access and they both point to the database.

However, when the database gets overloaded, you can’t simply copy over the database, because it contains data which is constantly changing.

To combat this, you create one server which acts as a manager. It will connect to each database to retrieve consistent information. Then, users will connect to the manager server.

SAN - a storage area network specifically made just for storing data

  

> [!important]  
> The output of PHP is HTML!  

## HTML

- It IS a language, but it’s not a programming language.
    - A programming language is _==Turing complete.==_
- HTML is a _markup_ language.
    - You can add markup to text which tells you information about how the text should be displayed.
    - It is derived from SGML (Standard Generalized Markup Language)

```HTML
<!-- Name is a tag -->
<name>content</name>

<name attributes>content</name>
<!-- attributes are formatted as: key=value, key=value-->
```

### Forms

Forms are spaces on HTML pages that can receive user input.

- `action` - where to send the information (what page will process the data)
    - Usually a `php` file, which isn’t displayed to the user
- `method` - specified the HTTP method to be used when submitting the form data
    - GET
    - POST
- `label` - labels an input field. used for describing an input field
    - If you link it to an input label using the `for` attribute, when you click on the label, it will focus on the input box.
### Databases

Data is stored in tables (rows and columns) but it's not actually stored in rows and columns?
* How is it actually stored?

#### ER Diagrams
- Used to map out *Entity Relations*.
- ex: Student with all its attributes
	- -> has Phone number
	- attributes are marked by ovals stemming from the box
	- doubled ovals have multiple attributes
	- diamonds represent relations