## Documentation of `VetController.java`

This Java class serves as a controller for handling requests related to veterinarians in the Spring PetClinic application. It utilizes Spring's annotation-based MVC framework to map HTTP requests to specific handler methods.

**Overview:**

The `VetController` class provides two main functionalities:

1. **Displaying a list of veterinarians:** It handles requests to `/vets.html`, retrieving a paginated list of veterinarians from the `VetRepository` and rendering the list in the `vets/vetList` template.
2. **Returning a list of veterinarians as JSON:** It handles requests to `/vets`, retrieving all veterinarians from the `VetRepository` and returning them as a JSON object.

**Methods:**

* **`showVetList(int page, Model model)`:**
    * **Description:** Handles GET requests to `/vets.html`.
    * **Parameters:**
        * `page`: The current page number (default: 1).
        * `model`: A `Model` object used to pass data to the view.
    * **Logic:**
        1. Retrieves a paginated list of veterinarians from the `VetRepository` using `findPaginated(page)`.
        2. Creates a `Vets` object and adds the retrieved veterinarians to its list.
        3. Calls `addPaginationModel` to populate the `model` with pagination information (current page, total pages, total items).
        4. Returns the `vets/vetList` view name.
* **`addPaginationModel(int page, Page<Vet> paginated, Model model)`:**
    * **Description:** Populates the `model` with pagination information.
    * **Parameters:**
        * `page`: The current page number.
        * `paginated`: The paginated list of veterinarians.
        * `model`: A `Model` object used to pass data to the view.
    * **Logic:**
        1. Sets the `currentPage`, `totalPages`, `totalItems`, and `listVets` attributes in the `model`.
* **`findPaginated(int page)`:**
    * **Description:** Retrieves a paginated list of veterinarians from the `VetRepository`.
    * **Parameters:**
        * `page`: The current page number.
    * **Logic:**
        1. Creates a `Pageable` object with the specified page and a page size of 5.
        2. Calls `findAll` on the `VetRepository` with the `Pageable` object to retrieve a paginated list of veterinarians.
* **`showResourcesVetList()`:**
    * **Description:** Handles GET requests to `/vets`.
    * **Logic:**
        1. Retrieves all veterinarians from the `VetRepository`.
        2. Creates a `Vets` object and adds the retrieved veterinarians to its list.
        3. Returns the `Vets` object as a JSON response.



**Data Structures:**

* **`Vets`:** A custom object that holds a list of `Vet` objects.

**Dependencies:**

* **`VetRepository`:** An interface extending `Repository` for interacting with the `Vet` entity in the database.



**Edge Cases and Error Handling:**

* The code assumes that the `VetRepository` will handle any database-related errors.
* No specific error handling is implemented within the controller.



**Pseudo Code:**

```
1. Handle GET request to "/vets.html":
    - Get page number from request parameter.
    - Retrieve paginated list of veterinarians from repository.
    - Create Vets object and populate with veterinarians.
    - Set model attributes for pagination information.
    - Render "vets/vetList" view.

2. Handle GET request to "/vets":
    - Retrieve all veterinarians from repository.
    - Create Vets object and populate with veterinarians.
    - Return Vets object as JSON response.
```