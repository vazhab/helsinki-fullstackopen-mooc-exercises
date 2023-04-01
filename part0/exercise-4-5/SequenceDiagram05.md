```mermaid
sequenceDiagram
    participant User
    participant Browser
    participant Controller
    participant Server
    participant Database

    User->>Browser: Enters data and submits form  # User fills out form and submits it
    Browser->>Controller: Sends form data  # Browser sends form data to the controller
    Controller->>Server: Sends AJAX request  # Controller sends an AJAX request to the server
    Server->>Database: Processes request and queries database  # Server processes the request and queries the database for data
    Database-->>Server: Returns data  # Database returns the requested data to the server
    Server-->>Controller: Returns data to client  # Server returns the data to the controller, which updates the view in the browser
    Controller-->>Browser: Updates view  # Controller updates the view in the browser based on the returned data
