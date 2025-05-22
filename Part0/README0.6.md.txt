sequenceDiagram
    participant Browser
    participant Server

    Browser->>Browser: User writes a new note in the input field
    Browser->>Browser: User clicks the "Save" button
    Browser->>Server: POST /new_note with note content (sent via JavaScript)
    Server-->>Browser: Response (usually status 201 or confirmation)
    Browser->>Server: GET /data.json (to refresh notes list)
    Server-->>Browser: JSON data with updated notes
    Browser->>Browser: Update the list of notes on the page dynamically