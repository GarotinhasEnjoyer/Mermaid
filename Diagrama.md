``` mermaid
flowchart TD
    A(Client) -->|Sends HTTP Request| B(Server - Spring Boot)
    style A fill:black,stroke:black,stroke-width:4px,shadow:shadow
    B --> C{Analyze Request}
    style B fill:,stroke:black,stroke-width:4px,shadow:shadow
    C -->|Valid URL and Method| D(Controller - ProductoController)
    style C fill:teal,stroke:black,stroke-width:4px,shadow:shadow
    D --> E{Valid Data}
    style D fill:black,stroke:black,stroke-width:4px,shadow:shadow
    E -->|Yes| F(Service Layer - ProductoService)
    E -->|No| G[Error 400 Bad Request]
    style E fill:teal,stroke:black,stroke-width:2px,shadow:shadow
    style G fill:Darkred,stroke:black,stroke-width:2px,shadow:shadow
    F --> H(Process Operation)
    style F fill:black,stroke:black,stroke-width:4px,shadow:shadow
    H --> I(Return Data to Controller)
    style H fill:Gray,stroke:black,stroke-width:2px,shadow:shadow
    I --> J[Prepare HTTP Response]
    style I fill:Darkorange,stroke:black,stroke-width:2px,shadow:shadow
    J --> K[Send Response to Client]
    style J fill:Darkblue,stroke:black,stroke-width:2px,shadow:shadow
    style K fill:Darkgreen,stroke:black,stroke-width:2px,shadow:shadow

```
