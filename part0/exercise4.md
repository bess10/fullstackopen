```mermaid
sequenceDiagram
participant user
participant browser
participant server


user->>browser: click on the save button on the form
browser->>server: POST https://fullstack-exampleapp.herokuapp.com/new_note
activate server
server-->>browser: HTTP 302 Found
servidor solicitad una redirección y el navegador recarga la página
browser->>server: GET https://studies.cs.helsinki.fi/exampleapp/notes
  activate server
  server-->>browser: HTML document
  deactivate server

browser->>server: GET https://studies.cs.helsinki.fi/exampleapp/main.css
  activate server
  server-->>browser: the css file
  deactivate server
browser->>server: GET https://studies.cs.helsinki.fi/exampleapp/main.js
  activate server
  server-->>browser: the JavaScript file
  deactivate server
browser->>server: GET https://studies.cs.helsinki.fi/exampleapp/data.json
  activate server
  server-->>browser: [{ "content": "HTML is easy", "date": "2023-1-1" }, ... ]
  deactivate server
```
