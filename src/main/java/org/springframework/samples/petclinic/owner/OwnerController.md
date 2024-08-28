## Documentation of OwnerController.java

**Overview:**

The `OwnerController` class handles web requests related to managing `Owner` objects within a Spring MVC application. It provides functionality for creating, updating, deleting, and displaying owners. The controller leverages the `OwnerRepository` interface to interact with the database and Spring Data JPA to simplify data access operations.

**Dependencies:**

* **Spring Data JPA:** Provides the foundation for interacting with the database using JPA.
* **OwnerRepository:** An interface defining the data access methods for managing `Owner` objects.
* **Spring MVC:** Enables the creation of web controllers and handling of HTTP requests.

**Methods:**

1. **`initCreationForm(Map<String, Object> model)`:**
   * **Description:** Initializes the form for creating a new owner.
   * **Parameters:**
      * `model`: A `Map` used to store model attributes for the view.
   * **Return Value:** The view name (`VIEWS_OWNER_CREATE_OR_UPDATE_FORM`).
   * **Functionality:** Creates a new `Owner` object and sets it as a model attribute named "owner". This object will be used to populate the form.

2. **`processCreationForm(@Valid Owner owner, BindingResult result, RedirectAttributes redirectAttributes)`:**
   * **Description:** Processes the form submission for creating a new owner.
   * **Parameters:**
      * `owner`: The `Owner` object containing the submitted data.
      * `result`: A `BindingResult` object holding validation errors.
      * `redirectAttributes`: A `RedirectAttributes` object used to store flash attributes for redirecting the user.
   * **Return Value:** The view name (`"redirect:/owners/" + owner.getId()`).
   * **Functionality:** Validates the `Owner` object using `@Valid` annotation and `BindingResult`. If validation fails, it sets an error message in `redirectAttributes` and redirects back to the creation form. If successful, it saves the `Owner` object using `owners.save(owner)` and redirects to the owner's details page with a success message.

3. **`initFindForm()`:**
   * **Description:** Initializes the form for finding owners by last name.
   * **Return Value:** The view name (`"owners/findOwners"`).

4. **`processFindForm(@RequestParam(defaultValue = "1") int page, Owner owner, BindingResult result, Model model)`:**
   * **Description:** Processes the form submission for finding owners by last name.
   * **Parameters:**
      * `page`: The current page number.
      * `owner`: The `Owner` object containing the search criteria.
      * `result`: A `BindingResult` object holding validation errors.
      * `model`: A `Model` object used to store model attributes for the view.
   * **Return Value:** The view name (`"owners/ownersList"`).
   * **Functionality:** Performs a search for owners based on the provided last name using `owners.findByLastName(lastname, pageable)`. It handles different scenarios based on the number of results found: no results, one result, or multiple results.

5. **`addPaginationModel(int page, Model model, Page<Owner> paginated)`:**
   * **Description:** Adds pagination information to the model for displaying the owner list.
   * **Parameters:**
      * `page`: The current page number.
      * `model`: A `Model` object used to store model attributes for the view.
      * `paginated`: The `Page<Owner>` object containing the paginated results.
   * **Functionality:** Sets the current page, total pages, total items, and list of owners in the model.

6. **`findPaginatedForOwnersLastName(int page, String lastname)`:**
   * **Description:** Performs a paginated search for owners based on the last name.
   * **Parameters:**
      * `page`: The current page number.
      * `lastname`: The last name to search for.
   * **Return Value:** A `Page<Owner>` object containing the paginated results.
   * **Functionality:** Uses `owners.findByLastName(lastname, pageable)` to retrieve the paginated results.

7. **`initUpdateOwnerForm(@PathVariable("ownerId") int ownerId, Model model)`:**
   * **Description:** Initializes the form for updating an existing owner.
   * **Parameters:**
      * `ownerId`: The ID of the owner to update.
      * `model`: A `Model` object used to store model attributes for the view.
   * **Return Value:** The view name (`VIEWS_OWNER_CREATE_OR_UPDATE_FORM`).
   * **Functionality:** Retrieves the `Owner` object with the given ID using `owners.findById(ownerId)` and sets it as a model attribute named "owner".

8. **`processUpdateOwnerForm(@Valid Owner owner, BindingResult result, @PathVariable("ownerId") int ownerId, RedirectAttributes redirectAttributes)`:**
   * **Description:** Processes the form submission for updating an existing owner.
   * **Parameters:**
      * `owner`: The `Owner` object containing the updated data.
      * `result`: A `BindingResult` object holding validation errors.
      * `ownerId`: The ID of the owner to update.
      * `redirectAttributes`: A `RedirectAttributes` object used to store flash attributes for redirecting the user.
   * **Return Value:** The view name (`"redirect:/owners/{ownerId}"`).
   * **Functionality:** Validates the `Owner` object and updates the existing owner in the database using `owners.save(owner)`. It redirects to the owner's details page with a success message.

9. **`showOwner(@PathVariable("ownerId") int ownerId)`:**
   * **Description:** Displays the details of a specific owner.
   * **Parameters:**
      * `ownerId`: The ID of the owner to display.
   * **Return Value:** A `ModelAndView` object containing the view name (`"owners/ownerDetails"`) and the `Owner` object.
   * **Functionality:** Retrieves the `Owner` object with the given ID and sets it as a model attribute in the `ModelAndView` object.



**Note:** This documentation assumes familiarity with Spring MVC concepts such as controllers, models, views, and request handling.

