# GlobalExceptionHandler

This class handles `RuntimeException` exceptions globally in the application. It intercepts exceptions, constructs a standardized error response containing the error message, HTTP status code, and timestamp, and returns it as part of a `ResponseEntity` to the client.

The `@ControllerAdvice` annotation is a Spring Framework annotation that allows the creation of classes in Java that centralize exception handling throughout the application.

### 1. Methods

#### 1.1 `handleResourceNotFoundException(RuntimeException e)`
Handles `RuntimeException` by creating an `ErrorResponse` with the exception message and a `BAD_REQUEST` status code. It then returns the error response wrapped in a `ResponseEntity` with a `NOT_FOUND` status. Uses the `@ExceptionHandler(RuntimeException.class)` annotation to catch all RuntimeException instances throughout the application context.

- **Parameters**:
  `ex` (`RuntimeException`) — The exception that was thrown.

- **Returns**:
  `ResponseEntity<?>` — A response containing the error details with a `NOT_FOUND` status.