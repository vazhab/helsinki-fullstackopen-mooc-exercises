
<!-- In this diagram, the User first types the URL into the Browser. The Browser then requests the HTML from the Server, which returns the HTML to the Browser. The Browser then requests the data from the Server, which queries the data from the Database. The Database returns the data to the Server, which returns the data to the Browser.

When the User sends a new note, the Browser sends the note to the Server, which saves the note to the Database. The Database then returns the saved note to the Server, which returns the saved note to the Browser.

new_note	302	document / Redirect	Other	123 B	113 ms	
notes	200	document	new_note	414 B	113 ms	Stylesheetmain.css	200	stylesheet	notes	268 B	129 ms	
Scriptmain.js	200	script	notes	781 B	125 ms	XHRdata.json	200	xhr	main.js:23	5.8 kB	111 ms	XHRcontent.min.css	200	xhr	content.min.js:1	2.7 kB	6 ms	
Otherfavicon.ico	200	text/html	Other	212 B	107 ms	
-->

```mermaid

sequenceDiagram
    participant User
    participant Browser
    participant Server
    participant Database

    User->>Browser: Types URL
    Browser->>Server: Requests HTML
    Server-->>Browser: Returns HTML
    Browser->>Server: Requests Data
    Server-->>Database: Queries Data
    Database-->>Server: Returns Data
    Server-->>Browser: Returns Data
    Browser->>Server: Sends New Note Post Request
    Server-->>Database: Saves New Note
    Database-->>Server: Returns Saved Note
    Server-->>Browser: Returns Saved Note
