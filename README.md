# Descripción de la Base de Datos

La base de datos diseñada para el taller mecánico tiene como objetivo gestionar de manera eficiente la información clave relacionada con la operación del taller. A continuación, se presenta una descripción detallada de las entidades principales y su relación en el esquema:

## [Diagrama ER](schema.png)

## [Script](workshop.sql)

## 1. Usuario (User)

- **id (clave primaria):** Identificador único del usuario.
- **username:** Nombre de usuario para acceder al sistema.
- **email:** Dirección de correo electrónico del usuario.
- **password:** Contraseña segura del usuario.
- **role:** Rol del usuario en el taller (dueño, encargado, etc.).

## 2. Taller (Workshop)

- **id (clave primaria):** Identificador único del taller.
- **user_id:** Clave foránea que referencia al usuario dueño o encargado.
- **name:** Nombre del taller.
- **address:** Dirección física del taller.
- **phone:** Número de teléfono del taller.
- **email:** Correo electrónico del taller.

## 3. Cliente (Customer)

- **id (clave primaria):** Identificador único del cliente.
- **workshop_id:** Clave foránea que referencia al taller al que pertenece el cliente.
- **first_name:** Nombre del cliente.
- **last_name:** Apellido del cliente.
- **email:** Correo electrónico del cliente.
- **address:** Dirección del cliente.
- **phone:** Número de teléfono del cliente.

## 4. Vehículo (Vehicle)

- **id (clave primaria):** Identificador único del vehículo.
- **customer_id:** Clave foránea que referencia al cliente dueño del vehículo.
- **brand:** Marca del vehículo.
- **model:** Modelo del vehículo.
- **year:** Año de fabricación del vehículo.
- **license_plate:** Número de placa del vehículo.
- **chasis:** Número de chasis del vehículo.
- **kilometers:** Kilometraje actual del vehículo.

## 5. Mecánico (Mechanic)

- **id (clave primaria):** Identificador único del mecánico.
- **name:** Nombre del mecánico.
- **workshop_id:** Clave foránea que referencia al taller al que pertenece el mecánico.

## 6. Orden de Trabajo (Work Order)

- **id (clave primaria):** Identificador único de la orden de trabajo.
- **vehicle_id:** Clave foránea que referencia al vehículo asociado a la orden.
- **mechanic_id:** Clave foránea que referencia al mecánico asignado a la orden.
- **problem_description:** Descripción del problema a resolver.

## 7. Factura (Invoice)

- **id (clave primaria):** Identificador único de la factura.
- **work_order_id:** Clave foránea que referencia a la orden de trabajo asociada.
- **customer_id:** Clave foránea que referencia al cliente asociado.
- **total:** Monto total de la factura.

## 8. Pago (Payment)

- **id (clave primaria):** Identificador único del pago.
- **invoice_id:** Clave foránea que referencia a la factura asociada.
- **paid_amount:** Monto pagado en el pago.

Esta estructura de base de datos proporciona una plataforma sólida para la gestión integral de la información en un taller mecánico, desde la administración de clientes y vehículos hasta el seguimiento detallado de reparaciones y facturación.
