# ONE-PAGER EJECUTIVO — NIDOHOGAR (PORTAL INMOBILIARIO)
**Para:** Álvaro Nadal (CEO) · Irene Salas (Lead de Datos) · Gonzalo Prieto (Director Comercial) · Cristina Márquez (Product Manager del Marketplace)  
**Asunto:** Auditoría del embudo «del clic al contrato», evaluación del lanzamiento de «Destacado Premium» y recomendación para el Comité de Dirección  

---

## 1. Resumen Ejecutivo (En una frase)
Los anuncios **destacados** parecen el producto estrella en los cuadros de mando de Comercial porque, con el **$31,68\%$ del catálogo** ($1.489$ de $4.700$ pisos), **casi duplican las visitas por inmueble ($17,82$ vs $8,95$, $\times 1,99$) y los contactos recibidos ($5,79$ vs $3,05$, $\times 1,90$)**, pero al inundar de mensajes a agencias sin capacidad de atención provocan que el **$50,00\%$ de sus contactos queden sin respuesta ($4.305$ de $8.610$ leads ignorados)** frente al **$33,00\%$ en anuncios normales ($3.059$ de $9.270$)**, hundiendo su **tasa de conversión a contrato un $-37,6\%$ ($4,98\%$ vs $7,98\%$)** y su aportación a caja (**$537.419,74\text{ €}$ en comisiones [$40,06\%$]** frente a **$804.176,79\text{ €}$ [$59,94\%$]** de los normales); dado que **responder en menos de $2$ horas multiplica por $28$ la probabilidad de firma ($14,00\%$ vs $0,50\%$)** y que **dentro del mismo tramo `<2h` destacado y normal convierten exactamente igual ($13,99\%$ vs $14,01\%$)**, lanzar *«Destacado Premium»* sin corregir antes el cuello de botella comercial solo multiplicaría los leads ignorados en lugar de los contratos (**dejando sobre la mesa $+258$ contratos y $+337.358\text{ €}$ anuales en comisiones**).

---

## 2. Los Tres Hallazgos Clave

### Hallazgo 1 — Gonzalo tiene razón en la superficie: el Destacado gana arriba del embudo en tráfico y contactos
Si medimos el producto por lo que **entra** en las dos primeras etapas del embudo (*visita $\rightarrow$ contacto*), `destacado` cumple exactamente su promesa de visibilidad sobre la base limpia auditada ($4.700$ anuncios, $55.275$ visitas únicas tras eliminar $386$ duplicados y $17.880$ contactos únicos tras eliminar $125$ duplicados):
- **Doble de tráfico por inmueble:** cada anuncio `destacado` promedia **$17,82$ visitas** ($26.533$ visitas totales en $1.489$ anuncios) frente a **$8,95$ visitas** de un anuncio `normal` ($28.742$ visitas en $3.211$ anuncios), un multiplicador de **$\times 1,99$**.
- **Doble de contactos por inmueble:** cada anuncio `destacado` capta **$5,79$ contactos** de media ($8.610$ contactos totales, el **$48,15\%$** de todos los leads del portal) frente a **$3,05$ contactos** en `normal` ($9.270$ contactos, **$51,85\%$**), un multiplicador de **$\times 1,90$**.
- **Misma atracción de visita a contacto:** la tasa de paso de visita a contacto es idéntica en ambos tipos (**$32,45\%$** en `destacado` vs **$32,25\%$** en `normal`, media global del **$32,35\%$**).

