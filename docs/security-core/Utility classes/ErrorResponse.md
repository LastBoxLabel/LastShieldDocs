# ErrorResponse

Represents a standardized format for API error responses.This class includes three key properties: a message detailing the error, the HTTP status code associated with the error, and a timestamp indicating when the error occurred. Used by [GlobalExceptionHandler](GlobalExceptionHandler.md).

### 1. Attributes

<table>
  <thead>
    <tr>
      <th>Type</th>
      <th>Name</th>
      <th>Description</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>String</td>
      <td>message</td>
      <td>A description of the error that occurred.</td>
    </tr>
    <tr>
      <td>int</td>
      <td>statusCode</td>
      <td>The HTTP status code associated with the error.</td>
    </tr>
    <tr>
      <td>String</td>
      <td>timestamp</td>
      <td>A timestamp indicating when the error occurred, formatted as ISO 8601.</td>
    </tr>
  </tbody>
</table>
<br></br>

### 2. Methods

#### 2.1 `ErrorResponse(String message, int statusCode)`

Constructs a new `ErrorResponse` with the specified error message and status code. The timestamp is automatically set to the current date and time.

- **Parameters**:
  `message` (`String`) — The error message to be included in the response.
  `statusCode` (`int`) — The HTTP status code representing the error.

- **Returns**:
  `void` — This method does not return any value. It initializes the `ErrorResponse` with the provided message, status code, and the current timestamp.

---

#### 2.2 `getMessage()`

Gets the error message contained in the response.

- **Returns**:
  `String` — The error message.

---

#### 2.3 `getStatusCode()`

Gets the HTTP status code associated with the error.

- **Returns**:
  `int` — The HTTP status code representing the error.

---

#### 2.4 `getTimestamp()`

Gets the timestamp indicating when the error occurred.

- **Returns**:
  `String` — The timestamp when the error occurred.

