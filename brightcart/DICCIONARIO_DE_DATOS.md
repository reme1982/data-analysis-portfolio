# 📖 BrightCart — Diccionario de Datos y Diagnóstico de Calidad (Día 1)

**Autor:** Analista de Datos  
**Mentor:** Diego (Head de Datos)  
**Stakeholders:** Nuria (Marketing), Álex Peña (Data Team)  
**Fecha:** 2024-07-22 (Cierre de Campaña Rebajas Verano)

---

## 1. Arquitectura y Granularidad del Almacén

| Fichero | Rol en el Modelo | Clave Primaria (PK) | Granularidad (¿Qué representa cada fila?) | Filas Totales | Entidades Únicas | Estado de Calidad |
| :--- | :--- | :--- | :--- | :---: | :---: | :---: |
| **`lineas_pedido.csv`** | **HECHOS** (Núcleo) | `linea_id` | 1 prenda concreta vendida dentro de un pedido | 20.140 | 20.000 | ⚠️ 140 duplicados, precios con "€" y descuentos mixtos |
| **`pedidos.csv`** | CONTEXTO | `pedido_id` | 1 ticket de compra global realizado por un cliente | 8.000 | 8.000 | ⚠️ Fechas en formatos mixtos |
| **`productos.csv`** | CONTEXTO | `producto_id` | 1 referencia del catálogo de moda | 400 | 400 | ⚠️ 12 costes nulos |
| **`clientes.csv`** | CONTEXTO | `cliente_id` | 1 cliente registrado en la tienda online | 5.010 | 4.970 | ⚠️ 40 duplicados, 150 fechas nulas, mayúsculas |
| **`campana.csv`** | CONTEXTO | `campana_id` | 1 campaña de marketing/promoción | 4 | 4 | ⚠️ Fila 2 con formato de texto `"61.000 €"` |
| **`devoluciones.csv`** | CONTEXTO / EVENTOS | `devolucion_id` | 1 prenda devuelta por un cliente | 5.558 | 5.558 | ⚠️ 42 devoluciones huérfanas, tallas desalineadas |
| **`visitas_web.csv`** | CONTEXTO / TRÁFICO | Compuesta (`fecha`, `canal`) | Tráfico diario agregado por canal | 112 | 112 combinaciones | ⚠️ 4 valores nulos en sesiones |

---

## 2. Detalle de Campos por Tabla y Suciedades Detectadas

### 2.1. `lineas_pedido.csv` (Tabla de Hechos)
*La tabla transaccional donde se registran los ingresos reales y las unidades vendidas.*
- **`linea_id`** (`int64`): Identificador único de la línea. *Anomalía:* Hay 140 filas repetidas exactamente por fallo del exportador SQL.
- **`pedido_id`** (`int64`): Clave foránea que apunta a `pedidos.csv`. Hay exactamente 8.000 pedidos vinculados (promedio de 2.51 prendas/ticket).
- **`producto_id`** (`int64`): Clave foránea que apunta a `productos.csv`.
- **`talla`** (`str / object`): Talla de la prenda vendida. Vienen en formatos variados (`36`, `38`, `S`, `M`, `L`, `XL`, etc.).
- **`cantidad`** (`int64`): Unidades adquiridas en esa línea.
- **`precio_unitario`** (`str / object` ⚠️): Precio de catálogo por unidad. **Suciedad:** Viene como texto con símbolo de moneda y coma decimal (`"63,83 €"`). *Requiere limpieza a float antes de cualquier cálculo.*
- **`descuento_pct`** (`str / object` ⚠️): Descuento comercial aplicado. **Suciedad:** Formatos heterogéneos (`0`, `0.3`, `"20%"`). *Requiere estandarización a float decimal (0.0 a 1.0).*

---

### 2.2. `pedidos.csv` (Dimensión Pedidos)
- **`pedido_id`** (`int64`): Clave primaria única (8.000 pedidos).
- **`cliente_id`** (`int64`): Clave foránea a `clientes.csv`. Hay 2.287 clientes compradores distintos.
- **`fecha_pedido`** (`str / object` ⚠️): Fecha de la compra. **Suciedad:** Formatos mixtos (`"24/06/2024"` vs `"2024-07-02"`). *Requiere conversión a `datetime` unificado.*
- **`campana_id`** (`float64` ⚠️): Identificador de la campaña si el pedido provino de una promo. **Suciedad:** Trae 1.179 nulos (compras orgánicas) y por eso Pandas lo convirtió a float (`1.0` en vez de `1`).
- **`canal`** (`str`): Canal de captación (`directo`, `instagram`, `email`, etc.).
- **`ciudad`** (`str` ⚠️): Ciudad de envío. Inconsistencias de mayúsculas/minúsculas (`"lisboa"` vs `"Lisboa"`).
- **`metodo_pago`** (`str`): `tarjeta`, `bizum`, `paypal`.

