# 📦 Proyecto de Normalización de Base de Datos en SQL

## Descripción

Este proyecto consiste en la limpieza, normalización e implementación de una base de datos de compras utilizando PostgreSQL. La base de datos fue diseñada a partir de un conjunto de datos con inconsistencias, aplicando las tres primeras formas normales (1FN, 2FN y 3FN) para mejorar la integridad y reducir la redundancia.

## Objetivos

- Identificar inconsistencias en la base de datos original.
- Estandarizar los datos.
- Aplicar el proceso de normalización.
- Crear una base de datos relacional en PostgreSQL.
- Establecer relaciones mediante claves primarias y foráneas.

## Inconsistencias encontradas

Durante el análisis de la base de datos se identificaron las siguientes inconsistencias:

- Registros duplicados de proveedores.
- Categorías y subcategorías repetidas.
- Diferentes formatos de fecha.
- Redundancia de información en productos y proveedores.
- Unidades de medida almacenadas como texto repetitivo.
- Falta de integridad referencial.

## Soluciones implementadas

Para solucionar las inconsistencias se realizaron las siguientes acciones:

- Creación de tablas independientes para proveedores, categorías, subcategorías, productos, bodegas y unidades de medida.
- Uso de claves primarias (`PRIMARY KEY`) para identificar cada registro.
- Implementación de claves foráneas (`FOREIGN KEY`) para relacionar las tablas.
- Estandarización de los tipos de datos.
- Eliminación de información redundante.

## Modelo de la base de datos

La base de datos está conformada por las siguientes tablas:

- Proveedores
- Categorías
- Subcategorías
- Unidades de medida
- Productos
- Bodegas
- Compras

### Relaciones

- Una categoría puede tener muchas subcategorías.
- Una subcategoría puede tener muchos productos.
- Una unidad de medida puede estar asociada a varios productos.
- Un proveedor puede registrar muchas compras.
- Un producto puede aparecer en muchas compras.
- Una bodega puede almacenar muchas compras.

## Tecnologías utilizadas

- PostgreSQL
- pgAdmin 4
- SQL

## Estructura del proyecto

```
Proyecto_SQL/
│
├── README.md
├── script.sql
├── modelo_relacional.png
├── base_datos.xlsx
└── evidencias/
```

## Cómo ejecutar el proyecto

1. Crear una base de datos en PostgreSQL.
2. Abrir pgAdmin.
3. Ejecutar el archivo `script.sql`.
4. Insertar los datos mediante los comandos `INSERT INTO`.
5. Verificar las relaciones entre las tablas.

## Normalización aplicada

### Primera Forma Normal (1FN)

- Eliminación de grupos repetitivos.
- Cada columna almacena un único valor.

### Segunda Forma Normal (2FN)

- Separación de entidades como proveedores, productos y categorías.

### Tercera Forma Normal (3FN)

- Eliminación de dependencias transitivas mediante tablas relacionadas.

## Autora

**Kerlys Bello D.**

Proyecto desarrollado para la asignatura de **Desarrollo de Software (SQL)**.
