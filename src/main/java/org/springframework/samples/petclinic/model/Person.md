## Documentation for Person.java

**Overview:**

The `Person` class represents a person in the application. It inherits from the `BaseEntity` class, meaning it has an `id` property for identification. It also has properties for `firstName` and `lastName`.

**Methods:**

1. **`getFirstName()`:**
   - **Purpose:** Returns the first name of the person.
   - **Parameters:** None.
   - **Return Value:** A `String` representing the person's first name.

2. **`setFirstName(String firstName)`:**
   - **Purpose:** Sets the first name of the person.
   - **Parameters:**
     - `firstName`: A `String` representing the new first name.
   - **Return Value:** None.

3. **`getLastName()`:**
   - **Purpose:** Returns the last name of the person.
   - **Parameters:** None.
   - **Return Value:** A `String` representing the person's last name.

4. **`setLastName(String lastName)`:**
   - **Purpose:** Sets the last name of the person.
   - **Parameters:**
     - `lastName`: A `String` representing the new last name.
   - **Return Value:** None.

**Data Structures:**

* **`String firstName`:** A string variable holding the person's first name.
* **`String lastName`:** A string variable holding the person's last name.

**Dependencies:**

* **Jakarta Persistence API (JPA):**  Provides annotations and interfaces for object-relational mapping (ORM).
* **Jakarta Validation API:** Provides annotations for validating data, such as `@NotBlank`.

**Assumptions:**

* The database schema includes tables with columns for `first_name` and `last_name` to store person names.



**Pseudo Code:**

```
// Person Class

// Method getFirstName
  - Return the value of the 'firstName' variable

// Method setFirstName
  - Set the value of the 'firstName' variable to the input 'firstName'

// Method getLastName
  - Return the value of the 'lastName' variable

// Method setLastName
  - Set the value of the 'lastName' variable to the input 'lastName'



```



