```mermaid
sequenceDiagram
    participant User
    participant Browser
    participant Controller
    participant Server
    participant Database

    User->>Browser: Enters data and submits form  # User fills out form and submits it
    Browser->>Controller: Sends form data  # Browser sends form data to the controller
    Controller->>Server: Sends AJAX request to save new note  # Controller sends an AJAX request to the server to save the new note
    Server->>Database: Processes request and saves new note  # Server processes the request and saves the new note to the database
    Database-->>Server: Returns success message  # Database returns a success message to the server
    Server-->>Controller: Returns success message to client  # Server returns the success message to the controller
    Controller-->>Browser: Displays success message  # Controller displays a success message to the user in the browser
