## Documentation for Owner.java

**Overview:**

The `Owner` class represents an owner in a pet clinic system. It extends the `Person` class and adds specific attributes related to an owner, such as address, city, telephone, and a list of associated `Pet` objects.

**Data Structures:**

* **Owner:** Represents an owner in the system, inheriting from the `Person` class. It contains attributes like address, city, telephone, and a list of pets.
* **Pet:** Represents a pet owned by an owner.

**Variables:**

* **address:**  The owner's address (String).
* **city:** The owner's city (String).
* **telephone:** The owner's telephone number (String).
* **pets:** A list of `Pet` objects owned by this owner (List<Pet>).

**Methods:**

1. **`getAddress()`:**
   - **Purpose:** Returns the owner's address.
   - **Parameters:** None.
   - **Return Value:** String - The owner's address.

2. **`setAddress(String address)`:**
   - **Purpose:** Sets the owner's address.
   - **Parameters:**
     - `address`: The new address for the owner.
   - **Return Value:** None.

3. **`getCity()`:**
   - **Purpose:** Returns the owner's city.
   - **Parameters:** None.
   - **Return Value:** String - The owner's city.

4. **`setCity(String city)`:**
   - **Purpose:** Sets the owner's city.
   - **Parameters:**
     - `city`: The new city for the owner.
   - **Return Value:** None.

5. **`getTelephone()`:**
   - **Purpose:** Returns the owner's telephone number.
   - **Parameters:** None.
   - **Return Value:** String - The owner's telephone number.

6. **`setTelephone(String telephone)`:**
   - **Purpose:** Sets the owner's telephone number.
   - **Parameters:**
     - `telephone`: The new telephone number for the owner.
   - **Return Value:** None.

7. **`getPets()`:**
   - **Purpose:** Returns the list of `Pet` objects owned by this owner.
   - **Parameters:** None.
   - **Return Value:** List<Pet> - A list of `Pet` objects.

8. **`addPet(Pet pet)`:**
   - **Purpose:** Adds a new `Pet` to the owner's list of pets.
   - **Parameters:**
     - `pet`: The `Pet` object to be added.
   - **Return Value:** None.
   - **Logic:** Checks if the pet is new (i.e., not already saved) and adds it to the `pets` list if it is.

9. **`getPet(String name)`:**
   - **Purpose:** Returns the `Pet` with the given name owned by this owner.
   - **Parameters:**
     - `name`: The name of the pet to search for.
   - **Return Value:** Pet - The `Pet` object with the matching name, or null if not found.
   - **Logic:** Iterates through the `pets` list and compares the pet's name to the given name. Returns the matching `Pet` object.

10. **`getPet(Integer id)`:**
   - **Purpose:** Returns the `Pet` with the given id owned by this owner.
   - **Parameters:**
     - `id`: The id of the pet to search for.
   - **Return Value:** Pet - The `Pet` object with the matching id, or null if not found.
   - **Logic:** Iterates through the `pets` list and compares the pet's id to the given id. Returns the matching `Pet` object.

11. **`getPet(String name, boolean ignoreNew)`:**
   - **Purpose:** Returns the `Pet` with the given name owned by this owner, considering whether to ignore new pets.
   - **Parameters:**
     - `name`: The name of the pet to search for.
     - `ignoreNew`: A boolean indicating whether to ignore new pets.
   - **Return Value:** Pet - The `Pet` object with the matching name, or null if not found.
   - **Logic:** Similar to `getPet(String name)`, but includes a parameter to control whether new pets should be ignored.

12. **`toString()`:**
   - **Purpose:** Returns a string representation of the `Owner` object.
   - **Parameters:** None.
   - **Return Value:** String - A string representation of the `Owner` object, including its id, name, address, city, and telephone number.

13. **`addVisit(Integer petId, Visit visit)`:**
   - **Purpose:** Adds a visit to the `Pet` with the given identifier.
   - **Parameters:**
     - `petId`: The id of the `Pet` to add the visit to.
     - `visit`: The `Visit` object to be added.
   - **Return Value:** None.
   - **Logic:** Retrieves the `Pet` object with the given `petId` and calls the `addVisit` method on that `Pet` object to add the given `visit`.



**Assumptions:**

* The `Person` class is defined elsewhere and provides basic attributes and methods for a person.
* The `Pet` class is defined elsewhere and represents a pet owned by an owner.
* The `Visit` class is defined elsewhere and represents a visit to a veterinarian.
* The `BaseEntity` class is defined elsewhere and provides common functionality for entities in the system.



**Dependencies:**

* `jakarta.persistence` for JPA annotations.
* `org.springframework.boot` for Spring Boot framework.

**Usage:**

The `Owner` class can be used to represent owners in a pet clinic application. It can be instantiated and populated with data, and its methods can be used to access and modify the owner's information.



