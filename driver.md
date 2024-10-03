# 1.Registro e Inicio de Sesión

### Definir actores y casos de uso
Usuario: Interactúa con el sistema para registrarse o iniciar sesión.

Sistema de Autenticación (Auth): Responsable de validar el correo o el número de teléfono.

Redes Sociales: Servicios externos (Google, Facebook, etc.)

### Definir el diagrama de casos de uso

```mermaid
graph TD
    Usuario --> A[Registrarse con correo electrónico]
    Usuario --> B[Registrarse con número de teléfono]
    Usuario --> C[Registrarse con redes sociales]
    Usuario --> D[Iniciar sesión con correo/número]
    Usuario --> E[Iniciar sesión con redes sociales]

    A --> F[Auth - Verificar correo]
    B --> G[Auth - Verificar número de teléfono]
    C --> H[RedesSociales - Autenticación OAuth]
    
    D --> I[Auth - Validar credenciales]
    E --> J[RedesSociales - Autenticación OAuth]
```
# 2. Credenciales

### Definir actores y casos de uso
actor Administrador
actor Driver
actor "Sistema de Autenticación" as Autenticación

### Diagrama de casos de uso

```mermaid
graph TD
    Administrador --> A[Asignar credenciales al driver]
    A -->Driver
    Driver --> B[Iniciar sesión en su portal]
    B --> C[Acceder a su perfil]

```
# 3. Servicios Agendados

### Definir actores y casos de uso
El driver recolectara dependiendo la fecha

### Diagrama de casos de uso

```mermaid
graph TD
    Driver --> A[Administrar servicios]
    A --> B[Consultar calendario]
    A --> D[ubicación]
    A --> E[Confirmar servicio]
    A --> c[Cancelar]

    Servicios --> B
    Servicios --> D
    
```

# 4. Recolección

### Definir actores y casos de uso
llegada a la ubicación, la consulta de la ubicación mediante Google Maps API, la comunicación con el cliente, la toma de evidencia y la recopilación de datos adicionales.

### Diagrama de casos de uso

```mermaid
graph TD
    Driver --> A[Llegar a la ubicación]
    A --> B[Consultar ubicación en Google Maps,api]
    A --> C[Comunicarse con el cliente]
    A --> D[Tomar evidencia]
    A --> E[Recopilar datos adicionales]

    Maps --> B

```
# 5. Pago

### Definir actores y casos de uso
actor Driver
actor "Sistema de Pago" as Pago

### Diagrama de casos de uso

```mermaid
graph TD
    Driver --> A[Iniciar proceso de pago]
    A --> B[Seleccionar método de pago]
    A --> C[Agregar servicios adicionales]
    A --> D[Confirmar pago]

    B --> E[Efectivo]
    B --> F[Transferencia]
```
# 6. Comunicación

### Definir actores y casos de uso
El inicio de la comunicación, el envío de mensajes por WhatsApp, la realización de llamadas y la notificación al usuario sobre cambios en el servicio.


### Diagrama de casos de uso

```mermaid
graph TD
    Driver --> A[Iniciar comunicación]
    A --> B[Enviar mensaje por WhatsApp]
    A --> C[Hacer llamada]
    A --> D[Notificar al usuario sobre cambios]
```
# 7. Entrega

### Definir actores y casos de uso
ncluyen el aviso al usuario antes de salir del mecánico, el llenado del reporte de servicio y el envío del reporte al cliente.

### Diagrama de casos de uso

```mermaid
graph TD
    Driver --> A[Avisar al usuario antes de salir del mecánico]
    A --> B[Llenar reporte de servicio]
    A --> C[Enviar reporte al cliente]
    A --> Entrega

    Entrega --> B
```
# 8. Perfil del Driver

### Definir actores y casos de uso
actor Driver
actor "Sistema de Perfil" 

### Diagrama de casos de uso

```mermaid
graph TD
    Driver --> A[Acceder al perfil]
    A --> B[Consultar ganancias]
    A --> C[Consultar servicios realizados]
    A --> D[Consultar recolecciones]
    A --> E[Modificar información personal]

    Perfil --> B
    Perfil --> C
    Perfil --> D
    Perfil --> E

