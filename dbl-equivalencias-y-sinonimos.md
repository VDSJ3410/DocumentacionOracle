# DBL, Equivalencias y Sinónimos

#### 🔗 **Database Link (DBLink)**

Un **DBLink** permite **conectarse a otra base de datos desde una base actual**, como si fuera una extensión de la misma.\
Esto es útil cuando se trabaja con varias bases de datos distribuidas o remotas.

🧠 Ejemplo:

```
CREATE DATABASE LINK DBL_JAVAPOO
CONNECT TO JAVAPOO IDENTIFIED BY java
USING 'XE';
```

#### 🧩 **Equivalencias**

Las **equivalencias** se utilizan cuando queremos relacionar o igualar campos entre tablas diferentes, para lograr que los datos se correspondan correctamente en consultas o relaciones.

Ejemplo:

```
SELECT * FROM GERENTE@DBL_JAVAPOO;
SELECT * FROM EMPLEADO@DBL_JAVAPOO;
SELECT * FROM EMPLEADO;
```

#### 🧱 **Sinónimos**

Un **sinónimo** es un nombre alternativo para un objeto de la base de datos (una tabla, vista, secuencia, procedimiento, etc.).\
Facilita el acceso y evita escribir nombres largos o complejos.

Ejemplo:

```
CREATE SYNONYM EMPLEADO FOR EMPLEADO@DBL_JAVAPOO;
```

