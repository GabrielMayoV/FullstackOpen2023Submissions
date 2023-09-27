``` mermaid
  sequenceDiagram
      participant browser
      participant server
  
      browser->>server: GET https://studies.cs.helsinki.fi/exampleapp/spa
      activate server
      server-->>browser: HTML document
      deactivate server
  
      browser->>server: GET https://studies.cs.helsinki.fi/exampleapp/main.css
      activate server
      server-->>browser: the css file
      deactivate server
  
      browser->>server: GET https://studies.cs.helsinki.fi/exampleapp/spa.js
      activate server
      server-->>browser: the single page JavaScript file
      deactivate server
  
      Note right of browser: The browser starts executing the JavaScript code that fetches the JSON from the server
  
      browser->>server: GET https://studies.cs.helsinki.fi/exampleapp/data.json
      activate server
      server-->>browser: [{ "content": "say sum", "date": "2023-09-26" }, ... ]
      deactivate server
  
      Note right of browser: The Javascript manipulates the DOM to add the ul to the web page
```
