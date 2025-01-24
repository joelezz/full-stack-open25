sequenceDiagram
    participant User
    participant Browser
    participant Server

    User ->> Browser: Enter New Note
    Browser ->> Server: POST https://studies.cs.helsinki.fi/exampleapp/notes
    activate Server
    Server -->> Browser: 200 [{ "content": "Mew Content added", "date": "2023-1-1" }, ... ]S
    deactivate Server

    Browser ->> Server: GET /main.css
    activate Server
    Server -->> Browser: CSS file
    deactivate Server

    Browser ->> Server: GET /spa.js
    activate Server
    Server -->> Browser: JavaScript file
    deactivate Server

    Browser ->> Server: GET /data.json
    activate Server
    Server -->> Browser: JSON data
    deactivate Server

    Browser ->> Browser: Process JSON and update DOM
    Browser -->> User: Render updated web page