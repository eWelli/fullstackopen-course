sequenceDiagram
NOTE over BROWSER: spa.js is loaded and executes form.onSubmit function
NOTE over BROWSER: which prevents normal get request and only sends POST with notes data.
BROWSER->>SERVER: POST request "https://studies.cs.helsinki.fi/exampleapp/new_note
NOTE over SERVER: Process spa.js
NOTE over SERVER: recieve POST Request data: note=what is life
NOTE over SERVER: SERVER pushes request note to the notes variable on server.
SERVER-->>BROWSER: HTML document
BROWSER->>SERVER: GET https://studies.cs.helsinki.fi/exampleapp/main.css
SERVER-->>BROWSER: main.css
BROWSER->>SERVER: https://studies.cs.helsinki.fi/exampleapp/main.js
SERVER-->>BROWSER: main.js
NOTE over BROWSER: BROWSER starts execution of main.js and requests data.json file.
BROWSER->>SERVER: GET request https://studies.cs.helsinki.fi/exampleapp/data.json
SERVER-->>BROWSER: Returns  list: [... {content: "what is life", date: "2022-12-01T16:51:35.079Z"}]
NOTE over BROWSER: Continue exection of main.js
loop JS Exection
    BROWSER->>BROWSER:Loop though data.json elements and add them to html via javascript.
end
BROWSER->>SERVER: GET https://studies.cs.helsinki.fi/favicon.ico
SERVER-->>BROWSER: favicon.ico