### Hallazgo 2 — Al cruzar con contratos y tiempos de respuesta, el ranking se invierte por Saturación Comercial
Cuando medimos lo que **se firma** al fondo del embudo ($1.169$ contratos cerrados, tasa reina global del **$6,54\%$** de contacto a contrato usando `LEFT JOIN`; *nota técnica: un `INNER JOIN` amputaría los $16.711$ contactos no firmados falseando un $100\%$ de conversión*), la ventaja del destacado se desploma por un único mecanismo operativo:
- **La Grieta ($4,98\%$ vs $7,98\%$):** los anuncios `destacados` convierten a contrato solo el **$4,98\%$** de sus contactos ($429$ contratos sobre $8.610$ leads), mientras que los `normales` convierten al **$7,98\%$** ($740$ contratos sobre $9.270$ leads): **$-3,00\text{ pp}$ menos ($-37,6\%$ de caída relativa)**. También caen en conversión de visita a contrato (**$1,62\%$** vs **$2,57\%$**).
- **La Palanca Reina es la velocidad de respuesta ($\times 28$):** en el conjunto de NidoHogar, el **$41,19\%$ de todos los contactos ($7.364$ mensajes) nunca recibe respuesta**. Al segmentar por el tiempo que tarda la agencia en contestar (`fecha_respuesta - fecha_contacto`):
  - **`<2h` ($6.600$ contactos, $36,91\%$):** convierte al **$14,00\%$** ($924$ contratos, el **$79,04\%$ de todas las firmas** y el **$81,62\%$ de las comisiones: $1.095.060,54\text{ €}$**).
  - **`2-24h` ($2.434$ contactos, $13,61\%$):** la conversión cae a la mitad (**$6,98\%$**, $170$ contratos, $168.970,66\text{ €}$).
  - **`>24h` ($1.482$ contactos, $8,29\%$):** la conversión se desploma al **$2,56\%$** ($38$ contratos, $41.066,76\text{ €}$).
  - **`sin_respuesta` ($7.364$ contactos, $41,19\%$):** apenas cierra un **$0,50\%$** residual ($37$ contratos, $36.498,57\text{ €}$).
- **El Mecanismo (Saturación del Buzón de la Agencia):** el anuncio `destacado` mete casi el doble de leads en agencias que no dan abasto, provocando que el **$50,00\%$ de los contactos en destacados ($4.305$ leads) se queden sin respuesta** (frente al **$33,00\%$ [$3.059$]** en normales) y que solo el **$24,00\%$ ($2.066$)** sea atendido en **`<2h`** (frente al **$48,91\%$ [$4.534$]** en normales). Incluso cuando contestan, en destacados tardan **$29,78\text{ h}$ de media** (mediana $3,43\text{ h}$) frente a **$15,04\text{ h}$** (mediana $1,34\text{ h}$) en normales.

### Hallazgo 3 — El número que decide el presupuesto: $804.177\text{ €}$ vs $537.420\text{ €}$ en comisiones y $+337.358\text{ €}$ sobre la mesa
- **NidoHogar vive del contrato, no de vender etiquetas de visibilidad:** toda la facturación acumulada por productos de visibilidad ($1.697$ compras: $1.364$ destacados y $333$ subidas de ranking) suma **$59.190,30\text{ €}$**, mientras que las comisiones por contratos firmados suman **$1.341.596,53\text{ €}$** ($22,7$ veces más).
- **Los anuncios normales aportan un $+49,6\%$ más de comisión total:** gracias a su mayor conversión ($740$ vs $429$ contratos), `normal` genera **$804.176,79\text{ €}$ ($59,94\%$ de la caja)** frente a **$537.419,74\text{ €}$ ($40,06\%$)** de `destacado` (**$+266.757,05\text{ €}$** a favor del anuncio normal), a pesar de que la comisión media unitaria del destacado es superior ($1.307,59\text{ €}$ vs $1.139,06\text{ €}$ sobre los $1.117$ contratos con comisión informada).
- **Contrafactual (Dinero sobre la mesa):** si los anuncios `destacados` simplemente igualasen la distribución de tiempos de respuesta de los `normales` ($48,91\%$ en `<2h` y $33,00\%$ sin respuesta), su conversión subiría del $4,98\%$ al **$7,98\%$**, cerrando **$687$ contratos en lugar de $429$** (**$+258$ contratos adicionales** y **$+337.358\text{ €}$ más en comisiones directas** sin necesidad de captar una sola visita adicional).

