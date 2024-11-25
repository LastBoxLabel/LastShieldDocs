# SecurityUtil


`SecurityUtil` is a utility class designed to assist with various security-related tasks in the application. It provides methods for interacting with user roles, authorities, and repositories using reflection. The class handles the retrieval of user repositories, conversion of user roles to `GrantedAuthority` objects, and more, enabling efficient user management and security configuration.

### 1. Attributes

<table>
    <thead>
        <th scope="col">Type</th>
        <th scope="col">Name</th>
        <th scope="col">Description</th>
    </thead>
    <tbody>
        <tr>
            <td>Logger</td>
            <td>logger</td>
            <td>A logger instance for logging relevant information and errors during execution. </td>
        </tr>
    </tbody>
</table>
<br></br>

### 2. Methods

#### 2.1 `getUserRepositoryClass()`

Retrieves the user repository class annotated with `@UserHandler`. The method use reflections to scan the classpath for classes annotated with `@UserHandler` and returns the corresponding user repository class.

- **Returns**: `Class<?>` — The user repository class annotated with `@UserHandler`.
- **Throws**: `RuntimeException` if no user handler class is found or an error occurs during class loading.
---
#### 2.2 `getUserAuthorities(Object user)`

Converts the roles of a user into a list of `GrantedAuthority` objects. This is used to manage access control in Spring Security.

The user entity must have an attribute named 'role' (for a single role) or 'roles' (for multiple roles) to define the user's roles.

- **Parameters**:
  `user` (`Object`) — The user object from which roles will be extracted.

- **Returns**:
  `List<GrantedAuthority>` — A list of `GrantedAuthority` objects representing the user's roles.
---
#### 2.3 `findUserByUsername(Object userService, String username)`

Finds a user by their username by invoking the `findUserByUsername` method on the provided user repository.

- **Parameters**:
  `userService` (`Object`) — The user repository to search for the user.
  `username` (`String`) — The username of the user to find.

- **Returns**:
  `Object` — The user entity associated with the given username.

- **Throws**:
  `RuntimeException` if the `findUserByUsername` method is not found in the user repository or if an error occurs during method invocation.
