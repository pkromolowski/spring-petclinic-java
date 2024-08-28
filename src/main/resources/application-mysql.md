## Documentation of `application-mysql.properties`

This file defines configuration settings specific to using a MySQL database for the Spring PetClinic application. It builds upon the general `application.properties` file by providing database connection details and initialization parameters.

**Overview:**

The file configures the MySQL database connection, including URL, username, password, and initialization mode. It overrides the general database configuration from `application.properties` to ensure compatibility with MySQL.

**Key Properties and Settings:**

* `database`: Specifies the database dialect used (MySQL in this case).
* `spring.datasource.url`: Defines the JDBC URL for connecting to the MySQL database. It uses environment variables `MYSQL_URL` for flexibility.
* `spring.datasource.username`: Specifies the username for accessing the MySQL database. It uses environment variable `MYSQL_USER` for flexibility.
* `spring.datasource.password`: Specifies the password for accessing the MySQL database. It uses environment variable `MYSQL_PASS` for flexibility.
* `spring.sql.init.mode`: Configures the database initialization mode. Set to `always` to ensure database initialization occurs on startup, regardless of existing schema.

**Dependencies:**

* **MySQL Database:** This file assumes the MySQL database is installed and running.
* **Spring Boot Framework:** This file relies on the Spring Boot framework for property loading and database configuration.



**Pseudo Code:**

1. **Load Properties:** Read the content of `application-mysql.properties` file.
2. **Database Configuration:**
   - Set `database` to `mysql`.
   - Extract `MYSQL_URL`, `MYSQL_USER`, and `MYSQL_PASS` from environment variables.
   - Set `spring.datasource.url`, `spring.datasource.username`, and `spring.datasource.password` using the extracted values.
3. **Initialization:**
   - Set `spring.sql.init.mode` to `always`.



