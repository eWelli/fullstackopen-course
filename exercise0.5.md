sequenceDiagram
NOTE over BROWSER: spa.js is loaded and executes form.onSubmit function
NOTE over BROWSER: which prevents normal get request and only sends POST with notes data.
BROWSER->>SERVER: POST request https://studies.cs.helsinki.fi/exampleapp/new_note
NOTE over SERVER: Process spa.js
NOTE over SERVER: recieve POST Request data: note=what is life
NOTE over SERVER: SERVER pushes request note to the notes variable on server.
SERVER-->>BROWSER: HTML document



