# What is SQL?
SQL (Structured Query Language) is a standardized programming language used for managing and manipulating relational databases. 
It allows users to perform various operations on data stored in a database, such as querying, updating, inserting, and deleting records. 
SQL is widely used in database management systems like MySQL, PostgreSQL, Oracle, SQL Server, and SQLite.
## Key Features:
**Data Querying:** Retrieve data from a database using the SELECT statement.

**Data Manipulation:** Insert (INSERT), update (UPDATE), and delete (DELETE) data.

**Data Definition:** Define and modify database structures using commands like CREATE, ALTER, and DROP.

**Data Control:** Manage access to data using GRANT and REVOKE statements.

# What is MariaDB?
MariaDB is an open-source relational database management system (RDBMS) that is a fork of MySQL. 
It was created by the original developers of MySQL in response to concerns over its acquisition by Oracle Corporation. 
MariaDB aims to maintain high compatibility with MySQL while offering additional features, performance improvements, and enhanced security.

## Key Features:
**Open Source:** MariaDB is freely available under the GNU General Public License.

**High Compatibility:** MariaDB is designed to be a drop-in replacement for MySQL, meaning most MySQL applications can work with MariaDB without modification.

**Performance Improvements:** MariaDB includes optimizations and enhancements that can lead to better performance compared to MySQL.

**Storage Engines:** MariaDB supports multiple storage engines, including InnoDB, MyRocks, Aria, and ColumnStore, allowing for flexibility in how data is stored and accessed.

**Security Enhancements:** MariaDB includes additional security features, such as more robust authentication mechanisms and data encryption options.

**Active Development:** MariaDB has a strong community and active development, ensuring regular updates and new features.

# _Concise Comparision of MariaDB & MySQL_

**• Licensing**

*MariaDB:* Fully open-source (GPL).

*MySQL:* Open-source but has proprietary features under Oracle.

**• Development**

*MariaDB:* Community-driven, developed by MySQL’s original creators.

*MySQL:* Owned and maintained by Oracle.

**• Performance**

*MariaDB:* Faster due to optimizations (e.g., better query handling, replication).

*MySQL:* Solid but may lag in advanced workloads.

**• Features**

*MariaDB:* More storage engines (e.g., Aria, ColumnStore), Galera Cluster, advanced JSON support.

*MySQL:* Focuses on enterprise tools (e.g., MySQL Enterprise Backup).

**• Compatibility**

*MariaDB:* Drop-in replacement for MySQL.

*MySQL:* Not fully compatible with MariaDB-specific features.

**• Security**

*MariaDB:* More frequent updates, additional plugins (e.g., ed25519).

*MySQL:* Robust but less innovative.

**_When to Use_**

*MariaDB:* Open-source, performance, advanced features.

*MySQL:* Enterprise needs, Oracle ecosystem.

In short, **MariaDB** is more modern and open-source, while MySQL is enterprise-focused with Oracle support.
