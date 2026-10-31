# ONE-PAGER EJECUTIVO — BRIGHTCART (MODA ONLINE)
**Para:** Carmen (Directora General / CEO) · Diego (Head de Datos) · Nuria (Directora de Marketing) · Dirección de Compras y Operaciones  
**Asunto:** Auditoría forense de rentabilidad real de las Rebajas de Verano 2024, impacto de devoluciones y decisión sobre la reposición del *Vestido Alma*  

---

## 1. Resumen Ejecutivo (En una frase)
La campaña de **Rebajas de Verano 2024 (`campana_id = 1`)** parece un éxito rotundo en los paneles comerciales porque facturó **$572.301,82\text{ €}$ en caja** ($+11,70\%$ frente a los $512.340,00\text{ €}$ del año anterior, sobre $748.731,02\text{ €}$ a precio de catálogo con un $23,56\%$ de descuento medio), impulsada por **Instagram Ads** ($\text{ROAS Bruto } 4,20\times$) y el superventas **Vestido Alma** ($1.016$ unidades y $30.473,90\text{ €}$ brutos); sin embargo, al cruzar con devoluciones y costes operativos se destapa que el **$27,68\%$ de las líneas vendidas regresó al almacén** ($4.718$ de $17.044$ líneas; $5.535$ de $20.008$ prendas), drenando **$-169.918,32\text{ €}$ en reembolsos** ($29,69\%$ de la caja) más **$-30.667,00\text{ €}$ en logística inversa** ($6,50\text{ €/devolución}$) para dejar el **Ingreso Neto Real en $402.383,51\text{ €}$** ($371.716,51\text{ €}$ post-logística), siendo el **Vestido Alma** el epicentro de la sangría con un **$42,66\%$ de devolución** ($92,08\%$ por mal patronaje en las tallas **M** y **L**) y un **margen unitario negativo de $-3,66\text{ €/prenda}$** (perdiendo **$-3.719,34\text{ €}$ netos**), por lo que **debe cancelarse de inmediato la orden de reposición de $2.000$ unidades** (evitando **$31.132,59\text{ €}$** en pérdidas directas).

---

## 2. Los Tres Hallazgos Clave

### Hallazgo 1 — En la superficie Nuria tiene razón: la campaña batió récord de volumen y facturación bruta en caja
Si medimos la campaña únicamente por lo que **salió del almacén** entre el $01/07/2024$ y el $21/07/2024$, todos los indicadores de crecimiento están en verde:
- **Volumen comercial:** **$6.819$ pedidos válidos**, **$17.044$ líneas de venta** y **$20.008$ prendas vendidas** (casi duplicando el ritmo semanal de la Semana Previa base, que fue de $124.817,85\text{ €}$ y $1.179$ pedidos).
- **Facturación cobrada en caja:** **$572.301,82\text{ €}$** reales pagados tras aplicar un descuento promocional medio del $23,56\%$ sobre los $748.731,02\text{ €}$ de valor de catálogo, superando en **$+59.961,82\text{ €}$ ($+11,70\%$)** las ventas de las Rebajas de Verano 2023 ($512.340,00\text{ €}$). *(Nota de descenso esperado del Ticket Medio: pasa de $105,87\text{ €}$ en la semana previa sin descuento a **$83,93\text{ €}$** en rebajas por efecto mecánico del descuento, manteniendo $2,93$ prendas/pedido).*
- **Tracción del producto estrella:** El **Vestido Alma (`producto_id = 1042`)** lideró el ranking con **$1.016$ unidades** ($858$ líneas) y **$30.473,90\text{ €}$** brutos, sacándole un **$+68,77\%$** en unidades al segundo producto (`Top Ola`, $602$ uds).

