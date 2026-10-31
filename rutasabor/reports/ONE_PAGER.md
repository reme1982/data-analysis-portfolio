# ONE-PAGER EJECUTIVO: DECISIÓN DE EXPANSIÓN Y RENTABILIDAD
**Destinatarios:** Clara Montero (CEO), Gonzalo Prats (Director de Expansión), Bea Solís (Head de Operaciones)  
**Preparado por:** Equipo de Analítica de Datos (RutaSabor)  
**Fecha:** 15 de Octubre de 2026  
**Veredicto de Inversión:** **DESESTIMAR la clonación de La Brasa Burger y ESCALAR Poke Break en las 3 nuevas cocinas**.

---

### 1. Dale la razón en la superficie (Gonzalo tiene razón en lo que ve)
A primera vista y según los cuadros de mando oficiales (Metabase), **La Brasa Burger es la número uno indiscutible de la empresa**:
* **Volumen:** Concentra **50.978 pedidos** ($33,99\%$ de toda la compañía).
* **Facturación Bruta (GMV):** Genera **587.218 €** ($33,85\%$ de las ventas totales).
* Duplica holgadamente en volumen y ventas a la segunda marca del catálogo.

> Gonzalo no se equivoca en las cifras de superficie: La Brasa es la reina de las pantallas.

---

### 2. Por qué esa foto engaña: La trampa del delivery y los costes ocultos
Cuando a cada pedido de La Brasa se le descuentan los tres costes variables que ningún panel muestra juntos (ingredientes, comisión de marketplace e incidencias), la rentabilidad se desmorona:

* **De los 11,52 € que paga el cliente por pedido:**
  * **-7,06 €** se van en coste de materia prima e ingredientes.
  * **-3,26 €** se los queda el marketplace (comisión media del $28,3\%$, dominada por Glovo al $30\%$).
  * **-0,60 €** se pierden en compensaciones y reembolsos por incidencias.
* **Quedan en caja únicamente 0,60 € de Margen de Contribución por pedido** (el peor de todo el portafolio).

```text
CASCADA UNITARIA DE LA BRASA BURGER:
[ 11,52 € Importe ] ──▶ [ -7,06 € Ingred. ] ──▶ [ -3,26 € Comisión ] ──▶ [ -0,60 € Incid. ] ──▶ [ = 0,60 € MARGEN ]
```

**Las 3 razones que viajan juntas y hunden a La Brasa:**
1. **Ticket Bajo:** $11,52$ € (un punto de partida con escaso margen absoluto).
2. **Canal Caro:** El **$68,1\%$ de sus pedidos entra por Glovo** ($30\%$ de comisión), con apenas un **$3,9\%$ en la App propia**.
3. **Alta Tasa de Fallo:** Un **$12,24\%$ de tasa de incidencias** (casi 1 de cada 8 hamburguesas llega fría, tarde o incompleta).

---

### 3. El Hallazgo en Números: El Espejismo del GMV vs la Cuota de Contribución

| Marca | Ticket Medio | Margen Contribución / Pedido | Cuota GMV (% Facturación) | Cuota Contribución Real (% Margen Caja) | Diagnóstico |
| :--- | :---: | :---: | :---: | :---: | :--- |
| **Poke Break** | **15,83 €** | **3,56 €** | **19,2%** | **27,9%** | **La que sostiene el negocio** |
| **Pizza Nostra** | 13,61 € | 2,66 € | 20,0% | 25,2% | Sólida y equilibrada |
| **Wok Express** | 11,48 € | 2,12 € | 16,9% | 20,2% | Rentable y estable |
| **Dulce Antojo** | 6,51 € | 1,39 € | 10,2% | 14,1% | Ticket bajo pero eficiente |
| **La Brasa Burger** | **11,52 €** | **0,60 €** | **33,9%** | **12,6%** | **Mueve cajas, no genera caja** |

* **La Brasa Burger** factura el **$33,9\%$** de la empresa pero solo aporta el **$12,6\%$** del margen real.
* **Poke Break**, con un volumen mucho más modesto ($14,0\%$ de pedidos y $19,2\%$ de GMV), aporta el **$27,9\%$** de todo el margen de RutaSabor.
* **Conclusión contundente:** Clonar La Brasa es multiplicar volumen sin margen: saturar las cocinas con pedidos que apenas cubren sus costes variables.

---

### 4. El Blindaje (Control de Robustez): No es la cocina, es la marca
Para descartar la hipótesis operativa planteada por Bea Solís (*"¿Y si La Brasa sale mal por culpa de la cocina de Vallecas?"*), se analizó el margen de contribución dentro de cada una de las 10 cocinas:

* **Vallecas** rinde ligeramente por debajo de Chamberí en todas las marcas (el nivel general varía $\approx 0,17$ €).
* **Sin embargo, la brecha entre Poke Break y La Brasa es prácticamente constante en las 10 cocinas (entre 2,70 € y 3,04 € por pedido).**
* En Chamberí (la mejor cocina), La Brasa deja **0,74 €** y Poke **3,69 €** ($\Delta = 2,95$ €).
* En Vallecas (la cocina sospechosa), La Brasa deja **0,57 €** y Poke **3,50 €** ($\Delta = 2,93$ €).

> **Veredicto técnico:** La cocina mueve ligeramente el nivel; la marca define la brecha. El problema es estructural del modelo de La Brasa, no operativo de Vallecas.

---

### 5. Recomendación Ejecutiva en Tres Movimientos

1. **NO clonar La Brasa Burger en las 3 nuevas cocinas:**
   * Abrir 3 cocinas con La Brasa costará cientos de miles de euros en capex, equipamiento y personal para multiplicar pedidos que dejan 60 céntimos.
2. **SÍ escalar Poke Break:**
   * Es la marca más rentable de la compañía ($3,56$ €/pedido), con la menor tasa de incidencias ($3,23\%$) y la mayor independencia del marketplace ($42,2\%$ de ventas por la App propia).
3. **Empujar la App Propia y sanear la economía de La Brasa antes de tocarla:**
   * Trasvasar ventas de Glovo ($30\%$) a la App propia ($6\%$).
   * Rediseñar la carta de La Brasa: subir combos para elevar el ticket medio ($>13,50$ €) y reformular el packaging térmico para reducir a la mitad su tasa de incidencias.

---
*Documentación técnica, consultas SQL reproducibles y cuadernos asociados: `dia_01.ipynb` a `dia_05.ipynb`.*
