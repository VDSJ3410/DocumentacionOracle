---
description: >-
  Una bitácora es un registro donde se documentan los cambios, pruebas o
  modificaciones realizadas en las tablas de una base de datos.
---

# Bitácoras

### **Funciones principales:**

1. Controlar qué se hizo en cada tabla y en qué fecha.
2. Registrar observaciones para mantener un historial.
3. Servir de apoyo en auditorías, errores o revisiones.

```
-- Creación de la tabla empleados_bit (bitácora de la tabla empleados)
CREATE TABLE empleados_bit (
    id_empleado   NUMBER(5),          -- Identificador del empleado
    nombre        VARCHAR2(50),       -- Nombre del empleado
    puesto        VARCHAR2(30),       -- Puesto de trabajo
    salario       NUMBER(8,2),        -- Salario
    fecha_ingreso DATE,               -- Fecha de ingreso
    fecha_modif   DATE,               -- Fecha de modificación del registro
    ip_usuario    VARCHAR2(20),       -- IP desde donde se hizo la acción
    folio         NUMBER(10),         -- Número de folio único
    anio          NUMBER(4)           -- Año de la modificación
);
```

* **Objetivo de la bitácora:** explicar por qué se hace, más allá de solo funciones. Por ejemplo:
  * Garantizar la trazabilidad de los cambios.
  * Facilitar la identificación de errores o inconsistencias.
  * Servir como registro histórico para consultas futuras.
* **Cómo se llenaría la bitácora:** una pequeña nota sobre que cada vez que se modifica un registro en la tabla principal, se inserta automáticamente o manualmente un registro en la tabla `_bit`.

**Nota sobre buenas prácticas:** algo breve como:

* Siempre mantener los nombres consistentes (`_bit`) para diferenciar las tablas principales de sus bitácoras.
* Registrar toda la información necesaria para auditoría o seguimiento de cambios.

#### Conclusión

Los principios básicos de Oracle muestran cómo este gestor organiza la información a través de tipos de datos, restricciones y comandos. Con la práctica de creación de tablas se reforzó el uso de **comentarios para documentar el código**, y con la elaboración de **bitácoras** se comprendió la importancia del registro y control de actividades en una base de datos.
