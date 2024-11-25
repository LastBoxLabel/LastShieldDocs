# CorsConfig

The `CorsConfig` class is responsible for configuring Cross-Origin Resource Sharing (CORS) settings for the application. It provides flexible options to define allowed origins, methods, headers, and credentials, ensuring secure and efficient handling of cross-origin requests.

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
      <td>List&lt;String&gt;</td>
      <td>allowedOrigins</td>
      <td>List of origins allowed for cross-origin requests. If not set, defaults to <code>*</code> (all origins).</td>
    </tr>
    <tr>
      <td>List&lt;String&gt;</td>
      <td>allowedMethods</td>
      <td>List of HTTP methods allowed for cross-origin requests. If not set, defaults to <code>["GET", "POST", "PUT", "DELETE", "OPTIONS"]</code>.</td>
    </tr>
    <tr>
      <td>List&lt;String&gt;</td>
      <td>allowedHeaders</td>
      <td>List of HTTP headers allowed for cross-origin requests. If not set, defaults to <code>*</code> (all headers).</td>
    </tr>
    <tr>
      <td>Boolean</td>
      <td>allowCredentials</td>
      <td>Indicates whether credentials (cookies, HTTP authentication, etc.) are allowed in cross-origin requests. Defaults to <code>true</code>.</td>
    </tr>
    <tr>
      <td>Logger</td>
      <td>logger</td>
      <td>Logs messages related to CORS configuration setup.</td>
    </tr>
  </tbody>
</table>

<br></br>

### 2. Methods

#### 2.1 `Customizer<CorsConfigurer<HttpSecurity>> configure()`
Configures CORS settings for HTTP security. This method applies the specified CORS attributes (e.g., allowed origins, methods, headers, and credentials) to the security filter chain.

- **Returns:**
  A `Customizer` that applies CORS settings to `HttpSecurity`.

---

#### 2.2 `setAllowedOrigins(String origin)`
Adds a single origin to the list of allowed origins for cross-origin requests.

- **Parameters:**
  `origin` - The allowed origin to be added (e.g., `http://example.com`).

---

#### 2.3 `setAllowedOrigins(List<String> allowedOrigins)`
Sets the list of allowed origins for cross-origin requests.

- **Parameters:**
  `allowedOrigins` - A list of origins to allow (e.g., `["http://example.com", "http://another.com"]`).

---

#### 2.4 `setAllowedMethods(String method)`
Adds a single HTTP method to the list of allowed methods for cross-origin requests.

- **Parameters:**
  `method` - The allowed HTTP method to be added (e.g., `GET`).

---

#### 2.5 `setAllowedMethods(List<String> allowedMethods)`
Sets the list of allowed HTTP methods for cross-origin requests.

- **Parameters:**
  `allowedMethods` - A list of allowed HTTP methods (e.g., `["GET", "POST", "PUT"]`).

---

#### 2.6 `setAllowedHeaders(String header)`
Adds a single HTTP header to the list of allowed headers for cross-origin requests.

- **Parameters:**
  `header` - The allowed header to be added (e.g., `Authorization`).

---

#### 2.7 `setAllowedHeaders(List<String> allowedHeaders)`
Sets the list of allowed HTTP headers for cross-origin requests.

- **Parameters:**
  `allowedHeaders` - A list of allowed headers (e.g., `["Authorization", "Content-Type"]`).

---

#### 2.8 `setAllowCredentials(Boolean allowCredentials)`
Sets whether credentials (e.g., cookies, HTTP authentication) are allowed in cross-origin requests.

- **Parameters:**
  `allowCredentials` - `true` to allow credentials, `false` to disallow them.

---

### Usage

The `CorsConfig` class can be used to set up flexible and secure CORS configurations for your application. Below is an example of how to configure it:

```java
@Autowired
private CorsConfig corsConfig;

corsConfig.setAllowedOrigins(List.of("http://example.com"));
corsConfig.setAllowedMethods(List.of("GET", "POST"));
corsConfig.setAllowedHeaders(List.of("Authorization", "Content-Type"));
corsConfig.setAllowCredentials(true);
