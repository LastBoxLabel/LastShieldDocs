# SecurityConfig

The `SecurityConfig` class is responsible for dynamically configuring the security rules of the application. It allows defining CORS policies, CSRF protection, and route permissions by delegating the configuration to the [CorsConfig](../security-core/Main%20classes/CorsConfig.md) and [CoreSecurityConfig](../security-core/Main%20classes/CoreSecurityConfig.md) classes. This class utilizes method chaining to provide a fluent interface for security configuration.

This class is used to set up security policies for the application, including cross-origin resource sharing (CORS) settings, protection against cross-site request forgery (CSRF), and defining role-based access control (RBAC) for various routes.

The main idea is to completely simplify the Spring Security configuration, allowing the user to spend less time on setup while providing a clear and quick overview of the processes taking place

### 1. Attributes

<table>
    <thead>
        <th scope="col">Type</th>
        <th scope="col">Name</th>
        <th scope="col">Description</th>
    </thead>
    <tbody>
        <tr>
            <td><strong>CorsConfig</strong></td>
            <td>corsConfig</td>
            <td>The configuration object that manages CORS policies.</td>
        </tr>
        <tr>
            <td><strong>CoreSecurityConfig</strong></td>
            <td>coreSecurityConfig</td>
            <td>The core configuration object that handles general security policies, including CSRF protection and route authorities.</td>
        </tr>
    </tbody>
</table>

<br></br>

### 2. Methods

#### 2.1 `corsAllowedOrigins(String allowedOrigin)`

Sets a single allowed origin for CORS.

- **Parameters**:
  `allowedOrigin` (`String`) — The allowed origin.

- **Returns**:
  `SecurityConfig` — The current instance of `SecurityConfig` for method chaining.

---

#### 2.2 `corsAllowedOrigins(List<String> allowedOrigins)`

Sets multiple allowed origins for CORS.

- **Parameters**:
  `allowedOrigins` (`List<String>`) — A list of allowed origins.

- **Returns**:
  `SecurityConfig` — The current instance of `SecurityConfig` for method chaining.

---

#### 2.3 `corsAllowMethods(String allowedMethod)`

Sets a single allowed HTTP method for CORS.

- **Parameters**:
  `allowedMethod` (`String`) — The allowed HTTP method.

- **Returns**:
  `SecurityConfig` — The current instance of `SecurityConfig` for method chaining.

---

#### 2.4 `corsAllowedMethods(List<String> allowedMethods)`

Sets multiple allowed HTTP methods for CORS.

- **Parameters**:
  `allowedMethods` (`List<String>`) — A list of allowed HTTP methods.

- **Returns**:
  `SecurityConfig` — The current instance of `SecurityConfig` for method chaining.

---

#### 2.5 `corsAllowedHeaders(String allowedHeader)`

Sets a single allowed header for CORS.

- **Parameters**:
  `allowedHeader` (`String`) — The allowed header.

- **Returns**:
  `SecurityConfig` — The current instance of `SecurityConfig` for method chaining.

---

#### 2.6 `corsAllowedHeaders(List<String> allowedHeaders)`

Sets multiple allowed headers for CORS.

- **Parameters**:
  `allowedHeaders` (`List<String>`) — A list of allowed headers.

- **Returns**:
  `SecurityConfig` — The current instance of `SecurityConfig` for method chaining.

---

#### 2.7 `corsAllowCredentials(boolean allowCredentials)`

Enables or disables credentials support for CORS.

- **Parameters**:
  `allowCredentials` (`boolean`) — `true` to allow credentials, `false` otherwise.

- **Returns**:
  `SecurityConfig` — The current instance of `SecurityConfig` for method chaining.

---

#### 2.8 `setCsrfProtection(boolean csrfProtection)`

Enables or disables CSRF protection.

- **Parameters**:
  `csrfProtection` (`boolean`) — `true` to enable CSRF protection, `false` to disable it.

- **Returns**:
  `SecurityConfig` — The current instance of `SecurityConfig` for method chaining.

---

#### 2.9 `addRouteAuthority(String path)`

Adds a public route without restrictions on HTTP methods.

- **Parameters**:
  `path` (`String`) — The route path.

- **Returns**:
  `SecurityConfig` — The current instance of `SecurityConfig` for method chaining.

---

#### 2.10 `addRouteAuthority(String path, HttpMethod httpMethod)`

Adds a public route restricted to a specific HTTP method.

- **Parameters**:
  `path` (`String`) — The route path.
  `httpMethod` (`HttpMethod`) — The allowed HTTP method.

- **Returns**:
  `SecurityConfig` — The current instance of `SecurityConfig` for method chaining.

---

#### 2.11 `addRouteAuthority(String path, HashSet<HttpMethod> httpMethods)`

Adds a public route restricted to multiple HTTP methods.

- **Parameters**:
  `path` (`String`) — The route path.
  `httpMethods` (`HashSet<HttpMethod>`) — A set of allowed HTTP methods.

- **Returns**:
  `SecurityConfig` — The current instance of `SecurityConfig` for method chaining.

---

#### 2.12 `addRouteAuthority(String path, String role)`

Adds a route restricted to a specific user role.

- **Parameters**:
  `path` (`String`) — The route path.
  `role` (`String`) — The required user role.

- **Returns**:
  `SecurityConfig` — The current instance of `SecurityConfig` for method chaining.

---

#### 2.13 `addRouteAuthority(String path, List<String> roles)`

Adds a route restricted to multiple user roles.

- **Parameters**:
  `path` (`String`) — The route path.
  `roles` (`List<String>`) — A list of required user roles.

- **Returns**:
  `SecurityConfig` — The current instance of `SecurityConfig` for method chaining.

---

#### 2.14 `addRouteAuthority(String path, String role, HttpMethod httpMethod)`

Adds a route restricted to a specific user role and HTTP method.

- **Parameters**:
  `path` (`String`) — The route path.
  `role` (`String`) — The required user role.
  `httpMethod` (`HttpMethod`) — The allowed HTTP method.

- **Returns**:
  `SecurityConfig` — The current instance of `SecurityConfig` for method chaining.

---

#### 2.15 `addRouteAuthority(String path, String role, List<HttpMethod> httpMethods)`

Adds a route restricted to a specific user role and multiple HTTP methods.

- **Parameters**:
  `path` (`String`) — The route path.
  `role` (`String`) — The required user role.
  `httpMethods` (`List<HttpMethod>`) — A list of allowed HTTP methods.

- **Returns**:
  `SecurityConfig` — The current instance of `SecurityConfig` for method chaining.

---

#### 2.16 `build()`

Finalizes and validates the security configuration. This method is used to apply all the configured security rules.

- **Returns**:
  `void` — No return value.

---

### 3. Usage

```java
securityConfig.corsAllowCredentials(true)
              .corsAllowedOrigins(List.of("*"))
              .corsAllowedMethods(List.of("*"))
              .addRouteAuthority("/login")
              .addRouteAuthority("/register")
              .addRouteAuthority("/admin", "ADMIN")
              .addRouteAuthority("/**", List.of("USER", "ADMIN"))
              .setCsrfProtection(false)
              .build();
```
