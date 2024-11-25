# AdvancedFilterChecker

<p>The AdvancedFilterChecker class serves as a utility for managing advanced filtering configurations within the application. It provides methods to enable or disable advanced filtering, manage a list of paths that should be excluded from filtering, and verify whether a specific path is part of this exclusion list.</p>

This class is utilized by both [CoreSecurityConfig](../Main%20classes/CoreSecurityConfig.md) and [SecurityFilter](../Main%20classes/SecurityFilter.md) to streamline route authorization management, ensuring that specific paths are appropriately handled.

### 1. Attributes
<table>
    <thead>
        <th scope="col">Type</th>
        <th scope="col">Name</th>
        <th scope="col">Description</th>
    </thead>
    <tbody>
        <tr>
            <td><strong>boolean</strong></td>
            <td>isAdvancedFiltered</td>
            <td>A boolean attribute indicating if advanced filtering is enabled or not.</td>
        </tr>
        <tr>
            <td><strong>List&lt;String&gt;</strong></td>
            <td>shouldNotFilterPathList</td>
            <td>A list of paths that should not be filtered.</td>
        </tr>
    </tbody>
</table>
<br></br>

### 2. Methods

#### 2.1 `isAdvancedFiltered()`

Determines if advanced filtering is currently enabled.
This method retrieves the state of the `isAdvancedFiltered` attribute, which indicates whether advanced filtering is active in the application.

- **Returns**:
  `boolean` — `true` if advanced filtering is enabled; otherwise, `false`.
---

#### 2.2 `isInShouldNotFilterList(String pathToCompare)`

Checks whether the specified path should be excluded from filtering by comparing it against a list of paths that are explicitly marked to bypass filtering. This method verifies if the given path starts with any of the entries in the `shouldNotFilterPathList` attribute.

- **Parameters**:
  `pathToCompare` (`String`) — The path to be checked.

- **Returns**:
  `boolean` — `true` if the path matches any entry in the exclusion list; otherwise, `false`.
---

#### 2.3 `addShouldNotFilterPath(String path)`

Add a path to the list of paths that should not be filtered. The path is normalized by removing any wildcard suffix "/**" before adding it to the list.

- **Parameters:** `path (String)` - The path that will be added to the list of paths exempt from filtering.
---

#### 2.4 `setAdvancedFiltered(boolean isAdvancedFiltered)`

Sets the state of the advanced filter

- **Parameters:** `isAdvancedFiltered (boolean)`  - `true` to enable advanced filtering, `false` to disable it.