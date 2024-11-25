# SecurityFilter

The `SecurityFilter` class extends `OncePerRequestFilter` and is designed to handle authentication for HTTP requests using JWT (JSON Web Tokens). This filter intercepts requests, validates the token provided in the `Authorization` header, and sets the authenticated user in the security context if the token is valid.

Responsible for:
- Validates JWT tokens in incoming requests.
- Authenticates users based on the decoded token.
- Sets the security context with the authenticated user and their roles.
- Responds with appropriate HTTP status codes for authentication failures.

---

### 1. Attributes

<table>
  <thead>
    <tr>
      <th>Type</th>
      <th>Attribute</th>
      <th>Description</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>JwtService</td>
      <td>jwtService</td>
      <td>The service used to validate and decode JWT tokens.</td>
    </tr>
    <tr>
      <td>Object</td>
      <td>userRepository</td>
      <td>The user repository bean used for fetching user details.</td>
    </tr>
    <tr>
      <td>ApplicationContext</td>
      <td>applicationContext</td>
      <td>The Spring application context for accessing beans.</td>
    </tr>
    <tr>
      <td>Logger</td>
      <td>logger</td>
      <td>Logger instance for logging errors and important events.</td>
    </tr>
    <tr>
      <td>SecurityUtil</td>
      <td>securityUtil</td>
      <td>Utility class for performing security-related operations.</td>
    </tr>
  </tbody>
</table>

---

### 2. Methods

#### 2.1 `SecurityFilter(JwtService jwtService, ApplicationContext applicationContext, SecurityUtil securityUtil)`

The constructor initializes the `SecurityFilter` with the required dependencies.

- **Parameters:**
  - `jwtService`: Service for validating JWT tokens.
  - `applicationContext`: Spring application context for accessing beans.
  - `securityUtil`: Utility for user and role-related operations.


#### 2.2 `setUserRepository(Class<?> userRepositoryClass)`

Sets the user repository used for user lookups.

- **Parameters:**
  - `userRepositoryClass`: The class type of the user repository bean.

---

#### 2.3 `doFilterInternal(HttpServletRequest request, HttpServletResponse response, FilterChain filterChain)`

Intercepts and processes HTTP requests. Validates JWT tokens and sets the authentication context.

- **Parameters:**
  - `request`: The HTTP request.
  - `response`: The HTTP response.
  - `filterChain`: The filter chain to pass the request to the next filter.

- **Behavior:**
  - Validates the JWT token in the `Authorization` header.
  - If the token is valid, retrieves the user and sets the authentication context.
  - Sends appropriate HTTP error responses for invalid tokens or missing users.

---

#### 2.4 `shouldNotFilter(HttpServletRequest request)`

Determines if this filter should skip processing for the given request.

- **Parameters:**
  - `request`: The HTTP request.

- **Returns:**
  `boolean` - `true` if the request should not be filtered, `false` otherwise.
