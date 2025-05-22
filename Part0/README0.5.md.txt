sequenceDiagram
    participant Browser
    participant Server

    Browser->>Server: GET /spa
    Server-->>Browser: HTML page
    Browser->>Server: GET /main.js
    Server-->>Browser: JavaScript file
    Browser->>Server: GET /data.json
    Server-->>Browser: JSON data with notes
    Browser->>Browser: Render the notes on the page using JavaScript
