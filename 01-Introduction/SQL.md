# SQL (Structured Query Language):

- SQL is a standardized language used for managing relational databases.
- It provides a set of commands for querying, updating, and managing data in relational database management systems (RDBMS).
- SQL is an ANSI/ISO standard language. However, different database management systems may implement SQL slightly differently, resulting in variations in syntax and functionality.

### Features:

1. Data Definition Language (DDL):
   - Allows defining and modifying database schemas, such as creating tables, altering table structures, and defining constraints.
2. Data Manipulation Language (DML):
   - Provides commands for querying and modifying data, such as SELECT, INSERT, UPDATE, and DELETE.
3. Data Control Language (DCL):
   - Manages user access permissions and security settings, such as GRANT and REVOKE.
4. Transaction Control Language (TCL):
   - Controls transactions within the database, such as COMMIT, ROLLBACK, and SAVEPOINT.

# MySQL:

- MySQL is an open-source relational database management system (RDBMS) that uses SQL as its query language.
- It is one of the most popular RDBMS used for web applications, especially in the LAMP (Linux, Apache, MySQL, PHP/Python/Perl) stack.
- MySQL was originally developed by MySQL AB, which was later acquired by Sun Microsystems in 2008. Sun Microsystems was subsequently acquired by Oracle Corporation in 2010. MySQL is now owned and maintained by Oracle.

### Features:

1. Data Storage: Stores data in tables with rows and columns, following the relational model.
2. SQL Compatibility: Supports standard SQL commands and syntax, along with additional features specific to MySQL.
3. Performance: Known for its fast performance, scalability, and reliability.
4. Community and Ecosystem: Has a large and active community of developers, along with extensive documentation and support resources.
5. Storage Engines: Supports multiple storage engines, such as InnoDB (default), MyISAM, and MEMORY, each with its own advantages and use cases.
6. Security: Provides features for user authentication, access control, and encryption to ensure data security.

### Differences Between SQL and MySQL:

1. Scope:

   - SQL: Refers to the language itself, which is used to interact with relational databases.
   - MySQL: Refers to a specific relational database management system that implements SQL.

2. Standardization:

   - SQL: Standardized language defined by ANSI/ISO.
   - MySQL: Implements SQL along with additional features and optimizations specific to MySQL.

3. Usage:

   - SQL: Can be used with any relational database management system that supports SQL.
   - MySQL: Is a specific RDBMS that uses SQL as its query language.

4. Ownership:

   - SQL: Not owned by any specific company or organization; it's a standardized language.
   - MySQL: Owned and maintained by Oracle Corporation.

5. Implementation:
   - SQL: Specifies the syntax and semantics of commands for managing relational databases.
   - MySQL: Implements SQL commands and provides additional features, optimizations, and tools specific to MySQL.

### MYSQL Installation Guide

- Step-by-step guide to installing and setting up MySQL on a Windows PC, along with basic configuration and security settings:

1. Download MySQL Installer:
   - Go to the MySQL Community Downloads page.
   - Scroll down to find the MySQL Community Server section.
   - Click on "Download" for the MySQL Installer appropriate for your Windows version.
2. Run MySQL Installer:
   - Once the installer is downloaded, double-click on it to run it.
   - If prompted by User Account Control (UAC), click "Yes" to allow the installer to make changes to your device.
3. Choose Installation Type:
   - In the MySQL Installer window, select "Custom" installation type.
   - Click "Next" to proceed.
4. Select Products:
   - In the Product Selection window, select "MySQL Server" from the list of available products.
   - Optionally, you can also select other components such as MySQL Workbench for database administration.
   - Click "Next" to proceed.
5. Installation:
   - In the Installation window, click "Execute" to begin the installation process.
   - The installer will download and install the selected MySQL components.
6. Configure MySQL Server:
   - After installation, the Configuration window will appear.
   - Choose a setup type:
     - Standalone MySQL Server/Classic MySQL Replication: Suitable for most users.
     - InnoDB Cluster: For advanced users requiring high availability and scalability.
     - Click "Next" to proceed.
7. Configuration Type:
   - Select "Development Computer" or "Server Machine" depending on your intended use.
   - Click "Next" to proceed.
8. Database Configuration:
   - Choose the default authentication method:
   - Use Strong Password Encryption: Recommended for improved security.
   - Set a root password for the MySQL server.
   - Click "Next" to proceed.
9. Windows Service:
   - Choose whether to configure MySQL Server as a Windows service.
   - Provide a service name and configure the service startup type.
   - Click "Next" to proceed.
10. Apply Configuration:
    - Review the configuration settings.
    - Click "Execute" to apply the configuration and start the MySQL Server.
11. Complete Installation:
    - Once the configuration is applied, click "Finish" to complete the installation process.
12. Verify Installation:
    - Open MySQL Command Line Client or MySQL Workbench.
    - Log in using the root username and the password you set during installation.
    - Verify that you can connect to the MySQL server successfully.

#### NOTE :

- Ensure that you have set a strong password for the root user during installation.
- Create additional MySQL users with restricted privileges for specific tasks if required.
