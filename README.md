---
description: >-
  Oracle permite organizar, almacenar y manipular información de manera
  estructurada, garantizando seguridad, integridad y escalabilidad en los datos.
---

# Principios básicos

Oracle es uno de los sistemas gestores de bases de datos relacionales más utilizados a nivel mundial. Su importancia radica en que permite trabajar con **grandes volúmenes de información** de manera estructurada, segura y eficiente. Un gestor como Oracle organiza los datos en **tablas**, que pueden relacionarse entre sí mediante llaves primarias y foráneas.

Los principios básicos incluyen:

* **Modelo relacional:** todo se organiza en tablas que pueden relacionarse entre sí.
* **Independencia de datos:** los datos se pueden manipular sin alterar toda la estructura general.
* **Seguridad y control de acceso:** se pueden asignar permisos y roles para que solo ciertas personas modifiquen o consulten la información.
* **Integridad de datos:** mediante reglas y restricciones, se asegura que los datos sean correctos y coherentes.

Para empezar, Oracle utiliza ciertos **tipos de datos y comandos básicos**, entre los más comunes están:

* **`VARCHAR2(n)`**: sirve para almacenar texto de longitud variable, por ejemplo:

```
nombre VARCHAR2(50) -- texto de hasta 50 caracteres
```

* **`NUMBER(p,s)`**: se utiliza para números, enteros o decimales. `p` indica la precisión y `s` el número de decimales.

```
salario NUMBER(8,2) -- hasta 8 dígitos en total, 2 de ellos decimales
```

* **`DATE`**: almacena fechas (día, mes y año) e incluso horas si se requieren.

```
fecha_ingreso DATE
```

* **`CREATE TABLE`**: comando para crear una nueva tabla dentro de la base de datos.

```
CREATE TABLE empleados (...);
```

* **Restricciones más comunes:**
  * **`PRIMARY KEY`**: define la llave principal de la tabla (no se repite).
  * **`NOT NULL`**: evita que un campo quede vacío.
  * **`UNIQUE`**: asegura que no se repitan valores en esa columna.

Con estos ejemplos se puede entender cómo Oracle define y organiza la información desde lo más básico.
