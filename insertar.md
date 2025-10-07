---
description: >-
  El comando INSERT se usa para agregar registros nuevos a las tablas. Puede
  hacerse directamente, o mediante un procedimiento almacenado, para automatizar
  procesos.
---

# Insertar

### Insert de Clientes

```
INSERT INTO CLIENTES (NOMBRE, APATERNO, AMATERNO, RFC, FECHA_ALTA) VALUES('Ana', 'Gomez', 'Perez', 'COPA800101', DATE '2023-01-15');
INSERT INTO CLIENTES (NOMBRE, APATERNO, AMATERNO, RFC, FECHA_ALTA) VALUES('Betoo', 'Lopez', 'Rojas', 'LORA900505', DATE '2023-03-20');
COMMIT;
```

#### 🧾 **Insertar en Facturas desde Procedimiento Almacenado**

Un procedimiento almacenado puede realizar el insert automáticamente y controlar otros procesos (como validar clientes o calcular impuestos).

Ejemplo:

```
SELECT 
    CLIENTES.ID_CLIENTE,
    TELEFONOS.ID_TELEFONO,
    CLIENTES.NOMBRE || ' ' || CLIENTES.APATERNO || ' ' || CLIENTES.AMATERNO AS NOMBRE_CLIENTE,
    CLIENTES.RFC,
    TELEFONOS.TELEFONO
FROM CLIENTES
LEFT JOIN TELEFONOS ON CLIENTES.ID_CLIENTE = TELEFONOS.ID_CLIENTE
-- INNER JOIN TELEFONOS ON CLIENTES.ID_CLIENTE = TELEFONOS.ID_CLIENTE
-- WHERE TELEFONOS.ID_TELEFONO IS NOT NULL
ORDER BY CLIENTES.NOMBRE, CLIENTES.APATERNO, CLIENTES.AMATERNO;
```

💳 **Insert de Pagos**

```
VARIABLE v_id_pago NUMBER;
EXECUTE SP_INSERTAR_PAGO(3, 1000.00, DATE '2023-05-15', :v_id_pago);
PRINT v_id_pago;
```

### 🧭 **Conclusión**

Las vistas y vistas materializadas permiten visualizar y optimizar la información de manera estructurada.\
Los database links, equivalencias y sinónimos ayudan a **interconectar** y **simplificar el acceso** entre bases de datos distintas.\
Por último, los inserts —ya sea directos o mediante procedimientos— son esenciales para mantener actualizadas las tablas principales del sistema, garantizando la **integridad y consistencia de los datos**.
