# Usuario guarda su información

### Definir actores y casos de uso
actor Usuario
actor "Google/Facebook" as OAuth
actor "API Vehículos" as API

### Definir el diagrama de casos de uso

```mermaid
graph TD
    Usuario --> A[Iniciar sesión con Google]
    Usuario --> B[Iniciar sesión con Facebook]
    Usuario --> C[Guardar información personal]
    Usuario --> D[Buscar vehículos]
    Usuario --> E[Guardar vehículos]

    A --> F[OAuth - Google Autenticación]
    B --> G[OAuth - Facebook Autenticación]
    C --> H[Base de datos - Guardar nombre completo, correo, fecha de nacimiento, foto de perfil]
    D --> I[Conectar con API para obtener información de vehículos]
    E --> J[Guardar uno o más vehículos en la API]

    I --> |Límite de llamadas 1000| K[API - Obtener detalles del vehículo]
```

### Explicación:
- Los actores involucrados son **Usuario**, **OAuth (Google/Facebook)** y **API Vehículos**.
- Los casos de uso incluyen la autenticación con Google o Facebook, el almacenamiento de información personal, la búsqueda y el guardado de vehículos.
- El bloque Mermaid es responsable de generar el diagrama de flujo.

---

# Listado/agendado de servicio

### Definir actores y casos de uso
actor Usuario
actor "Sistema de Servicios" as Servicios

### Definir el diagrama de casos de uso

```mermaid
graph TD
    Usuario --> A[Leer servicios]
    Usuario --> B[Escoger uno o más servicios]
    Usuario --> C[Elige un solo vehículo]
    Usuario --> D[Crear solicitud de servicio]
    Usuario --> E[Proponer detalles del servicio.]
    Usuario --> F[Calcular precio final]
    Usuario --> G[Aceptar servicio]

    Servicios --> A
    Servicios --> F

    F --> H[Mapear tipo de auto con servicio para calcular el precio final]
    D --> |Consideración de tipo de servicio| I[Agregar ventana para conseguir piezas/refacciones]
```


### Explicación:
- Diagrama con los actores **Usuario** y **Sistema de Servicios**.
- Los casos de uso cubren la selección de servicios, la creación de una solicitud, la propuesta de detalles, el cálculo del precio final y la aceptación del servicio.

---

# Portal de pago

### Definir actores y casos de uso
actor Usuario
actor "Sistema de Pago" as Stripe

### Definir el diagrama de casos de uso

```mermaid
graph TD
    Usuario --> A[Ingresar datos de tarjeta]
    A --> B[Validar datos de tarjeta]
    B --> C[Procesar pago]

    C --> Stripe[Procesar pago con Stripe]

    Stripe --> D[Enviar confirmación de pago]

    D --> E[Mostrar confirmación de pago]
```

### Explicación:
- Los actores involucrados son **Usuario** y **Sistema de Pago (Stripe)**.
- Los casos de uso incluyen la entrada de datos de la tarjeta, la validación de los datos, el procesamiento del pago y la confirmación del pago.

---

# Listado de solicitudes y órdenes

### Definir actores y casos de uso
actor Usuario
actor "Sistema de Notificaciones" as Notificaciones
actor "Perfil Administrativo" as Admin

### Definir el diagrama de casos de uso

```mermaid
graph TD
    Usuario --> A[Recap del servicio]
    A --> B[Mostrar información de driver]
    A --> C[Enviar confirmación por correo]
    A --> D[Enviar mensaje por WhatsApp]
    A --> E[Mostrar detalles con fotografías y videos]
    A --> F[Mostrar barra de seguimiento]

    F --> G[Fotografías y videos]
    F --> H[Notas]
    F --> I[Reportes]
    F --> J[Notificación de entrega]

    Notificaciones --> C
    Notificaciones --> D

    Admin --> A
    Admin --> F

    Admin --> K[Ver detalles de la orden]
    Admin --> L[Ver historial de órdenes]
    
```

### Explicación:
- Los actores involucrados son **Usuario**, **Sistema de Notificaciones** y **Perfil Administrativo**.
- Los casos de uso incluyen la visualización de información del conductor, la confirmación por correo, el envío de mensajes por WhatsApp, la visualización de detalles con fotos y videos, la barra de seguimiento y la notificación de entrega.

---

