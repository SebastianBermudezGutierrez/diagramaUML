## Problema del Carrito de Compras

- El proyecto consiste en desarrollar una base de datos para un sistema de carrito de compras, donde los
estudiantes deberán manejar roles de administrador y comprador. Además, deberán realizar consultas SQL
como JOINs entre varias entidades. Las entidades mínimas que deben incluirse son Usuario, Producto,
Inventario, Detalle Factura y Factura. Cada ejercicio debe involucrar al menos cuatro entidades, y se deben
entregar scripts DDL y DML completos. El objetivo es que los estudiantes utilicen y generen la
documentación del proyecto de acuerdo con lo enseñado en clase, utilizando un archivo .md y generando
diagramas de clase parciales y generales.


## construccion del codigo en plantUML

´´´sql
@startuml
package "Sistema de Carrito de Compras" {

    component "Interfaz " {
        [Vista de Productos]
        [Carrito de Compras]
        [Gestión de Usuario]
        [Confirmación de Pedido]
    }

    component "Backend " {
        [ServicioUsuario]
        [ServicioProducto]
        [ServicioFactura]
        [ServicioInventario]
        [ServicioDetalleFactura]
    }

    component "Base de Datos " {
        [Usuario]
        [Producto]
        [Inventario]
        [Factura]
        [DetalleFactura]
    }

    component "Autenticación " {
        [Validación de Usuario]
        [Generador de Tokens]
    }

    component "Servidor Web " {
        [Distribución de Archivos]
        [Proxy Reverso]
    }
    
    "Interfaz " -down-> "Backend " : Peticiones REST 
    "Backend " -down-> "Base de Datos " : Operaciones CRUD 
    "Autenticación " -left-> "Backend " : Control de Acceso
    "Servidor Web " -down-> "Interfaz " : Distribución de Archivos Estáticos
    "Servidor Web " -down-> "Backend " : Proxy Reverso
}
@enduml

## Diagrama Componentes

![base datos](https://github.com/user-attachments/assets/f27a8b92-5e98-426e-a750-4b629649e05c)
