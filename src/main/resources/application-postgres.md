## Documentation of `application-postgres.properties`

This file defines configuration properties for a Spring Boot application using PostgreSQL as the database. It sets up the database connection details and other relevant parameters.

**Overview:**

The file configures the connection details for the PostgreSQL database, including the URL, username, and password. It also defines the initialization mode for SQL scripts.

**Key Properties:**

* **`database`:** Specifies the database type, set to "postgres" in this case.
* **`spring.datasource.url`:** Defines the URL for connecting to the PostgreSQL database. It uses the `POSTGRES_URL` environment variable, defaulting to `jdbc:postgresql://localhost/petclinic`.
* **`spring.datasource.username`:** Specifies the username for accessing the PostgreSQL database. It uses the `POSTGRES_USER` environment variable, defaulting to "petclinic".
* **`spring.datasource.password`:** Defines the password for accessing the PostgreSQL database. It uses the `POSTGRES_PASS` environment variable, defaulting to "petclinic".
* **`spring.sql.init.mode`:** Sets the mode for SQL script initialization. It's set to "always", ensuring that SQL scripts are executed every time the application starts.


**Pseudo Code:**

1. **Database Connection:**
   - Retrieve the value of the `POSTGRES_URL`, `POSTGRES_USER`, and `POSTGRES_PASS` environment variables.
   - Construct the database connection URL using the retrieved values.
   - Establish a connection to the PostgreSQL database using the constructed URL and credentials.
2. **SQL Initialization:**
   - Execute any defined SQL scripts based on the `spring.sql.init.mode` setting ("always" in this case).



**Dependencies:**

* **PostgreSQL Driver:** The application requires the PostgreSQL JDBC driver (`org.postgresql:postgresql`) to connect to the database.

* **Spring Boot Framework:** The application leverages the Spring Boot framework for dependency management, configuration, and application execution.



