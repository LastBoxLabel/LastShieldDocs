---
sidebar_position: 2
---

# Security core

<p>The Security Core module is designed to provide essential functionalities for secured application development. It handles key aspects like request filtering, exception management, role-based access control, and token validation, offering a robust framework to implement authentication and authorization workflows.</p>

<p>This module is structured around several core components, each with a dedicated purpose to ensure clean separation of concerns and maintainability. Here's an overview of the classes:</p>


### Main classes

<table>
<thead>
<th scope="col">Class</th>
<th scope="col">Description</th>
</thead>
<tbody>
    <tr>
        <td>CoreSecurityConfig</td>
        <td>Sets up and manages the application's security configurations.</td>
    </tr>
    <tr>
        <td>CorsConfig</td>
        <td>Configures the application's Cross-Origin Resource Sharing (CORS)</td>
    </tr>
    <tr>
        <td>CustomUserDetailService</td>
        <td>Handles the loading of user-specific data during authentication by fetching user details from a dynamically determined repository.</td>
    </tr>
    <tr>
        <td>RouteAuthority</td>
        <td>Defines the authorization configuration for a specific route, including roles and allowed HTTP methods.</td>
    </tr>
    <tr>
        <td>SecurityFilter</td>
        <td>Implements a custom security filter that intercepts HTTP requests to validate JWT tokens, authenticate users, and populate the security context when advanced filtering is enabled.</td>
    </tr>

</tbody>
</table>

### Utility classes

<table>
<thead>
    <th scope="col"> Class </th>
    <th scope="col"> Description </th>
</thead>
<tbody>
    <tr>
        <td>AdvancedFilterChecker</td>
        <td>Offers utility methods to manage when advanced filtering is required.</td>
    </tr>
    <tr>
        <td>ErrorResponse</td>
        <td>Represents a utility class responsible for defining a standardized format for API error responses.</td>
</tr>
<tr>
        <td>GlobalExceptionHandler</td>
        <td>Handles RuntimeException occurrences across the application, delivering a consistent and standardized error response format.</td>
    </tr>
    <tr>
        <td>SecurityUtil</td>
        <td>Provides utility methods for security operations, including user role retrieval, authority conversion, user repository discovery, and reflective interaction with user entities.</td>
    </tr>
</tbody>
</table>

### Annotations
<table>
    <thead>
        <th scope="col">Annotation</th>
        <th scope="col">Description</th>
    </thead>
    <tbody>
        <tr>
            <td>Password</td>
            <td>Used to mark a field in a user entity class
 as containing the user's password.</td>
        </tr>
        <tr>
            <td>UserHandler</td>
            <td>Used to mark a class
as a handler for user-related operations within the security context.</td>
        </tr>
        <tr>
            <td>Username</td>
            <td>Used to mark a field in a user entity class as containing the user's username.</td>
        </tr>
    </tbody>
</table>

### Custom exceptions
<table>
    <thead>
        <th scope="col">Exception</th>
        <th scope="col">Description</th>
    </thead>
    <tbody>
        <tr>
            <td>EmptyTokenException</td>
            <td>This exception is thrown when an expected token is empty or missing.</td>
        </tr>
    </tbody>
</table>


<p>Now that we have completed the overview, let’s dive deeper into each class. In the following sections, we will explore the purpose, structure, and functionality of each component, understanding how they contribute to the overall security architecture of the application.</p>