---

## 3. Tablas Maestras del Embudo (Base Limpia: 4.700 Anuncios · 55.275 Visitas · 17.880 Contactos · 1.169 Contratos)

### 3A. Tabla Maestra por Tipo de Anuncio (`destacado` vs `normal`)

| Tipo de Anuncio | Anuncios | Cuota Anuncios | Visitas Totales | Visitas / Anuncio | Contactos Totales | Contactos / Anuncio | Visita $\rightarrow$ Contacto | Atendidos `<2h` (%) | Sin Respuesta (%) | Horas Resp. Media (Mediana) | Contratos Cerrados | **Contacto $\rightarrow$ Contrato** | Visita $\rightarrow$ Contrato | Comisión Media (€) | **Comisión Total (€)** | Cuota Comisión |
| :--- | ---: | ---: | ---: | ---: | ---: | ---: | ---: | ---: | ---: | ---: | ---: | ---: | ---: | ---: | ---: | ---: |
| **destacado** | 1.489 | 31,68% | 26.533 | **17,82** | 8.610 | **5,79** | 32,45% | **24,00%** (2.066) | **50,00%** (4.305) | 29,78 h (3,43 h) | 429 | **4,98%** | 1,62% | 1.307,59 € | **537.419,74 €** | 40,06% |
| **normal** | 3.211 | 68,32% | 28.742 | **8,95** | 9.270 | **3,05** | 32,25% | **48,91%** (4.534) | **33,00%** (3.059) | 15,04 h (1,34 h) | **740** | **7,98%** | **2,57%** | 1.139,06 € | **804.176,79 €** | **59,94%** |
| **TOTAL NIDOHOGAR** | **4.700** | **100,00%** | **55.275** | **11,76** | **17.880** | **3,92** | **32,35%** | **36,91%** (6.600) | **41,19%** (7.364) | **20,69 h (1,68 h)** | **1.169** | **6,54%** | **2,11%** | **1.201,07 €** | **1.341.596,53 €** | **100,00%** |

### 3B. Tabla Maestra por Tramo de Tiempo de Respuesta (Con Control `Destacado` vs `Normal`)

| Tramo de Respuesta | Contactos Totales | Cuota Contactos | Contratos Totales | Cuota Contratos | **Conversión Global** | Contactos Destacado | Contratos Destacado | **Conv. Destacado** | Contactos Normal | Contratos Normal | **Conv. Normal** | Brecha (Dest. - Norm.) | **Comisión Total (€)** | Cuota Comisión |
| :--- | ---: | ---: | ---: | ---: | ---: | ---: | ---: | ---: | ---: | ---: | ---: | ---: | ---: | ---: |
| **`<2h` (Menos de 2 horas)** | 6.600 | 36,91% | **924** | **79,04%** | **14,00%** | 2.066 | 289 | **13,99%** | 4.534 | 635 | **14,01%** | **-0,02 pp** | **1.095.060,54 €** | **81,62%** |
| **`2-24h` (En el día)** | 2.434 | 13,61% | 170 | 14,54% | **6,98%** | 1.378 | 96 | **6,97%** | 1.056 | 74 | **7,01%** | **-0,04 pp** | 168.970,66 € | 12,59% |
| **`>24h` (Más de 1 día)** | 1.482 | 8,29% | 38 | 3,25% | **2,56%** | 861 | 22 | **2,56%** | 621 | 16 | **2,58%** | **-0,02 pp** | 41.066,76 € | 3,06% |
| **`sin_respuesta` (Ignorado)** | **7.364** | **41,19%** | 37 | 3,17% | **0,50%** | **4.305** | 22 | **0,51%** | 3.059 | 15 | **0,49%** | **+0,02 pp** | 36.498,57 € | 2,72% |
| **TOTAL NIDOHOGAR** | **17.880** | **100,00%** | **1.169** | **100,00%** | **6,54%** | **8.610** | **429** | **4,98%** | **9.270** | **740** | **7,98%** | **-3,00 pp** | **1.341.596,53 €** | **100,00%** |

