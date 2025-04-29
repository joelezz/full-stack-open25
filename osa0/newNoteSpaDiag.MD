        sequenceDiagram
        participant user
        participant browser
        participant server

        user ->> browser: new note -> enter
        
        browser->> server: POST https://studies.cs.helsinki.fi/exampleapp/new_note_spa
        activate server
        server -->> browser: sends the response 200 and the content
        deactivate server 

        browser ->> server: GET https://studies.cs.helsinki.fi/exampleapp/data.json
        activate server
        server -->> browser: sends the JSON data to the browserS
        deactivate server

        browser:  JavaScript processes the data and dynamically updates the DOM
        browser -->> user: Show the web-page with all of the new content