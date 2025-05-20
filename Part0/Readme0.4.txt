# Exercise: Creating a new note

This diagram illustrates the sequence of events when a user creates a new note on the [example app](https://studies.cs.helsinki.fi/exampleapp/notes) and clicks the **Save** button.

## 🖼 Sequence Diagram (Image)

![Sequence diagram](./diagram.png)

## 💻 Sequence Diagram (Mermaid Code)

```mermaid
sequenceDiagram
    participant Browser
    participant Server

    Browser->>Browser: The user writes a note in the text field
    Browser->>Browser: The user clicks the "Save" button
    Browser->>Server: POST /new_note with the note content
    Server-->>Browser: 302 Redirect to /notes
    Browser->>Server: GET /notes
    Server-->>Browser: HTML page with the updated list of notes
    Browser->>Server: GET /main.js
    Server-->>Browser: main.js
    Browser->>Server: GET /data.json
    Server-->>Browser: JSON data with all notes
    Browser->>Browser: Render the notes on the page