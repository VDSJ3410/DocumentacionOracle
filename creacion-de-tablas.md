---
description: >-
  La creación de tablas es una de las tareas más importantes en Oracle, ya que
  son la base de toda la estructura de datos
---

# Creación de Tablas

Una tabla permite almacenar información de manera organizada en filas y columnas, definiendo qué tipo de datos se van a guardar y bajo qué reglas.

En este proceso se utilizan **comandos SQL** como `CREATE TABLE`, junto con los **tipos de datos** (`VARCHAR2`, `NUMBER`, `DATE`, etc.) y las **restricciones** (`PRIMARY KEY`, `NOT NULL`, `UNIQUE`). Además, se recomienda incluir **comentarios en el código** para explicar la función de cada columna, lo que facilita la comprensión y el mantenimiento de la base de datos a futuro.

* Ejemplo trabajado en clase:

```
-- 1. Crear el usuario 
CREATE USER javapoo IDENTIFIED BY java
DEFAULT TABLESPACE users
TEMPORARY TABLESPACE temp
QUOTA UNLIMITED ON users;

-- 2. Dar privilegios básicos para conectarse y trabajar con sus tablas
GRANT CREATE SESSION TO javapoo ;
GRANT CREATE TABLE TO javapoo ;
GRANT CREATE SEQUENCE TO javapoo ;
GRANT CREATE VIEW TO javapoo ;
```

**Explicación:**

1. **`CREATE USER javapoo IDENTIFIED BY java`** → crea un nuevo usuario llamado _javapoo_ con la contraseña _java_.
2. **`DEFAULT TABLESPACE users`** → define en qué espacio de almacenamiento (tablespace) se guardarán, por defecto, los objetos que cree este usuario.
3. **`TEMPORARY TABLESPACE temp`** → asigna un espacio temporal para operaciones como ordenamientos o consultas grandes.
4. **`QUOTA UNLIMITED ON users`** → otorga espacio ilimitado dentro del tablespace _users_, permitiendo que el usuario pueda crear objetos sin restricciones de tamaño.
5. **`GRANT CREATE SESSION TO javapoo`** → le da permiso al usuario para conectarse a la base de datos (sin este permiso, el usuario no puede iniciar sesión).
6. **`GRANT CREATE TABLE TO javapoo`** → le permite crear sus propias tablas.
7. **`GRANT CREATE SEQUENCE TO javapoo`** → le permite crear secuencias, útiles para generar valores consecutivos (ejemplo: IDs automáticos).
8. **`GRANT CREATE VIEW TO javapoo`** → le permite crear vistas, que son consultas guardadas como si fueran tablas virtuales.

Este script permite que el usuario _javapoo_ exista en Oracle, tenga espacio para trabajar y cuente con los privilegios básicos necesarios para empezar a desarrollar sus propias estructuras (tablas, secuencias, vistas) dentro de la base de datos.
