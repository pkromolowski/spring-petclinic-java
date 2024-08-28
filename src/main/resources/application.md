## Documentation of `application.properties`

This file defines configuration settings for a Spring Boot application. It uses the standard Spring Boot property format, where keys are properties and values are their corresponding settings.

**Overview:**

The file configures various aspects of the application, including database connection, web server settings, JPA configuration, internationalization, actuator endpoints, logging, and static resource caching.

**Key Properties and Settings:**

* **Database Configuration:**
    * `database`: Specifies the database dialect used (h2 in this case).
    * `spring.sql.init.schema-locations`: Defines the location of schema SQL files for database initialization.
    * `spring.sql.init.data-locations`: Defines the location of data SQL files for database initialization.

* **Web Server Configuration:**
    * `spring.thymeleaf.mode`: Sets the Thymeleaf template mode to HTML.

* **JPA Configuration:**
    * `spring.jpa.hibernate.ddl-auto`: Configures Hibernate to not automatically create or update the database schema (set to `none`).
    * `spring.jpa.open-in-view`: Enables opening the JPA EntityManager in the view.

* **Internationalization:**
    * `spring.messages.basename`: Specifies the base name for message property files.

* **Actuator Configuration:**
    * `management.endpoints.web.exposure.include=*`: Exposes all actuator endpoints.

* **Logging Configuration:**
    * `logging.level.org.springframework`: Sets the logging level for the Spring framework to INFO.

* **Static Resource Caching:**
    * `spring.web.resources.cache.cachecontrol.max-age`: Sets the maximum age for cached static resources to 12 hours.



**Dependencies:**

* **Spring Boot Framework:** This file relies on the Spring Boot framework for property loading and configuration.

**Pseudo Code:**

1. **Load Properties:**
   - Read the content of `application.properties` file.
2. **Parse Properties:**
   - Iterate through each line in the file.
   - Split each line into key-value pairs.
3. **Apply Configurations:**
   - Set the database configuration based on the `database` property.
   - Configure web server settings using properties like `spring.thymeleaf.mode`.
   - Configure JPA settings using properties like `spring.jpa.hibernate.ddl-auto` and `spring.jpa.open-in-view`.
   - Configure internationalization using `spring.messages.basename`.
   - Enable actuator endpoints with `management.endpoints.web.exposure.include=*`.
   - Set logging levels based on `logging.level.*` properties.
   - Configure static resource caching using `spring.web.resources.cache.cachecontrol.max-age`.



