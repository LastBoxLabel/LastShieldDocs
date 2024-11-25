# RouteAuthority Documentation

The `RouteAuthority` class represents the access control configuration for a specific route within an application. It defines the security rules for a path, including allowed roles and HTTP methods (GET, POST, etc.).

This class is used to specify the security constraints for each route in the application's security configuration.

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
      <td>String</td>
      <td>path</td>
      <td>The path of the route to which this authority applies.</td>
    </tr>
    <tr>
      <td>String[]</td>
      <td>roles</td>
      <td>An array of roles that are allowed to access this route.</td>
    </tr>
    <tr>
      <td>List&lt;HttpMethod&gt;</td>
      <td>httpMethods</td>
      <td>A list of HTTP methods (e.g., GET, POST) allowed on this route.</td>
    </tr>
  </tbody>
</table>

---

### 1. Constructors

### 1.1 `RouteAuthority(String path)`
Constructs a `RouteAuthority` with the specified path and no roles.

- **Parameters:**
  - `path`: The path of the route.

---

#### 1.2 `RouteAuthority(String path, String role)`
Constructs a `RouteAuthority` with the specified path and a single role.

- **Parameters:**
  - `path`: The path of the route.
  - `role`: The role required to access the route.

---

#### 1.3 `RouteAuthority(String path, String role, HttpMethod... httpMethods)`
Constructs a `RouteAuthority` with the specified path, role, and HTTP methods.

- **Parameters:**
  - `path`: The path of the route.
  - `role`: The role required to access the route.
  - `httpMethods`: The HTTP methods allowed on the route.

---

#### 1.4 `RouteAuthority(String path, List<String> roles)`
Constructs a `RouteAuthority` with the specified path and list of roles.

- **Parameters:**
  - `path`: The path of the route.
  - `roles`: A list of roles allowed to access the route.

---

### 1.5 `RouteAuthority(String path, HttpMethod... httpMethods)`
Constructs a `RouteAuthority` with the specified path and HTTP methods.

- **Parameters:**
  - `path`: The path of the route.
  - `httpMethods`: The HTTP methods allowed on the route.

---

### 2. Methods

#### 2.1 `getPath()`
Gets the path associated with this `RouteAuthority`.

- **Returns:** `String path` -  The path for this route.

---

#### 2.2 `getRoles()`
Gets the roles associated with this `RouteAuthority`.

- **Returns:** `String[] roles` - An array of roles allowed to access this route.

---

#### 2.3 ` getHttpMethods()`
Gets the HTTP methods allowed on this route.

- **Returns:** `List<HttpMethod> httpMethods` -  A list of allowed HTTP methods (e.g., GET, POST).

---

#### 2.4 `toString()`
Returns a string representation of the `RouteAuthority`.

- **Returns:** `String routeAuthority` -  A string containing the path, roles, and HTTP methods associated with this route.


