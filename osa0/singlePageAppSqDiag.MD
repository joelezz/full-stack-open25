        sequenceDiagram
        participant user
        participant browser
        participant server

        user ->> browser: https://studies.cs.helsinki.fi/exampleapp/spa -> enter
        
        browser->> server: get https://studies.cs.helsinki.fi/exampleapp/spa
        activate server
        server -->> browser: sends the HTML document to the browser
        deactivate server 

        browser->>server: GET https://studies.cs.helsinki.fi/exampleapp/main.css
        activate server
        server -->> browser: sends the CSS file to the browser
        deactivate server

        browser->>server: GET https://studies.cs.helsinki.fi/exampleapp/spa.js
        activate server
        server -->> browser: sends the JS file to the browser
        deactivate server

        browser->>server: GET https://studies.cs.helsinki.fi/exampleapp/data.json
        activate server
        server -->> browser: sends the JSON data to the browser
        deactivate server

        browser:  JavaScript processes the data and dynamically updates the DOM
        browser -->> user: Show the web-page with all of the content and styling