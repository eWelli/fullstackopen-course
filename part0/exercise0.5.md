## Single page app diagram - site https://studies.cs.helsinki.fi/exampleapp/spa


```mermaid
sequenceDiagram
    BROWSER->>SERVER: GET https://studies.cs.helsinki.fi/exampleapp/spa
    SERVER-->>BROWSER: HTML document
    BROWSER->>SERVER: GET https://studies.cs.helsinki.fi/exampleapp/main.css
    SERVER-->>BROWSER: main.css
    BROWSER->>SERVER: GET https://studies.cs.helsinki.fi/exampleapp/spa.js
    SERVER-->>BROWSER: spa.js
    NOTE over BROWSER: spa.js starts executing makes GET request to "/exampleapp/data.json"
    BROWSER->>SERVER: GET request https://studies.cs.helsinki.fi/exampleapp/data.json
    SERVER-->>BROWSER: Returns a list [... {...}]
    NOTE over SERVER: Continue spa.js exection
    loop JS forEach
        BROWSER->>BROWSER:Loop though data.json elements and add them to html via javascript.
    end
    BROWSER->>SERVER: GET https://studies.cs.helsinki.fi/favicon.ico
    SERVER-->>BROWSER: favicon.ico
```

[Previous exercise](exercise0.4.md)

[Next exercise](exercise0.6.md)