---

## 4. Blindaje del Hallazgo: Hipótesis Alternativas Descartadas

1. **Control por Tramo de Tiempo de Respuesta (Descarte de la hipótesis de «peor calidad del lead en destacados» — Paradoja de Simpson):**
   - Al fijar el tramo de respuesta (Tabla 3B), la diferencia de conversión entre `destacado` y `normal` **desaparece por completo en los cuatro tramos**: **`13,99%` vs `14,01%` en `<2h`**, **`6,97%` vs `7,01%` en `2-24h`**, **`2,56%` vs `2,58%` en `>24h`** y **`0,51%` vs `0,49%` en `sin_respuesta`**.
   - *Conclusión:* Es una **Paradoja de Simpson** clásica. El producto destacado no convierte peor a igualdad de atención; su media global baja del $7,98\%$ al $4,98\%$ porque la mitad de sus contactos cae en el cubo de `sin_respuesta` ($0,50\%$ de conversión).
2. **Control por Zona y Ciudad (40 barrios canónicos en 4 ciudades):**
   - Tras normalizar las $183$ grafías de zona a los $40$ barrios de `zonas.csv` y las $17$ grafías de ciudad, la brecha y la saturación del destacado se repiten de forma idéntica en las cuatro plazas:
     - **Sevilla ($4.614$ contactos):** `destacado` convierte al **$4,80\%$** ($50,36\%$ sin respuesta) vs `normal` al **$8,17\%$** ($32,65\%$ sin respuesta).
     - **Valencia ($4.519$ contactos):** `destacado` convierte al **$4,40\%$** ($49,59\%$ sin respuesta) vs `normal` al **$7,40\%$** ($33,99\%$ sin respuesta).
     - **Málaga ($4.447$ contactos):** `destacado` convierte al **$4,77\%$** ($49,88\%$ sin respuesta) vs `normal` al **$8,22\%$** ($32,80\%$ sin respuesta).
     - **Madrid ($4.300$ contactos):** `destacado` convierte al **$6,06\%$** ($50,15\%$ sin respuesta) vs `normal` al **$8,15\%$** ($32,54\%$ sin respuesta).
3. **Control por Tramo de Precio Mensual del Inmueble (Excluyendo los $6$ outliers de precio):**
   - Los pisos que se alquilan y los que no se alquilan tienen exactamente la **misma mediana de precio ($950,00\text{ €}$)** y la misma media ($1.035,01\text{ €}$ vs $1.029,46\text{ €}$).
   - Dentro de cada tramo de precio, `destacado` convierte siempre peor y sufre un $\sim 50\%$ de abandono:
     - **Económico (`<800 €`, $6.426$ contactos):** `destacado` **$4,36\%$** ($49,77\%$ sin respuesta) vs `normal` **$8,14\%$** ($33,19\%$ sin respuesta).
     - **Medio (`800–1.200 €`, $5.791$ contactos):** `destacado` **$5,26\%$** ($50,16\%$ sin respuesta) vs `normal` **$8,14\%$** ($32,96\%$ sin respuesta).
     - **Alto (`>1.200 €`, $5.640$ contactos):** `destacado` **$5,35\%$** ($50,14\%$ sin respuesta) vs `normal` **$7,63\%$** ($32,82\%$ sin respuesta).
