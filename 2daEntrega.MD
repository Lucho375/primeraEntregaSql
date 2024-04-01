# 2da Entrega SQL

### Para hacer los inserts :

> 1. Abrir la terminal y ubicarse en la carpeta inserts

```
cd inserts/
```

> 2. Ejecutar mysql desde la terminal

```
mysql -u root -p
```

> 3. Correr el siguiente comando

```sql
SOURCE main.sql
```

## Functions

### 1. getFullName

> Esta función toma un nombre y un apellido como entrada y devuelve el nombre completo concatenado.

#

> Objetivo: Proporcionar una forma conveniente de obtener el nombre completo de una persona.

#

> Datos/Tablas Manipuladas: No manipula directamente ninguna tabla, solo realiza operaciones de concatenación de cadenas.

### 2. calculateTotalInvoice

> Esta función calcula el total de la factura para una orden de trabajo específica.

#

> Objetivo: Permitir la recuperación del total de la factura asociada a una orden de trabajo.

#

> Datos/Tablas Manipuladas: Interactúa con la tabla invoice para calcular la suma total de las facturas asociadas a una orden de trabajo específica.

## Stored Procedures

## 1. CreateUser

## Parámetros de Entrada

> p_username: Nombre de usuario (VARCHAR, longitud máxima de 16 caracteres).

> p_email: Dirección de correo electrónico (VARCHAR, longitud máxima de 255 caracteres).

> p_password: Contraseña (VARCHAR, longitud máxima de 32 caracteres).

> p_role: Rol del usuario (VARCHAR, longitud máxima de 45 caracteres).

### Funcionalidad

> Inserta un nuevo registro en la tabla user con los valores proporcionados para cada columna.

### Objetivo

> Facilitar la creación de nuevos usuarios en la base de datos.

### Interacción con la Base de Datos

> Inserta datos en la tabla user.

## Views

### 1. customer_vehicle_info

> Esta vista combina información de la tabla customer y la tabla vehicle para proporcionar detalles sobre los clientes y sus vehículos.

#

### Campos seleccionados:

> customer_id: Identificación del cliente.

> first_name: Nombre del cliente.

> last_name: Apellido del cliente.

> vehicle_id: Identificación del vehículo.

> brand: Marca del vehículo.

> model: Modelo del vehículo.

### Interacción con la Base de Datos

> Realiza una operación de JOIN entre las tablas customer y vehicle.

### 2. billing_details

> Esta vista muestra detalles de facturación, incluido el monto total de la factura y el monto total pagado.

### Campos seleccionados:

> invoice_id: Identificación de la factura.

> total: Monto total de la factura.

> total_paid: Monto total pagado para la factura.

### Interacción con la Base de Datos

> Realiza una operación de LEFT JOIN entre las tablas invoice y payment, y utiliza la función COALESCE para manejar los casos en los que no hay pagos asociados.

### 3. work_order_summary

> Esta vista proporciona un resumen de las órdenes de trabajo, incluyendo detalles del vehículo, el nombre del mecánico y una descripción del problema.

### Campos seleccionados:

> work_order_id: Identificación de la orden de trabajo.

> brand: Marca del vehículo asociado a la orden de trabajo.

> model: Modelo del vehículo asociado a la orden de trabajo.

> mechanic_name: Nombre del mecánico asignado a la orden de trabajo.

> problem_description: Descripción del problema asociado a la orden de trabajo.

### Interacción con la Base de Datos

> Realiza operaciones de JOIN entre las tablas work_order, mechanic y vehicle.