---

### 2.3. `productos.csv` (Dimensión Catálogo)
- **`producto_id`** (`int64`): Clave primaria (400 artículos únicos).
- **`nombre`** (`str`): Nombre comercial de la prenda (ej. *"Vestido Aura"*).
- **`categoria`** (`str`): Categoría del producto (35 categorías distintas).
- **`temporada`** (`str`): Colección temporal.
- **`coleccion`** (`str`): Línea de diseño.
- **`coste_unitario`** (`float64` ⚠️): Coste de fabricación/adquisición. **Suciedad:** **12 valores nulos**. *Riesgo:* Deja sin cálculo el margen neto de esas 12 referencias.
- **`precio_base`** (`float64`): Precio de venta sugerido en catálogo.

---

### 2.4. `clientes.csv` (Dimensión Clientes)
- **`cliente_id`** (`int64`): Identificador del cliente. **Suciedad:** 5.010 filas para solo 4.970 clientes (40 clientes duplicados con variaciones de texto).
- **`fecha_registro`** (`str / object` ⚠️): **150 valores nulos**.
- **`ciudad`** (`str` ⚠️): Variaciones como `"bilbao"` y `"Bilbao"`, `"madrid"` y `"Madrid"`.
- **`genero`** (`str` ⚠️): Variaciones de mayúsculas y minúsculas (`"F"`, `"M"`, `"m"`).
- **`edad`** (`int64`): Rango de edad de los clientes.

---

### 2.5. `campana.csv` (Dimensión Campañas)
- **`campana_id`** (`int64`): Clave primaria (4 campañas registradas).
- **`nombre`** (`str`): Nombre comercial. La campaña bajo análisis es la **ID 1: "Rebajas Verano 2024"**.
- **`tipo`** (`str`): `rebajas`, `black_friday`, `promo`.
- **`fecha_inicio`** y **`fecha_fin`** (`str`): Rango de fechas (Rebajas Verano: `2024-07-01` al `2024-07-21`).
- **`canal`** (`str`): Canal principal asignado.
- **`presupuesto`** (`str / object` ⚠️): Presupuesto publicitario. **Suciedad:** Campaña 3 trae `"61.000 €"` como string mientras las demás vienen como float (`48000.0`).
- **`ventas_ano_anterior`** (`float64`): Cifra histórica de referencia (Rebajas Verano año anterior: **512.340,0 €**).

---

### 2.6. `devoluciones.csv` (Eventos de Retorno)
- **`devolucion_id`** (`int64`): Clave primaria (5.558 filas únicas).
- **`linea_id`** (`int64` ⚠️): Clave foránea a `lineas_pedido`. **Fuga de integridad:** **42 devoluciones huérfanas** que apuntan a IDs de línea que no existen en ventas.
- **`fecha_devolucion`** (`str` ⚠️): Fechas con formatos mixtos (`15/07/2024` vs `2024-07-16`).
- **`talla`** (`str` ⚠️): Tallas heterogéneas (`36`, `XL`, `m`, `s`).
- **`motivo`** (`str`): Motivos de retorno (`talla incorrecta`, `no me gusta`, etc.).

---

### 2.7. `visitas_web.csv` (Métricas de Tráfico)
- **`fecha`** (`str`): Día del registro de tráfico.
- **`canal`** (`str`): Origen del tráfico.
- **`sesiones`** (`float64` ⚠️): Número de sesiones. **Suciedad:** **4 valores nulos (`NaN`)**.

---

## 3. Plan de Acción para el Día 2 (Checklist de Limpieza)

Para que los cálculos de negocio sean defendibles ante Diego y Nuria, el **Día 2** aplicará este orden estricto de transformaciones:

1. [ ] **Depurar duplicados:** Eliminar las 140 filas repetidas en `lineas_pedido` y consolidar los 40 clientes en `clientes`.
2. [ ] **Conversión monetaria:** Quitar símbolos de euro `"€"`, espacios y comas decimales en `precio_unitario` y `presupuesto`, convirtiéndolos a `float`.
3. [ ] **Normalización de descuentos:** Convertir `"20%"` a `0.20`, conservar decimales y dejar `descuento_pct` en escala 0.0 - 1.0 numérica.
4. [ ] **Unificación de fechas:** Parsear todas las columnas de fecha a formato estándar ISO `YYYY-MM-DD` con `pd.to_datetime`.
5. [ ] **Aislar devoluciones huérfanas:** Filtrar las 42 devoluciones inválidas para no descontar dinero ni prendas inexistentes.
6. [ ] **Estandarizar texto:** Convertir ciudades, géneros y tallas a un formato canónico (ej. `str.strip().str.upper()`).
7. [ ] **Imputación de costes nulos:** Definir estrategia para los 12 productos sin coste antes de calcular el margen.