4. **Control por Tamaño de Agencia, Plan de Suscripción, Tipo de Anunciante y Canal:**
   - **Por tamaño de cartera de la agencia:** tanto en agencias **pequeñas (`<30` anuncios, $58$ agencias)**: `destacado` **$4,40\%$** vs `normal` **$7,27\%$** ($49,90\%$ vs $34,10\%$ sin respuesta); **medianas (`30–45` anuncios, $16$ agencias)**: **$5,94\%$** vs **$7,70\%$** ($50,82\%$ vs $32,15\%$ sin respuesta); como **grandes (`>45` anuncios, $46$ agencias)**: **$5,01\%$** vs **$8,32\%$** ($49,87\%$ vs $32,76\%$ sin respuesta).
   - **Por plan de suscripción:** `basico` ($4,64\%$ vs $7,65\%$), `pro` ($5,25\%$ vs $8,17\%$), `premium` ($4,89\%$ vs $8,70\%$) y `sin_suscripcion`/particulares ($5,22\%$ vs $8,00\%$).
   - **Por canal de contacto:** `formulario` ($5,07\%$ vs $8,11\%$), `chat` ($4,84\%$ vs $8,00\%$) y `telefono` ($4,90\%$ vs $7,63\%$).

---

## 5. Recomendación Accionable para el Comité

1. **NO lanzar «Destacado Premium» como palanca de contratos (Decisión para Álvaro Nadal y Gonzalo Prieto):**
   - Paralizar el lanzamiento de un nuevo escalón de visibilidad de pago. Inyectar aún más tráfico en anuncios destacados cuando las agencias ya dejan morir sin respuesta el **$50,00\%$ de sus leads ($4.305$ mensajes)** es poner un cartel luminoso más grande en la puerta de un restaurante que no tiene camareros para atender las mesas.
2. **Condicionar el algoritmo de posicionamiento al SLA de velocidad de respuesta (`<2h`) (Producto — Cristina Márquez):**
   - Modificar el orden de aparición en el marketplace para que la visibilidad (tanto orgánica como destacada) esté ponderada por el **porcentaje de respuesta en `<2h`** de la agencia. Las agencias que responden en menos de $2$ horas convierten al **$14,00\%$** y generan el **$81,62\%$ de las comisiones del portal**.
3. **Desplegar Alertas Push en Tiempo Real y «Freno de Saturación» al $40\%$ de abandono (Tecnología + Comercial):**
   - Activar notificaciones push/WhatsApp inmediatas al comercial cuando entra un contacto y establecer una **regla de negocio automática**: si una agencia con $\ge 100$ contactos supera el **$40\%$ de leads sin responder** (como *Habitat Costa* [$51,28\%$], *Gestión Trafalgar* [$50,00\%$] o *Alquileres El Faro* [$45,38\%$]), se pausa temporalmente la contratación de nuevos destacados hasta que desatasque su bandeja de entrada.
   - **Impacto económico objetivo:** llevar la tasa de respuesta rápida de los destacados al nivel actual de los anuncios normales desbloquea **$+258$ contratos y $+337.358\text{ €}$ anuales en comisiones directas** para NidoHogar.

---

## 6. Gráficos de Soporte en `reports/`
- [`01_embudo_destacado_vs_normal.png`](01_embudo_destacado_vs_normal.png) — *Primero la razón, luego la grieta: Visitas y contactos por anuncio vs. Tasa de conversión a contrato y Comisión total (€).*
- [`02_velocidad_respuesta_conversion.png`](02_velocidad_respuesta_conversion.png) — *La palanca reina: Tasa de conversión a contrato (`14,00%` en `<2h` vs `0,50%` sin respuesta, $\times 28$) y peso en comisiones.*
- [`03_saturacion_agencias_destacado.png`](03_saturacion_agencias_destacado.png) — *El mecanismo: `50,0%` de contactos ignorados en anuncios destacados vs `33,0%` en normales y caída de atención en `<2h` (`24,0%` vs `48,9%`).*
- [`04_control_confusion_tramos_respuesta.png`](04_control_confusion_tramos_respuesta.png) — *El blindaje científico (Paradoja de Simpson): Dentro del mismo tramo de respuesta (`<2h`), destacado (`13,99%`) y normal (`14,01%`) convierten igual.*
