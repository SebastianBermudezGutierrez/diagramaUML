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

    component "Frontend (React/Vue)" {
        [Vista de Productos]
        [Carrito de Compras]
        [Gestión de Usuario]
        [Confirmación de Pedido]
    }

    component "Backend (Java Spring Boot)" {
        [UsuarioService]
        [ProductoService]
        [FacturaService]
        [InventarioService]
        [DetalleFacturaService]
    }

    component "Base de Datos (MySQL/PostgreSQL)" {
        [Usuario]
        [Producto]
        [Inventario]
        [Factura]
        [DetalleFactura]
    }

    component "Autenticación (JWT/Spring Security)" {
        [Validación de Usuario]
        [Generador de Tokens]
    }

    component "Servidor Web (Nginx)" {
        [Distribución de Archivos]
        [Proxy Reverso]
    }

    ' Dependencias y Conexiones'
    "Frontend (React/Vue)" -down-> "Backend (Java Spring Boot)" : Peticiones REST 
    "Backend (Java Spring Boot)" -down-> "Base de Datos (MySQL/PostgreSQL)" : Operaciones CRUD 
    "Autenticación (JWT/Spring Security)" -left-> "Backend (Java Spring Boot)" : Control de Acceso
    "Servidor Web (Nginx)" -down-> "Frontend (React/Vue)" : Distribución de Archivos Estáticos
    "Servidor Web (Nginx)" -down-> "Backend (Java Spring Boot)" : Proxy Reverso
}
@enduml

## Diagrama Componentes

![base datos](https://github.com/user-attachments/assets/f27a8b92-5e98-426e-a750-4b629649e05c)
