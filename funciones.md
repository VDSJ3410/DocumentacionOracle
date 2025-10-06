---
description: >-
  Las funciones permiten encapsular código que retorna un valor, facilitando la
  reutilización y la organización de la lógica en la base de datos.
---

# Funciones

#### 🔹 Funciones vistas en clase

**a) `FN_GET_IP`**\
Obtiene la dirección IP o el nombre del host desde donde se ejecuta la acción.\
Si no puede obtenerlo, devuelve “LOCALHOST”.

```
CREATE OR REPLACE FUNCTION FN_GET_IP RETURN VARCHAR2
```

**b) `FN_OBTENER_FOLIO_FACTURA`**\
Devuelve el **folio correspondiente a una factura**, tomando como base el año de la fecha de emisión.\
Antes de generar el número, **llama al procedimiento `SP_CREAR_SEQ_FOLIO_ANIO`** para asegurarse de que la secuencia del año exista.

```
CREATE OR REPLACE FUNCTION FN_OBTENER_FOLIO_FACTURA(p_fecha_factura IN DATE)
```

Estas funciones permiten automatizar procesos, reducir errores y centralizar la lógica de negocio.

#### Ventajas

* Reutilización del código en distintas partes del sistema.
* Mayor legibilidad y mantenimiento del código.
* Permiten encapsular reglas de negocio directamente en la base de datos.
