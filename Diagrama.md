graph TD
    A[Cliente] -->|Envía solicitud HTTP| B[Servidor (Spring Boot)]
    B -->|Analiza ruta y método HTTP| C[Controlador (ProductoController)]
    C -->|Extrae y valida datos| D{Datos válidos?}
    D -->|No| E[Devuelve 400 Bad Request]
    D -->|Sí| F[Capa de Servicio (ProductoService)]
    F -->|Procesa operación| G[Devuelve datos al Controlador]
    G -->|Prepara respuesta HTTP| H[Respuesta JSON con código de estado]
    H -->|Envia respuesta al cliente| A
