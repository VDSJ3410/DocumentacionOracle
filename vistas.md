---
description: >-
  Una vista es una consulta guardada en la base de datos que permite visualizar
  información proveniente de una o varias tablas, sin necesidad de escribir la
  consulta cada vez.
---

# Vistas

Sirve para **organizar, simplificar y proteger** los datos de los usuarios, mostrando solo la información necesaria.

#### 🔹 Tipos de vistas

* **Vista normal:** solo guarda la consulta, no los datos. Cada vez que se consulta, se ejecuta la sentencia SQL.
* **Vista materializada:** guarda físicamente los datos resultantes de la consulta, acelerando la lectura y reduciendo la carga de procesamiento.

#### 🧠 Ejemplo de vista normal

```
CREATE OR REPLACE VIEW VIW_CLIENTES_TELEFONOS AS
SELECT
    CLIENTES.ID_CLIENTE,
    TELEFONOS.ID_TELEFONO,
    CLIENTES.NOMBRE || ' ' || CLIENTES.APATERNO || ' ' || CLIENTES.AMATERNO AS NOMBRE_CLIENTE,
    CLIENTES.RFC,
    TELEFONOS.TELEFONO
FROM CLIENTES
LEFT JOIN TELEFONOS ON CLIENTES.ID_CLIENTE = TELEFONOS.ID_CLIENTE 
ORDER BY CLIENTES.NOMBRE, CLIENTES.APATERNO, CLIENTES.AMATERNO;
```

#### 🏗 Ejemplo de vista materializada

```
CREATE MATERIALIZED VIEW MV_CLIENTES_TELEFONOS
BUILD IMMEDIATE
REFRESH COMPLETE
START WITH SYSDATE
NEXT SYSDATE + 1/24
AS
SELECT
    CLIENTES.ID_CLIENTE,
    TELEFONOS.ID_TELEFONO,
    CLIENTES.NOMBRE || ' ' || CLIENTES.APATERNO || ' ' || CLIENTES.AMATERNO AS NOMBRE_CLIENTE,
    CLIENTES.RFC,
    TELEFONOS.TELEFONO
FROM CLIENTES
LEFT JOIN TELEFONOS ON CLIENTES.ID_CLIENTE = TELEFONOS.ID_CLIENTE
ORDER BY CLIENTES.NOMBRE, CLIENTES.APATERNO, CLIENTES.AMATERNO;
```

