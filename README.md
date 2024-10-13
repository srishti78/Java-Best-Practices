# **Controllers**

## **Steps to Follow When Creating the Controller Layer**

### 1. **Define the Controller**

* Annotate the class with `@RestController`.
* Set the base URL using `@RequestMapping` (e.g., `/api/v1/products`).

    ```java
    @RestController
    @RequestMapping("/api/v1/products")
    public class ProductController { }
    ```

---

### 2. **Use Correct HTTP Method Annotations**

* Use the appropriate HTTP method for each operation:
  * `@GetMapping` for retrieval.
  * `@PostMapping` for creation.
  * `@PutMapping` for updates.
  * `@DeleteMapping` for deletions.

    ```java
    @GetMapping("/{id}")
    public ResponseEntity<Product> getProduct(@PathVariable Long id) { }
    ```

---

### 3. **Handle Parameters**

* Use `@PathVariable` for dynamic values in the URL.
* Use `@RequestParam` for query parameters.

    ```java
    @GetMapping("/search")
    public ResponseEntity<List<Product>> search(@RequestParam String name) { }
    ```

---

### 4. **Input Validation**

* Use `@Valid` to validate the request body.
* Implement Java Bean Validation for request objects.

    ```java
    @PostMapping
    public ResponseEntity<Product> createProduct(@Valid @RequestBody ProductRequest request) { }
    ```

---

### 5. **Return Appropriate HTTP Status**

* Use `ResponseEntity` to return the correct HTTP status and response body.

    ```java
    return ResponseEntity.ok(product);
    return ResponseEntity.status(HttpStatus.CREATED).body(newProduct);
    ```

---

### 6. **Exception Handling**

* Centralize exception handling using `@ControllerAdvice`.

    ```java
    @ControllerAdvice
    public class GlobalExceptionHandler { }
    ```

---

### 7. **Follow REST Naming Conventions**

* Use **plural nouns** for resource names (e.g., `/products`).
* Avoid using verbs in URLs (e.g., use `/products/{id}` instead of `/getProduct`).

---

### 8. **Logging**

* Log important actions using `log.info()` and `log.error()`.
* Avoid logging sensitive data.

    ```java
    log.info("Fetching product with id {}", id);
    ```

---

### 9. **Secure Endpoints**

* Use `@PreAuthorize` or `@Secured` to secure endpoints.

    ```java
    @PreAuthorize("hasRole('ADMIN')")
    @DeleteMapping("/{id}")
    public ResponseEntity<Void> deleteProduct(@PathVariable Long id) { }
    ```

---

### 10. **Use DTOs (Data Transfer Objects)**

* Use DTOs for input/output to avoid exposing internal entity models directly.

    ```java
    public class ProductRequest { }
    ```

---

## **Summary**

This guide provides structured steps and best practices for creating the controller layer in a Spring Boot project. It emphasizes the importance of validation, logging, security, and REST conventions to build scalable, maintainable APIs.
