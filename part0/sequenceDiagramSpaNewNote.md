sequenceDiagram
    participant browser
    participant server

    browser->> ads new note to Notes array
    browser ->> redraws notes list

    browser->>server: POST https://studies.cs.helsinki.fi/exampleapp/new_note_spa payload {content: "testing spa" date: "2025-09-26T20:16:33.711Z"}
    activate server
    server-->>browser: 201 response, message: "note created"
    deactivate server

    Note right of browser: The notes functionality is performed thanks the code inside the "window.onload" and "sendToServer" Javascript blocks.

    