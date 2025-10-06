---
description: >-
  Las secuencias son objetos de base de datos que generan valores numéricos
  consecutivos, generalmente usados para llaves primarias, folios o numeraciones
  automáticas.
---

# Secuencias

Se pueden configurar con parámetros como:

* `START WITH` → valor inicial.
* `INCREMENT BY` → cantidad que aumenta en cada llamada.
* `NOCACHE` → evita almacenar valores en memoria.
* `NOCYCLE` → impide que la secuencia reinicie automáticamente.

#### 🔹 Ventajas

* Generan identificadores únicos sin riesgo de repetición.
* Aumentan la eficiencia al automatizar la numeración.

Evitan la duplicación de valores y garantizan la integridad en registros nuevos.

#### 🔹 Ejemplos vistos

Se crearon distintas secuencias para las tablas principales y sus bitácoras:

```
CREATE SEQUENCE SEC_ID_CLIENTE START WITH 1 INCREMENT BY 1 NOCACHE NOCYCLE;
CREATE SEQUENCE SEC_ID_CLIENTE_BIT START WITH 1 INCREMENT BY 1 NOCACHE NOCYCLE;
```

También se creó un **procedimiento almacenado** que genera automáticamente secuencias por año:

```
CREATE OR REPLACE PROCEDURE SP_CREAR_SEQ_FOLIO_ANIO(p_anio IN NUMBER)
```

Este procedimiento **verifica si la secuencia del año ya existe** y, si no, la crea de forma dinámica (`SEC_FOLIO_2025`, `SEC_FOLIO_2026`, etc.).\
Así se mantiene un control anual de los folios de facturación.
