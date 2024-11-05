Código WSD:
```js
@startuml diagrama de uso
class Usuario {
    - idUsuario: int
    - nombre: String
    - correo: String
    - rol: String
    + getIdUsuario(): int
    + getNombre(): String
    + getCorreo(): String
}

class Producto {
    - idProducto: int
    - nombre: String
    - descripcion: String
    - precio: double
    + getIdProducto(): int
    + getNombre(): String
    + getPrecio(): double
}

class Inventario {
    - idInventario: int
    - idProducto: int
    - cantidadDisponible: int
    + getIdInventario(): int
    + getCantidadDisponible(): int
    + actualizarInventario(cantidad: int): void
}

class Factura {
    - idFactura: int
    - fecha: Date
    - total: double
    - idUsuario: int
    + getIdFactura(): int
    + getFecha(): Date
    + calcularTotal(): double
}

class DetalleFactura {
    - idDetalle: int
    - idFactura: int
    - idProducto: int
    - cantidad: int
    - subtotal: double
    + getIdDetalle(): int
    + calcularSubtotal(): double
}

Usuario "1" --> "0..*" Factura 
Factura "1" --> "0..*" DetalleFactura 
Producto "1" --> "0..*" DetalleFactura 
Producto "1" --> "1" Inventario 
Inventario "1" --> "1" Producto 
@enduml*

###FOTO###


Descripción del ejercicio
El ejercicio consiste en modelar un sistema básico de facturación mediante un diagrama de clases en UML. En este sistema, se identifican las entidades principales: Usuario, Producto, Inventario, Factura, y DetalleFactura. Cada clase representa un componente esencial del sistema, con atributos y métodos que definen su comportamiento y permiten la interacción entre sí.

Explicación y utilidad del diagrama
El diagrama de clases presentado es de tipo estructural y muestra las relaciones entre las entidades de un sistema de facturación. Cada clase contiene atributos (datos específicos de la entidad) y métodos (acciones que la entidad puede realizar). Este diagrama ayuda a visualizar cómo interactúan los elementos del sistema y a definir la estructura de datos y funcionalidades clave de cada entidad.

Propósito de cada clase
Usuario: Representa a los usuarios del sistema, quienes realizan compras. Almacena sus datos básicos y tiene métodos para obtener esta información.
Producto: Representa los productos disponibles en el sistema, con sus datos y precio.
Inventario: Lleva el control de la disponibilidad de productos, con métodos para actualizar la cantidad disponible.
Factura: Representa una factura generada al realizar una compra. Incluye métodos para calcular el total de la compra.
DetalleFactura: Almacena los detalles de cada producto incluido en una factura, como cantidad y subtotal.
Relación entre clases
Un Usuario puede tener múltiples Factura (relación "1 a muchos").
Una Factura contiene múltiples DetalleFactura, y cada DetalleFactura está asociado a un solo Producto.
Un Producto está registrado en el Inventario, donde se controla su disponibilidad.
Este diagrama permite definir la estructura base para un sistema de gestión de inventarios y facturación, facilitando la implementación y el mantenimiento del sistema.



