0.4: new note

browser->server: HTTP POST https://studies.cs.helsinki.fi/exampleapp/new_note

note over server:
data is received from the browser
server creates a new note object and adds it to the notes array
end note

server-->browser: URL redirect
browser->server: HTTP GET https://studies.cs.helsinki.fi/exampleapp/notes
server-->browser: HTML-code
browser->server: HTTP GET https://studies.cs.helsinki.fi/exampleapp/main.css
server-->browser: main.css
browser->server: HTTP GET https://studies.cs.helsinki.fi/exampleapp/main.js
server-->browser: main.js

note over browser:
browser starts executing js-code
that requests JSON data (with the new note appended to it) from server
end note

browser->server: HTTP GET https://studies.cs.helsinki.fi/exampleapp/data.json
server-->browser: [{ content: "note", date: "yyyy-mm-dd" }, ...]

note over browser:
browser executes the event handler that renders notes to display
end note

0.5: Singe page app
browser->server: HTTP GET https://studies.cs.helsinki.fi/exampleapp/spa
server-->browser: HTML-code
browser->server: HTTP GET https://studies.cs.helsinki.fi/exampleapp/main.css
server-->browser: main.css
browser->server: HTTP GET https://studies.cs.helsinki.fi/exampleapp/spa.js
server-->browser: spa.js

note over browser:
browser starts executing js-code that requests JSON data from server 
end note

browser->server: HTTP GET https://studies.cs.helsinki.fi/exampleapp/data.json
server-->browser: [{ content: "note", date: "yyyy-mm-dd" }, ...]

note over browser:
browser executes the event handler that renders notes to display
end note

0.6: New note
browser->server: HTTP POST https://studies.cs.helsink.fi/exampleapp/new_note_spa

note over browser:
browser executes event handler that creates a new note and adds it the notes list, then rerenders the notes list
browser executes js code that sends the new note with an HTTP POST request and content-type JSON to the server.
end note