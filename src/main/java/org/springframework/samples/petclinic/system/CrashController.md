## Documentation for CrashController.java

**Overview:**

The `CrashController` class demonstrates how exceptions are handled in a Spring application. It features a single controller method, `triggerException()`, which intentionally throws a `RuntimeException`. This showcases how Spring Boot handles exceptions and displays the appropriate error page.

**Methods:**

1. **`triggerException()`:**
   - **Purpose:**  Intentionally throws a `RuntimeException` to demonstrate exception handling in Spring.
   - **Parameters:** None.
   - **Return Value:**  N/A (The method throws an exception and doesn't return a value).
   - **Logic:**
     - Calls `throw new RuntimeException(...)` with a message describing the purpose of the exception. This triggers an exception that Spring will catch and handle.


**Dependencies:**

* **Spring Framework:**  Provides the foundation for dependency injection, web handling, and exception handling.

**Pseudo Code:**

```
// CrashController Class

// Method triggerException
  - Throw a RuntimeException with the message "Expected: controller used to showcase what happens when an exception is thrown"



```

**Edge Cases and Error Handling:**

- The code explicitly throws a `RuntimeException`, which is a general exception type. Spring Boot has built-in mechanisms to handle exceptions and map them to appropriate error views.
- The error view "error.html" (not shown in the provided code) is likely configured in the application to display the error message and provide a user-friendly experience.



