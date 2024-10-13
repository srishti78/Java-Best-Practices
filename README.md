# Controllers

## Steps to follow when creating the controller layer

1. Define the Controller:
Annotate the class with @RestController.
Set the base URL using @RequestMapping (e.g., /api/v1/products).

@RestController
@RequestMapping("/api/v1/products")
public class ProductController { }


2. Use Correct HTTP Method Annotations:
@GetMapping for retrieval.
@PostMapping for creation.
@PutMapping for updates.
@DeleteMapping for deletions.

@GetMapping("/{id}")
public ResponseEntity<Product> getProduct(@PathVariable Long id) { }


3. Handle Parameters:
Use @PathVariable for URL parameters.
Use @RequestParam for query parameters.

@GetMapping("/search")
public ResponseEntity<List<Product>> search(@RequestParam String name) { }


4. Input Validation:
Use @Valid for request body validation.
Validate inputs with Java Bean Validation.

@PostMapping
public ResponseEntity<Product> createProduct(@Valid @RequestBody ProductRequest request) { }


5. Return Appropriate HTTP Status:
Use ResponseEntity to return the correct status and response.

return ResponseEntity.ok(product);
return ResponseEntity.status(HttpStatus.CREATED).body(newProduct);


6. Exception Handling:
Handle exceptions using @ControllerAdvice for centralized error handling.

@ControllerAdvice
public class GlobalExceptionHandler { }


7. Use REST Naming Conventions:
Use plural nouns for resource names (e.g., /products).
Avoid verbs in URLs (e.g., use /products/{id} instead of /getProduct).


8. Logging:
Log important actions using log.info() and log.error().
Avoid logging sensitive data.

log.info("Fetching product with id {}", id);


9. Secure Endpoints:
Use @PreAuthorize or @Secured to secure endpoints.

@PreAuthorize("hasRole('ADMIN')")
@DeleteMapping("/{id}")
public ResponseEntity<Void> deleteProduct(@PathVariable Long id) { }


10. Use DTOs:
Use DTOs (Data Transfer Objects) for input/output instead of entities to avoid exposing internal data models.

public class ProductRequest { }

