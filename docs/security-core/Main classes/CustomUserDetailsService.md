# CustomUserDetailsService Documentation

The `CustomUserDetailsService` class is a custom implementation of Spring's `UserDetailsService` interface. It is responsible for loading user-specific data during the authentication process by retrieving user details from a dynamically determined user repository.

---

### 1. Attributes

<table>
  <thead>
    <tr>
      <th>Attribute</th>
      <th>Type</th>
      <th>Description</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>SecurityUtil</td>
      <td>securityUtil</td>
      <td>Utility class for security-related operations, such as finding users by username and determining the user repository.</td>
    </tr>
    <tr>
      <td>ApplicationContext</td>
      <td>applicationContext</td>
      <td>The Spring application context, used to dynamically retrieve the appropriate user repository bean.</td>
    </tr>
    <tr>
      <td>Object</td>
      <td>userRepository</td>
      <td>The user repository used for fetching user entities. It is determined dynamically based on the configuration provided by <code>SecurityUtil</code>.</td>
    </tr>
  </tbody>
</table>
<br></br>

### 2. Methods

#### 2.1 `CustomUserDetailsService(SecurityUtil securityUtil, ApplicationContext applicationContext)`
Constructs an instance of `CustomUserDetailsService` with the necessary dependencies for security operations and the Spring application context.

- **Parameters:**
  - `securityUtil`: Utility class for security-related operations.
  - `applicationContext`: The Spring `ApplicationContext` used to retrieve beans dynamically.

---

#### 2.2 `UserDetails loadUserByUsername(String username)`
Loads user details by username. Fetches the user entity from the user repository and retrieves the password field annotated with `@Password`.

- **Parameters:**
  - `username`: The username of the user whose details are to be loaded.

- **Returns:**
  A `UserDetails` object containing the user's username and password.

- **Throws:**
  - `UsernameNotFoundException` if the user with the given username is not found.
  - `IllegalStateException` if no field with the `@Password` annotation exists in the user entity.
  - `RuntimeException` for other unexpected errors during the operation.




