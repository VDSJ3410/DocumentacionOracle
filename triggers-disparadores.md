---
description: >-
  Los triggers son bloques de código que se ejecutan automáticamente cuando
  ocurre un evento en una tabla (por ejemplo, un INSERT o UPDATE).
---

# Triggers (Disparadores)

Se utilizan para **auditorías, validaciones o sincronizaciones automáticas**.

#### Tipos principales

* **BEFORE** → se ejecuta antes del evento.
* **AFTER** → se ejecuta después del evento.
* **FOR EACH ROW** → actúa fila por fila.

#### 🔹 Ventajas

* Garantizan integridad y consistencia en los datos.
* Permiten crear auditorías automáticas.
* Eliminan la necesidad de procesos manuales para registrar cambios.

#### 🔹 Ejemplo trabajado: `TRG_CLIENTES_AIU`

Este trigger se ejecuta **después de una inserción o actualización** en la tabla `CLIENTES`.\
Su función es **registrar los cambios en la tabla de bitácora (`CLIENTES_BIT`)**, incluyendo acción realizada, fechas y la IP del usuario.

```
CREATE OR REPLACE TRIGGER TRG_CLIENTES_AIU
AFTER INSERT OR UPDATE ON CLIENTES FOR EACH ROW
```

Dentro del trigger se guarda:

* La acción realizada (INSERT o UPDATE).
* La fecha del cambio.
* La IP del usuario que realizó la operación.

Gracias a este trigger, se mantiene un historial completo de las modificaciones hechas a los registros.
