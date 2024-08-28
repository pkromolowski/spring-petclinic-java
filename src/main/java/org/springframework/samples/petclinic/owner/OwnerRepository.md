## Documentation of OwnerRepository.java

**Overview:**

The `OwnerRepository` interface defines the data access methods for managing `Owner` objects within a Spring Data JPA application. It leverages Spring Data's conventions to provide a clean and concise way to interact with the database.

**Dependencies:**

* **Spring Data JPA:** Provides the foundation for interacting with the database using JPA.
* **JPA Entity:** The `Owner` entity, which defines the structure of the `Owner` objects stored in the database.

**Methods:**

1. **`findPetTypes()`:**
   * **Description:** Retrieves all `PetType` objects from the database and orders them alphabetically by name.
   * **Parameters:** None.
   * **Return Value:** A `List` of `PetType` objects.
   * **Logic:** Uses a JPQL query (`SELECT ptype FROM PetType ptype ORDER BY ptype.name`) to fetch all `PetType` objects and orders them by their name property.

2. **`findByLastName(String lastName, Pageable pageable)`:**
   * **Description:** Finds all `Owner` objects whose last name starts with the given `lastName`. Uses pagination for efficient retrieval of large result sets.
   * **Parameters:**
      * `lastName`: The last name to search for.
      * `pageable`: A `Pageable` object that specifies the page and size of the results.
   * **Return Value:** A `Page` of `Owner` objects matching the search criteria.
   * **Logic:**
      * Uses a JPQL query (`SELECT DISTINCT owner FROM Owner owner left join  owner.pets WHERE owner.lastName LIKE :lastName% `) to find owners with matching last names.
      * The `:lastName` parameter is populated with the input `lastName`.
      * The `Pageable` object is used to control the pagination of the results.

3. **`findById(Integer id)`:**
   * **Description:** Retrieves a single `Owner` object by its ID.
   * **Parameters:**
      * `id`: The ID of the `Owner` object to retrieve.
   * **Return Value:** An `Owner` object with the matching ID.
   * **Logic:**
      * Uses a JPQL query (`SELECT owner FROM Owner owner left join fetch owner.pets WHERE owner.id =:id`) to find the owner by ID.
      * The `:id` parameter is populated with the input `id`.
      * The `left join fetch owner.pets` clause ensures that the associated `Pet` objects are also fetched, avoiding a separate query.

4. **`save(Owner owner)`:**
   * **Description:** Saves an `Owner` object to the database, either creating a new entry or updating an existing one.
   * **Parameters:**
      * `owner`: The `Owner` object to save.
   * **Return Value:** None.
   * **Logic:** Spring Data JPA automatically handles the persistence logic based on the provided `Owner` object.


5. **`findAll(Pageable pageable)`:**
   * **Description:** Retrieves all `Owner` objects from the database using pagination.
   * **Parameters:**
      * `pageable`: A `Pageable` object that specifies the page and size of the results.
   * **Return Value:** A `Page` of `Owner` objects.
   * **Logic:** Uses a JPQL query to retrieve all `Owner` objects and applies pagination based on the provided `Pageable` object.

**Data Structures:**

* **`Owner`:** A JPA entity representing an owner, containing properties like name, address, phone number, etc.
* **`PetType`:** A JPA entity representing a type of pet (e.g., "Dog", "Cat", "Bird").

**Assumptions:**

* The `Owner` entity has a relationship with the `PetType` entity.

* The database schema is properly configured to support the `Owner` and `PetType` entities.



**Pseudo Code:**

1. **Initialization:**
    * Define the `OwnerRepository` interface.
2. **`findPetTypes()` Method:**
    * Query the database for all `PetType` objects.
    * Order the results alphabetically by name.
    * Return the list of `PetType` objects.
3. **`findByLastName(String lastName, Pageable pageable)` Method:**
    * Query the database for all `Owner` objects whose last name starts with the given `lastName`.
    * Apply pagination using the provided `Pageable` object.
    * Return a `Page` of `Owner` objects.
4. **`findById(Integer id)` Method:**
    * Query the database for an `Owner` object with the given `id`.
    * Include associated `Pet` objects using a join fetch.
    * Return the `Owner` object.
5. **`save(Owner owner)` Method:**
    * Use Spring Data JPA to save the `Owner` object to the database.
6. **`findAll(Pageable pageable)` Method:**
    * Query the database for all `Owner` objects.
    * Apply pagination using the provided `Pageable` object.
    * Return a `Page` of `Owner` objects.



