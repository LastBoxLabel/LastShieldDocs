# CoreSecurityConfig

The `CoreSecurityConfig` class is responsible for configuring the security settings for a web application, including authorization, authentication, and Cross-Site Request Forgery (CSRF) protection. It leverages Spring Security to manage route-based access control and integrates with a custom security filter.

This core is configured using the SecurityConfig fluent API, which allows for streamlined and intuitive setup of core attributes through its methods.

### 1. Attributes

<table>
  <thead>
    <tr>
      <th><strong>Type</strong></th>
      <th><strong>Name</strong></th>
      <th><strong>Description</strong></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td><code>boolean</code></td>
      <td><code>isCalled</code></td>
      <td>A flag to check whether the <code>build()</code> method has been called to finalize the configuration.</td>
    </tr>
    <tr>
<td><code>boolean</code></td>
      <td><code>csrfProtection</code></td>
      <td>Flag indicating whether CSRF protection is enabled. Default is <code>true</code>.</td>
    </tr>
    <tr>
      <td><code>CorsConfig</code></td>
      <td><code>corsConfig</code></td>
      <td>The CORS configuration bean, used to configure Cross-Origin Resource Sharing (CORS) settings.</td>
    </tr>
    <tr>
      <td><code>SecurityUtil</code></td>
      <td><code>securityUtil</code></td>
      <td>The utility bean that provides security-related operations such as user repository handling.</td>
    </tr>
    <tr>
      <td><code>SecurityFilter</code></td>
      <td><code>securityFilter</code></td>
      <td>A custom security filter that processes authentication and authorization before the main filter.</td>
    </tr>
    <tr>
      <td><code>List&lt;RouteAuthority&gt;</code></td>
      <td><code>authorities</code></td>
      <td>A list of route authorities representing the routes and their required roles for access control.</td>
    </tr>
    <tr>
      <td><code>Logger</code></td>
      <td><code>logger</code></td>
      <td>Logger instance for logging various actions and events related to security configuration.</td>
    </tr>
  </tbody>
</table>
<br></br>

### 2. Methods

#### 2.1 `CoreSecurityConfig(CorsConfig corsConfig, SecurityUtil securityUtil, SecurityFilter securityFilter)`
The constructor for `CoreSecurityConfig` class. This constructor is used for dependency injection in Spring. It initializes the configuration with the necessary beans for CORS, security utilities, and a custom security filter.
---

#### 2.2 `defaultSecurityFilterChain(HttpSecurity http) throws Exception`
Configures the default `SecurityFilterChain` with CORS, CSRF protection, and authority-based access control. This method sets up the security filter chain by adding the `SecurityFilter` and configuring paths and roles.

The CORS configuration is handled by the CorsConfig class implementation, which allows setting various CORS policies such as allowed origins, methods, headers, and credentials.


- **Parameters**:
  - `http` - The `HttpSecurity` object used to configure security settings.
- **Returns**: A configured `SecurityFilterChain`.
- **Throws**: `Exception` if there is an error while configuring the security filter chain.
---

#### 2.3 `addAuthority(RouteAuthority routeAuthority)`
Adds a `RouteAuthority` to the list of authorities. If the provided `RouteAuthority` does not have any associated roles, the path of the authority is added to the list of paths that should not be filtered by the advanced filter. If the advanced filter is not enabled, this method enables it and configures the `SecurityFilter` with the appropriate user repository class.
- **Parameters**:
  - `routeAuthority` - The `RouteAuthority` object representing the authority to be added.
---

#### 2.4 `setCsrfProtection(boolean csrfProtection)`
Enables or disables CSRF protection for the application.
- **Parameters**:
  - `csrfProtection` - `true` to enable CSRF protection, `false` to disable it.
---

#### 2.5 `isCalled()`
Marks the security configuration as initialized. This should be called after the configuration is properly set up.