# Confirmación de la cita

### Definir actores y casos de uso
actor Usuario
actor "Sistema de Confirmación" as Confirmación

### Definir el diagrama de casos de uso

```mermaid
graph TD
    Usuario --> A[Confirmar orden]
    A --> B[Enviar confirmación al sistema]

    Confirmación --> B

    B --> C[Enviar confirmación por correo]
    B --> D[Enviar mensaje por WhatsApp]
    B --> E[Mostrar detalles con fotografías y videos]
    B --> F[Mostrar barra de seguimiento]

    F --> G[Fotografías y videos]
    F --> H[Notas]

```

### Explicación:
- Los actores involucrados son **Usuario** y **Sistema de Confirmación**.
- Los casos de uso incluyen la confirmación de la orden, el envío de confirmación al sistema, la confirmación por correo, el envío de mensajes por WhatsApp, la visualización de detalles con fotos y videos, la barra de seguimiento y las notas.

---

# Notificaciones

### Definir actores y casos de uso
actor Usuario
actor "Sistema de Notificaciones" as Notificaciones

### Definir el diagrama de casos de uso

```mermaid
graph TD
    Usuario --> A[Recibir notificaciones]
    A --> B[Notificaciones previas al servicio]
    A --> C[Notificaciones durante el servicio]
    A --> D[Notificaciones después del servicio]

    B --> E[Opción de reagendar]

    C --> F[Notificación de llegada del conductor]
    C --> G[Notificación de inicio del servicio]
    C --> H[Notificación de finalización del servicio]

```

### Explicación:
- Los actores involucrados son **Usuario** y **Sistema de Notificaciones**.
- Los casos de uso incluyen la recepción de notificaciones, las notificaciones previas, durante y después del servicio, y la opción de reagendar.

---

# Mapa

### Definir actores y casos de uso
actor Usuario
actor "Sistema de Mapa" as Mapa
actor "Driver" as Driver

### Definir el diagrama de casos de uso

```mermaid
graph TD
    Usuario --> A[Ver ubicación del driver]
    A --> B[Ubicación al recoger el auto]
    A --> C[Ubicación en camino al taller]
    A --> D[Ubicación al entregar el auto]
    A --> E[Llamar al driver]
    A --> F[Chatear con el driver]

    Driver --> E
    Driver --> F

    Mapa --> B
    Mapa --> C
    Mapa --> D
```

### Explicación:
- Los actores involucrados son **Usuario**, **Sistema de Mapa** y **Driver**.
- Los casos de uso incluyen la visualización de la ubicación del conductor, la ubicación al recoger el auto, en camino al taller y al entregar el auto, y la posibilidad de llamar o chatear con el conductor.

---

# Perfil

# Diagrama de casos de uso: Calificación a driver y del servicio

### Definir actores y casos de uso
actor Usuario
actor "Sistema de Calificación" as Calificación

### Definir el diagrama de casos de uso

```mermaid
graph TD
    Usuario --> A[Calificar servicio]
    A --> B[Dar calificación de estrellas]
    A --> C[Dejar comentarios]

    Usuario --> D[Calificar driver]
    D --> B
    D --> C

    Calificación --> B
    Calificación --> C
```

### Explicación:
- Los actores involucrados son **Usuario** y **Sistema de Calificación**.
- Los casos de uso incluyen la calificación del servicio y del conductor, con la posibilidad de dar una calificación de estrellas y dejar comentarios.

---

# Listado/registro de autos

### Definir actores y casos de uso
actor Usuario
actor "Sistema de Gestión de Autos" as Gestión

### Definir el diagrama de casos de uso

```mermaid
graph TD
    Usuario --> A[Ver listado de autos]
    A --> B[Botones de cada auto]
    A --> C[Servicios realizados]
    A --> D[Próximos servicios]
    A --> E[Reminders de trámites]

    Gestión --> C
    Gestión --> D

    B --> F[Detalles del auto]
    D --> G[Fecha recomendada]
    D --> H[Cotización]

    E --> I[Notificaciones de trámites]

```

### Explicación:
- Los actores involucrados son **Usuario** y **Sistema de Gestión de Autos**.
- Los casos de uso incluyen la visualización de un listado de autos, los botones de cada auto, los servicios realizados, los próximos servicios y los reminders de trámites.

---
