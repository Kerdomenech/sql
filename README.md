# 📦 Proyecto de Normalización de Base de Datos en SQL

# Inventory Management Database

## Project Description

This project consists of the design and implementation of a relational database for an inventory management system. The database allows managing suppliers, products, warehouses, purchases, inventory movements, categories, and units of measure. The objective is to guarantee data integrity, optimize inventory control, and facilitate business decision-making through SQL queries.

---

## Technologies Used

- PostgreSQL
- SQL
- pgAdmin 4
- Git
- GitHub

---

## Database Engine

PostgreSQL 17

---

## Normalization Process

The database was normalized up to the Third Normal Form (3NF).

### First Normal Form (1NF)

- Atomic values.
- No repeating groups.
- Primary keys defined for every table.

### Second Normal Form (2NF)

- Partial dependencies were removed.
- All non-key attributes depend on the whole primary key.

### Third Normal Form (3NF)

- Transitive dependencies were eliminated.
- Independent tables were created for:
  - Cities
  - Categories
  - Subcategories
  - Units of Measure

---

## Database Structure

The project contains the following tables:

- ciudades
- proveedores
- categorias
- sub_categorias
- unidades_medidas
- productos
- bodegas
- compras
- detalle_compras
- movimientos_inventario

---

## Entity Relationship Model

The Entity Relationship Model (ERM) defines the relationships between products, suppliers, warehouses, purchases, and inventory movements using primary and foreign keys.

---

## Installation Instructions

1. Install PostgreSQL.
2. Install pgAdmin 4.
3. Create a new database.
4. Execute the SQL script.
5. Run the INSERT statements.
6. Execute the SQL queries.

---

## Database Creation

The database was created using SQL DDL statements:

- CREATE DATABASE
- CREATE TABLE
- PRIMARY KEY
- FOREIGN KEY
- UNIQUE
- CHECK
- NOT NULL

---

## Data Loading Process

The database was populated manually using SQL INSERT INTO statements while respecting all integrity constraints.

---

## SQL Queries Explanation

The project includes SQL queries that allow:

- Inventory available by product.
- Products stored in each warehouse.
- Total purchases by supplier.
- Products with the lowest stock.
- Five most purchased products.
- Inventory value by city.
- JOIN operations.
- Aggregate functions.
- Business reports.

---

## Developer Information

**Full Name:** Kerlys Bello D. **MALECON**



* Explicación de la normalización* español



Primera Forma Normal (1FN)
Cada tabla posee una clave primaria.
No existen grupos repetitivos.
Todos los atributos contienen valores atómicos.

Ejemplo:

❌ Incorrecto

Producto	Teléfonos
Martillo	3001,3002

✅ Correcto

Producto	Teléfono
Martillo	3001
Martillo	3002
Segunda Forma Normal (2FN)

Todos los atributos dependen completamente de la clave primaria.

Ejemplo:

La información del proveedor se separó de la tabla de compras.

*-Antes-*

Compras

Proveedor
Teléfono
Dirección
Producto
Cantidad

*-Después-*

Proveedores

Compras
Tercera Forma Normal (3FN)

Se eliminaron dependencias transitivas.

Ejemplo

*-Antes-*

Producto
Categoría
Subcategoría

*-Después-*

Categorias

↓

Subcategorias

↓

Productos

Esto evita duplicidad de información.

3. Modelo Entidad Relación (MER)

El MER del proyecto es así:

                    CIUDADES
                  id_ciudad (PK)
                        │
                        │ 1:N
                        │
                PROVEEDORES
              id_proveedor (PK)
                        │
                        │ 1:N
                        │
                  COMPRAS
                id_compra (PK)
                        │
                        │ 1:N
                        │
              DETALLE_COMPRAS
                        │
          ┌─────────────┴─────────────┐
          │                           │
          │ N:1                       │ N:1
          │                           │
      PRODUCTOS                  BODEGAS
  id_producto (PK)            id_bodega (PK)
          │
          │ N:1
          │
 SUB_CATEGORIAS
 id_sub_categoria (PK)
          │
          │ N:1
          │
   CATEGORIAS
 id_categoria (PK)

PRODUCTOS
      │
      │ N:1
      │
UNIDADES_MEDIDAS

PRODUCTOS
      │
      │ 1:N
      │
MOVIMIENTOS_INVENTARIO



4. Modelo Relacional
CIUDADES
---------
id_ciudad (PK)
nombre_ciudad
pais

PROVEEDORES
------------
id_proveedor (PK)
nombre_proveedor
nit
telefono
email
id_ciudad (FK)

CATEGORIAS
------------
id_categoria (PK)
nombre_categoria

SUB_CATEGORIAS
---------------
id_sub_categoria (PK)
nombre_sub_categoria
id_categoria (FK)

UNIDADES_MEDIDAS
-----------------
id_unidad_medida (PK)
unidad_medida
abreviatura

PRODUCTOS
-----------
id_producto (PK)
nombre_producto
descripcion
precio_unitario
id_sub_categoria (FK)
id_unidad_medida (FK)

BODEGAS
---------
id_bodega (PK)
nombre_bodega

COMPRAS
---------
id_compra (PK)
fecha_compra
id_proveedor (FK)

DETALLE_COMPRAS
----------------
id_detalle (PK)
id_compra (FK)
id_producto (FK)
id_bodega (FK)
cantidad
precio_compra
subtotal

MOVIMIENTOS_INVENTARIO
-----------------------
id_movimiento (PK)
fecha_movimiento
tipo_movimiento
cantidad
id_producto (FK)
id_bodega (FK)