### Hallazgo 2 — Al cruzar con devoluciones, `Vestidos` y `Calzado` concentran el $60,71\%$ de toda la fuga de dinero
Cuando restamos lo que **volvió al almacén** ($4.718$ devoluciones vinculadas a la campaña tras depurar $42$ registros huérfanos), la rentabilidad por familia de producto cambia radicalmente:
- **Fuga global del $29,69\%$ de los ingresos:** De los $572.301,82\text{ €}$ cobrados, hubo que devolver **$169.918,32\text{ €}$** a los clientes, reduciendo la facturación neta retenida a **$402.383,51\text{ €}$** ($-21,46\%$ por debajo del benchmark de $512.340,00\text{ €}$ del año anterior).
- **Dos categorías explican más de $103.000\text{ €}$ en reembolsos:**
  - **`Vestidos`** (#1 en ventas con $154.292,26\text{ €}$) sufre la **mayor tasa de devolución de la compañía ($35,68\%$)**, perdiendo **$-54.542,01\text{ €}$** en reembolsos ($32,10\%$ del total devuelto) más **$-9.633,00\text{ €}$** en logística inversa.
  - **`Calzado`** (#2 en ventas con $141.720,87\text{ €}$) registra un **$34,08\%$ de devolución**, perdiendo **$-48.619,03\text{ €}$** en reembolsos ($28,61\%$ del total devuelto) más **$-5.908,50\text{ €}$** en logística inversa.
  - En contraste, **`Accesorios` ($12,65\%$ dev.)** y **`Camisetas` ($19,75\%$ dev.)** retienen el $87,35\%$ y el $80,25\%$ de sus ingresos brutos.

### Hallazgo 3 — La ilusión del ROAS Bruto en Marketing y la paradoja de conversión entre canales
- **Instagram Ads pierde $-1,19$ puntos de ROAS tras las devoluciones:** Con una inversión publicitaria de **$48.000,00\text{ €}$**, `instagram` reportó **$201.623,15\text{ €}$ brutos ($\text{ROAS Bruto } 4,20\times$)**, pero sufrió **$-57.235,51\text{ €}$ en devoluciones ($26,49\%$)** y **$-10.393,50\text{ €}$ en logística inversa**, reduciendo el ingreso neto real a **$144.387,64\text{ €}$ ($\text{ROAS Neto } 3,01\times$)**.
- **Tráfico vs. Conversión (`Email` convierte $2,65\times$ mejor que `Instagram`):** Mientras `instagram` necesitó **$57.624$ sesiones web** para lograr $2.400$ pedidos (**$4,16\%$ de conversión**), el canal **`email`** convirtió el **$11,03\%$ de sus sesiones** ($1.361$ pedidos sobre $12.337$ visitas) con coste publicitario cero, superando en ingresos netos (**$80.398,43\text{ €}$**) al canal **`directo`** (**$79.780,95\text{ €}$**, conversión del $7,86\%$).

---

## 3. Tablas Maestras de la Campaña Rebajas de Verano 2024 (`campana_id = 1`)

### 3A. Tabla Maestra por Categoría (Normalizada en 8 Familias Canónicas)

| Categoría | Líneas Vend. | Unidades Vend. | Líneas Dev. | Tasa Dev. (%) | Facturación Bruta (€) | Cuota Bruta | Reembolsos (€) | Facturación Neta (€) | Cuota Neta | Logística Inversa ($6,50\text{ €}$) | Caja Neta Post-Logística (€) |
| :--- | ---: | ---: | ---: | ---: | ---: | ---: | ---: | ---: | ---: | ---: | ---: |
| **Vestidos** | 4.154 | 4.870 | 1.482 | **35,68%** | **154.292,26 €** | **26,96%** | **-54.542,01 €** | **99.750,25 €** | 24,79% | -9.633,00 € | 90.117,25 € |
| **Calzado** | 2.667 | 3.134 | 909 | **34,08%** | **141.720,87 €** | **24,76%** | **-48.619,03 €** | **93.101,84 €** | 23,14% | -5.908,50 € | 87.193,34 € |
| **Pantalones** | 1.674 | 1.965 | 511 | 30,53% | 54.457,69 € | 9,52% | -16.455,00 € | 38.002,69 € | 9,44% | -3.321,50 € | 34.681,19 € |
| **Abrigos** | 833 | 1.000 | 220 | 26,41% | 49.503,03 € | 8,65% | -12.705,20 € | 36.797,82 € | 9,15% | -1.430,00 € | 35.367,82 € |
| **Camisetas** | 2.831 | 3.330 | 559 | **19,75%** | 44.698,04 € | 7,81% | -8.821,85 € | 35.876,19 € | 8,92% | -3.633,50 € | 32.242,69 € |
| **Jerséis** | 1.374 | 1.603 | 304 | 22,13% | 44.342,38 € | 7,75% | -10.041,88 € | 34.300,50 € | 8,52% | -1.976,00 € | 32.324,50 € |
| **Faldas** | 1.463 | 1.701 | 474 | 32,40% | 41.849,37 € | 7,31% | -13.493,44 € | 28.355,93 € | 7,05% | -3.081,00 € | 25.274,93 € |
| **Accesorios** | 2.048 | 2.405 | 259 | **12,65%** | 41.438,19 € | 7,24% | -5.239,90 € | 36.198,28 € | 9,00% | -1.683,50 € | 34.514,78 € |
| **TOTAL CAMPAÑA** | **17.044** | **20.008** | **4.718** | **27,68%** | **572.301,82 €** | **100,00%** | **-169.918,32 €** | **402.383,51 €** | **100,00%** | **-30.667,00 €** | **371.716,51 €** |

### 3B. Tabla Maestra por Canal de Captación (Tráfico, Conversión y Rentabilidad Neta)

| Canal | Sesiones Web | Pedidos | Conversión (%) | Líneas Vend. | Unidades | Líneas Dev. | Tasa Dev. (%) | Facturación Bruta (€) | Reembolsos (€) | Facturación Neta (€) | Ticket Medio Bruto / Neto (€) | Logística Inversa (€) |
| :--- | ---: | ---: | ---: | ---: | ---: | ---: | ---: | ---: | ---: | ---: | ---: | ---: |
| **instagram** | 57.624 | 2.400 | **4,16%** | 6.037 | 7.096 | 1.599 | 26,49% | **201.623,15 €** | -57.235,51 € | **144.387,64 €** | 84,01 € / 60,16 € | -10.393,50 € |
| **google** | 34.923 | 1.714 | 4,91% | 4.277 | 5.001 | 1.250 | **29,23%** | 142.900,62 € | -45.084,13 € | 97.816,49 € | 83,37 € / 57,07 € | -8.125,00 € |
| **email** | 12.337 | 1.361 | **11,03%** | 3.380 | 3.962 | 932 | 27,57% | 113.265,66 € | -32.867,23 € | **80.398,43 €** | 83,22 € / 59,07 € | -6.058,00 € |
| **directo** | 17.096 | 1.344 | 7,86% | 3.350 | 3.949 | 937 | 27,97% | 114.512,39 € | -34.731,44 € | 79.780,95 € | **85,20 €** / 59,36 € | -6.090,50 € |
| **TOTAL** | **121.980** | **6.819** | **5,59%** | **17.044** | **20.008** | **4.718** | **27,68%** | **572.301,82 €** | **-169.918,32 €** | **402.383,51 €** | **83,93 € / 59,01 €** | **-30.667,00 €** |

---

## 4. Blindaje del Hallazgo: Radiografía Forense del «Vestido Alma» y Unit Economics

1. **Diagnóstico por Talla — El fallo de patronaje está concentrado en las tallas `M` y `L` ($86,34\%$ de las devoluciones):**
   El `Vestido Alma` (`858` líneas / `1.016` unidades vendidas, `366` líneas / `433` unidades devueltas, **$42,66\%$ de tasa de devolución**) no falla por igual en todas las tallas:
   - **Talla `L`:** $249$ líneas vendidas ($294$ uds) $\rightarrow$ **$149$ devueltas ($59,84\%$ de tasa de devolución)**.
   - **Talla `M`:** $310$ líneas vendidas ($369$ uds) $\rightarrow$ **$167$ devueltas ($53,87\%$ de tasa de devolución)**.
   - **Talla `XL`:** $130$ líneas vendidas ($159$ uds) $\rightarrow$ $28$ devueltas ($21,54\%$).
   - **Talla `S`:** $134$ líneas vendidas ($153$ uds) $\rightarrow$ $18$ devueltas (**$13,43\%$**).
   - **Talla `XS`:** $35$ líneas vendidas ($41$ uds) $\rightarrow$ $4$ devueltas (**$11,43\%$**).
   *Conclusión técnica:* Las tallas **`M` y `L` suman $316$ de las $366$ devoluciones ($86,34\%$)** porque el escalado industrial del proveedor talló `M` y `L` más pequeñas de lo habitual.
2. **Diagnóstico por Motivo — El $92,08\%$ de las clientas devuelve el vestido por tallaje/ajuste, no por diseño ni defecto:**
   De las $366$ devoluciones del `Vestido Alma`, **`337` casos ($92,08\%$)** corresponden a problemas de talla: `talla incorrecta` ($220$, $60,11\%$), `no me queda bien` ($72$, $19,67\%$), `Talla` ($27$, $7,38\%$) y `me queda pequeño` ($18$, $4,92\%$). Solo un $7,92\%$ suma `no me gusta` ($14$), `defecto` ($8$), `cambié de opinión` ($4$) y `color distinto` ($3$).
3. **Ecuación de Unit Economics y Coste Oculto de Logística Inversa (Break-Even en $29,58\%$):**
   - A un PVP efectivo de **$29,99\text{ €}$**, descontando fabricación ($\text{COGS } 10,50\text{ €}$), envío de ida ($4,00\text{ €}$), pasarela TPV ($0,45\text{ €}$) y CAC en Instagram ($6,76\text{ €}$), **cada vestido retenido deja $+8,28\text{ €}$**.
   - Pero **cada vestido devuelto hace perder $-19,71\text{ €}$** ($4,00\text{ €}$ envío ida $+ 6,50\text{ €}$ logística inversa $+ 0,45\text{ €}$ TPV $+ 6,76\text{ €}$ CAC $+ 2,00\text{ €}$ reacondicionamiento).
   - El **punto de equilibrio (Break-Even)** se sitúa en el **$29,58\%$ de devolución**. Con su **$42,66\%$ real**, el `Vestido Alma` **destruye $-3,66\text{ €}$ por cada unidad vendida**, acumulando **$-3.719,34\text{ €}$ de pérdida neta** en sus $1.016$ unidades.

---

## 5. Recomendación Accionable para el Comité (Impacto Cuantificado: $+51.637,16\text{ €}$)

1. **Bloquear de inmediato la orden de compra de $2.000$ unidades del `Vestido Alma` (Impacto: $+31.132,59\text{ €}$ ahorrados):**
   - Cancelar la reposición a fábrica hasta que el proveedor corrija el patrón de las tallas `M` y `L`. Esta sola decisión evita **$853$ devoluciones futuras** ($25.585,87\text{ €}$ en reembolsos y $5.546,72\text{ €}$ en logística inversa). En el stock actual web, añadir aviso destacado: *«Este modelo talla pequeño en tallas M y L; recomendamos pedir una talla más»*.
2. **Activar el Protocolo Anti «Devoluciones Ping-Pong» en almacén (WMS) para las $366$ unidades devueltas (Impacto: $+5.703,92\text{ €}$):**
   - Bloquear la reentrada automática al stock online de las $366$ prendas devueltas del `Vestido Alma`; desviarlas a tiendas físicas con probador o reetiquetarlas con su talla real equivalente (`L` $\rightarrow$ `M`, `M` $\rightarrow$ `S`), evitando **$156$ segundas devoluciones reincidentes**.
3. **Integrar un Recomendador Interactivo de Tallas en `Vestidos` y `Calzado` (Impacto: $+14.800,66\text{ €}$ por campaña):**
   - Desplegar asistente de tallaje en las dos familias que concentran $296.013,13\text{ €}$ brutos y $103.161,04\text{ €}$ en reembolsos; reducir en 5 puntos porcentuales su tasa de retorno rescata **$+14.800,66\text{ €}$ netos por campaña**.
4. **Cambiar el KPI rector de Marketing y Logística:**
   - Reconfigurar la optimización de **Instagram Ads** hacia **ROAS Neto post-devolución** y sustituir en los cuadros de mando de Dirección la *Facturación Bruta* por **Facturación Neta Retenida y Margen Unitario Post-Logística Inversa**, incentivando además la devolución en tienda física (bajando el coste unitario de $6,50\text{ €}$ a $\sim 2,00\text{ €}$).

---

## 6. Gráficos de Soporte en `reports/`
- [`01_facturacion_bruta_vs_reembolsos.png`](01_facturacion_bruta_vs_reembolsos.png) — *El Mapa de la Fuga: Facturación Neta Retenida vs. Dinero Reembolsado por Categoría (`Vestidos` y `Calzado` = 60,7% de la sangría).*
- [`02_radiografia_vestido_alma.png`](02_radiografia_vestido_alma.png) — *La Radiografía Forense del Vestido Alma: 42,7% de devoluciones y 92,1% de causas por tallaje/ajuste.*
- [`03_roas_bruto_vs_neto_canales.png`](03_roas_bruto_vs_neto_canales.png) — *La Ilusión del ROAS en Marketing: Facturación Bruta vs. Neta por Canal y caída del ROAS de Instagram de 4,20x a 3,01x.*
- [`04_unit_economics_logistica_inversa.png`](04_unit_economics_logistica_inversa.png) — *El Blindaje Financiero: Curva de Unit Economics, Break-Even en 29,6% y pérdida neta de -3,66 €/prenda en el Vestido Alma.*
