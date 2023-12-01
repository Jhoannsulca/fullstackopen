<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Ejercicio 04 - Nuevo diagrama de notas</title>
</head>
<body>
    <pre class="mermaid">
        sequenceDiagram
            participant browser
            participant server
        
            browser->>server: POST https://studies.cs.helsinki.fi/exampleapp/new_note
            activate server
            server-->>browser: Document Redirect
            deactivate server

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
        
            Note right of browser: El navegador comienza a ejecutar el código JavaScript que recupera el JSON del servidor.
        
            browser->>server: GET https://studies.cs.helsinki.fi/exampleapp/data.json
            activate server
            server-->>browser: [{ "content": "HTML is easy", "date": "2023-1-12" }, ... ]
            deactivate server
        
            Note right of browser: El navegador ejecuta la función de devolución de llamada que muestra las notas.
    </pre>
    <script type="module">
      import mermaid from 'https://cdn.jsdelivr.net/npm/mermaid@10/dist/mermaid.esm.min.mjs';
    </script>
  </body>
</html>
