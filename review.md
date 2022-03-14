# Review

## Requesting data using `fetch`

_index.html:_
```html
<!DOCTYPE html>
<html>
  <head>...</head>
  <body>
    ...
    <script src="main.js"></script>
  </body>
</html>
```

_main.js:_
```js
const url = `...`;

// Use "fetch" to request data file
fetch(url)
  .then(resp => resp.json())
  .then(data => {
    // Process and display data
    ...
  });
```

```mermaid
sequenceDiagram
    actor You
    participant Browser
    participant Static Server

    You->>Browser: Go to web page's URL
    activate Browser
    Browser-->>Browser: Read HTML code
    Browser-->>Browser: Read JavaScript code
    Browser->>Static Server: Use "fetch" to request data
    activate Static Server
    Static Server-->>Static Server: Read data file
    Static Server->>Browser: Respond with file content
    deactivate Static Server
    Browser-->>Browser: Process and display data
    deactivate Browser
```

Using `fetch` to request data from an API is an inherently similar process. The server may do something different than just read a file, but that doesn't matter; it's all going to look the same to you.

```mermaid
sequenceDiagram
    actor You
    participant Browser
    participant API Server

    You->>Browser: Go to web page's URL
    activate Browser
    Browser-->>Browser: Read HTML code
    Browser-->>Browser: Read JavaScript code
    Browser->>API Server: Use "fetch" to request data
    activate API Server
    API Server-->>API Server: Generate data based on request
    API Server->>Browser: Respond with generated content
    deactivate API Server
    Browser-->>Browser: Process and display data
    deactivate Browser
```
