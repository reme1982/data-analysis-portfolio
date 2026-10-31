# ONE-PAGER EJECUTIVO — PLAYLOOP STUDIOS (MOBILE GAMING ANALYTICS)
**Para:** Comité de Dirección · Laura (Head of Product & Game Design) · Carlos (Head of User Acquisition / Marketing) · Diego (Senior Data Mentor) · Dirección Financiera (CFO)  
**Asunto:** Auditoría forense de retención, embudo de jugabilidad (Gameplay Funnel), rentabilidad publicitaria (ROAS) y modelo predictivo de Churn  

---

## 1. Resumen Ejecutivo (En una frase)
**`CoinRush`** aparenta ser el motor de crecimiento en los paneles superficiales de User Acquisition porque aporta el **$35,0\%$ de todas las instalaciones** ($2.800$ de $8.000$ jugadores) con el **CPI/CAC más bajo del mercado ($0,45\text{ €}$)**, pero al tratarse de tráfico incentivado sufre un **Churn al Día 7 del $98,04\%$** ($\text{Retención D7 } 1,96\%$, $\text{D30 } 0,14\%$) y genera un **LTV ínfimo de $0,13\text{ €}$**, convirtiéndose en el **único canal con ROAS deficitario ($28,79\%$) y destruyendo $-897,26\text{ €}$ de margen neto** (sin él, el beneficio neto de PlayLoop subiría de **$+5.826,56\text{ €}$** a **$+6.723,82\text{ €}$** con un ROAS del **$186,20\%$**); al mismo tiempo, dentro del juego la retención y la facturación (**$14.886,57\text{ €}$ totales**, donde **solo $17$ Ballenas [$0,21\%$] aportan el $78,38\%$ de las compras IAP**) están amenazadas por dos fallos críticos de diseño confirmados por Machine Learning ($\text{Random Forest ROC-AUC } 0,9429$): el **Muro de Frustración del Nivel 6** (donde el Win Rate cae del **$63,74\%$ al $16,81\%$**, expulsando al **$47,83\%$** de los jugadores) y el **Bloqueo Técnico del Nivel 15** (**$0,00\%$ de Win Rate** en $203$ partidas).

---

## 2. Los Tres Hallazgos Clave

### Hallazgo 1 — La Trampa del CPI Barato en User Acquisition (`CoinRush` vs. `Apple Search Ads` y `Meta Ads`)
Si evaluamos las campañas únicamente por volumen de descargas y coste unitario de entrada (CPI/CAC), `CoinRush` domina el cuadro de mando de Marketing; cuando cruzamos con retención real y monetización híbrida (`IAP + Ads`), el ranking se invierte por completo:
- **El espejismo de `CoinRush` (AdNetwork incentivada):** capta **$2.800$ usuarios ($35,0\%$ de la base)** a solo **$0,45\text{ €/instalación}$** ($1.259,99\text{ €}$ de inversión), pero el **$98,04\%$ desaparece en el Día 7** (apenas $4$ jugadores llegan activos a D30). Cada usuario deja solo **$0,13\text{ €}$ de LTV** ($76,73\text{ €}$ en IAP + $286,00\text{ €}$ en Ads = $362,73\text{ €}$), arrojando un **ROAS del $28,79\%$** y una **pérdida neta de $-897,26\text{ €}$**.
- **El caso intermedio de `TikTok`:** logra el segundo CAC más barato (**$1,20\text{ €}$**, $700$ instalaciones por $839,98\text{ €}$), sostiene una retención D7 aceptable (**$17,14\%$**) pero se desinfla en el largo plazo (**D30 del $1,57\%$**), cerrando con un LTV modesto de **$1,57\text{ €}$** ($\text{ROAS } 131,06\%$, margen neto de **$+260,89\text{ €}$**).
- **Los motores reales de valor (`Apple Search Ads`, `Meta Ads`, `Google Ads` y `Orgánico`):**
  - **`Apple Search Ads (ASA)`** tiene el CAC más alto (**$2,20\text{ €}$**), pero atrae a los jugadores de mayor calidad: lidera en **Retención D1 ($47,22\%$)**, **D7 ($21,44\%$)** y **D30 ($4,56\%$)**, dispara el **LTV a $4,21\text{ €}$** ($32,5\times$ el LTV de CoinRush) y alcanza el **ROAS #1 de pago ($191,17\%$)**, aportando **$+1.805,18\text{ €}$ netos**.
  - **`Meta Ads`** combina escala ($1.600$ jugadores, $20,0\%$) y retención (**D7 del $19,44\%$**), logrando un **LTV de $3,12\text{ €}$** frente a un CAC de $1,80\text{ €}$ (**ROAS $173,37\%$**) y liderando en **beneficio neto absoluto con $+2.113,05\text{ €}$**.
  - **`Orgánico`** ($600$ jugadores sin coste publicitario) genera **$2,56\text{ €}$ de LTV** y **$+1.535,62\text{ €}$ de margen puro**, mientras **`Google Ads`** ($1.400$ jugadores, CAC $1,50\text{ €}$, LTV $2,22\text{ €}$, ROAS $148,05\%$) suma otros **$+1.009,09\text{ €}$ netos**.

### Hallazgo 2 — El Embudo de Niveles (Gameplay Funnel): El Muro del Nivel 6 y el Techo Técnico del Nivel 15
El juego cautiva en el primer contacto (**Retención D1 global del $40,76\%$**, superando el benchmark de la industria casual de $35\text{--}40\%$, con una duración mediana de sesión idéntica de **$3,0\text{ minutos}$** tanto en Android [$3,04\text{ min}$ media] como en iOS [$3,09\text{ min}$ media]), pero el análisis de las **$61.671$ partidas válidas** descubre dos barreras estructurales en el mapa de progresión:
- **El Muro de la Frustración Temprana (Nivel 6):** entre los Niveles 1 y 5, la tasa de victoria desciende suavemente del **$70,83\%$ al $63,74\%$** ($\sim 1,27$ intentos por jugador). En el **Nivel 6**, el Win Rate se desploma de golpe al **$16,81\%$** ($1.920$ victorias frente a $9.499$ derrotas en $11.419$ partidas; **$3,10$ intentos por jugador**). Como consecuencia directa, **el $47,83\%$ de los jugadores que llegan al Nivel 6 abandonan definitivamente** (caen de $3.680$ jugadores en el Nivel 6 a solo $1.920$ en el Nivel 7).
- **El Muro Imposible / Techo Técnico (Nivel 15):** los **$160$ jugadores más comprometidos** que alcanzan el Nivel 15 registran **$0$ victorias y $203$ derrotas en $203$ intentos ($\text{Win Rate } 0,00\%$)**, revelando un bloqueo o bug de calibración que impide seguir avanzando precisamente al segmento VIP que financia el estudio.

### Hallazgo 3 — Economía Híbrida F2P y Concentración Extrema en Ballenas (Ley de Pareto)
PlayLoop recauda **$14.886,57\text{ €}$** ($\text{ARPU global } 1,86\text{ €}$), divididos en **$10.888,58\text{ €}$ por compras in-app ($\text{IAP } 73,14\%$)** y **$3.997,99\text{ €}$ por publicidad ($\text{Ads } 26,86\%$)**, con una **conversión neta a pago del $1,29\%$** ($103$ pagadores netos tras descontar $33$ reembolsos por $-85,67\text{ €}$) y un **ARPPU extraordinario de $105,71\text{ €}$**:
- **Dependencia extrema de las Ballenas (`Whales > 100 €`):** tan solo **$17$ jugadores ($0,21\%$ de la comunidad)** generan **$8.534,46\text{ €}$ en compras IAP ($78,38\%$ de todo el IAP)** y **$57,45\%$ del ingreso total del estudio**, con un ticket medio acumulado de **$502,03\text{ €}$** (liderados por las dos mega-ballenas `user_id=5905` con **$2.659,52\text{ €}$** y `user_id=3481` con **$2.656,41\text{ €}$**).
- **El pilar de los Delfines (`Dolphins 20–100 €`):** otros **$47$ jugadores ($0,59\%$)** aportan **$2.042,12\text{ €}$ ($18,75\%$ del IAP)**. Sumando **Ballenas + Delfines ($64$ usuarios, el $0,80\%$ de la base), concentran el $97,13\%$ de las compras IAP ($10.576,58\text{ €}$)**.
- **La base `Free Player` ($98,71\%$) sostiene el negocio de Ads:** los $7.897$ jugadores sin gasto neto en tienda generan **$3.866,55\text{ €}$ en impresiones publicitarias ($96,71\%$ del ingreso por Ads)**, demostrando la complementariedad del modelo híbrido.

---

## 3. Tablas Maestras de Resultados (8.000 Jugadores Únicos Auditados)

### 3.1 Tabla Maestra de Canales de Adquisición (UA), Retención y Rentabilidad (ROAS)

| Canal UA | Usuarios | Cuota Usu. | Ret. D1 | Ret. D7 | Ret. D30 | Churn D7 | Gasto UA (€) | Ingreso IAP (€) | Ingreso Ads (€) | Ingreso Total (€) | CAC (€) | LTV (€) | ROAS (%) | Margen Neto (€) |
| :--- | ---: | ---: | ---: | ---: | ---: | ---: | ---: | ---: | ---: | ---: | ---: | ---: | ---: | ---: |
| **Meta Ads** | 1.600 | 20,00% | 43,38% | 19,44% | 3,69% | 80,56% | 2.880,01 € | 3.753,06 € | 1.240,00 € | 4.993,06 € | 1,80 € | 3,12 € | 173,37% | **+2.113,05 €** |
| **Apple Search Ads** | 900 | 11,25% | **47,22%** | **21,44%** | **4,56%** | **78,56%** | 1.980,02 € | 3.095,20 € | 690,00 € | 3.785,20 € | 2,20 € | **4,21 €** | **191,17%** | **+1.805,18 €** |
| **Orgánico** | 600 | 7,50% | 42,33% | 16,50% | 2,83% | 83,50% | 0,00 € | 1.035,62 € | 500,00 € | 1.535,62 € | 0,00 € | 2,56 € | $\infty$ | **+1.535,62 €** |
| **Google Ads** | 1.400 | 17,50% | 41,71% | 16,21% | 3,14% | 83,79% | 2.100,01 € | 2.229,10 € | 880,00 € | 3.109,10 € | 1,50 € | 2,22 € | 148,05% | +1.009,09 € |
| **TikTok** | 700 | 8,75% | 38,29% | 17,14% | 1,57% | 82,86% | 839,98 € | 698,87 € | 402,00 € | 1.100,87 € | 1,20 € | 1,57 € | 131,06% | +260,89 € |
| **CoinRush** | **2.800** | **35,00%** | **37,00%** | **1,96%** | **0,14%** | **98,04%** | 1.259,99 € | 76,73 € | 286,00 € | 362,73 € | **0,45 €** | **0,13 €** | **28,79%** | **-897,26 €** |
| **TOTAL PLAYLOOP** | **8.000** | **100,00%** | **40,76%** | **12,56%** | **2,20%** | **87,44%** | **9.060,01 €** | **10.888,58 €** | **3.997,99 €** | **14.886,57 €** | **1,13 €** | **1,86 €** | **164,31%** | **+5.826,56 €** |
| *Sin CoinRush* | *5.200* | *65,00%* | *42,79%* | *18,27%* | *3,31%* | *81,73%* | *7.800,02 €* | *10.811,85 €* | *3.711,99 €* | *14.523,84 €* | *1,50 €* | *2,79 €* | **186,20%** | **+6.723,82 €** |

---

### 3.2 Tabla Maestra de Segmentación F2P (Ley de Pareto e Ingresos Híbridos)

| Segmento F2P | Usuarios | Cuota Usuarios | Ingreso IAP (€) | Cuota IAP | Ingreso Ads (€) | Cuota Ads | Ingreso Total (€) | Cuota Total | Gasto Medio IAP (€) | ARPU Total (€) |
| :--- | ---: | ---: | ---: | ---: | ---: | ---: | ---: | ---: | ---: | ---: |
| **Free Player ($\le 0\text{ €}$)** | 7.897 | **98,71%** | -3,49 € | -0,03% | **3.866,55 €** | **96,71%** | 3.863,06 € | 25,95% | 0,00 € | 0,49 € |
| **Minnow ($\le 20\text{ €}$)** | 39 | 0,49% | 315,49 € | 2,90% | 48,72 € | 1,22% | 364,21 € | 2,45% | 8,09 € | 9,34 € |
| **Dolphin ($20\text{--}100\text{ €}$)** | 47 | 0,59% | 2.042,12 € | **18,75%** | 64,47 € | 1,61% | 2.106,59 € | 14,15% | 43,45 € | 44,82 € |
| **Whale ($> 100\text{ €}$)** | **17** | **0,21%** | **8.534,46 €** | **78,38%** | 18,25 € | 0,46% | **8.552,71 €** | **57,45%** | **502,03 €** | **503,10 €** |
| **TOTAL PLAYLOOP** | **8.000** | **100,00%** | **10.888,58 €** | **100,00%** | **3.997,99 €** | **100,00%** | **14.886,57 €** | **100,00%** | **105,71 €** *(ARPPU)* | **1,86 €** |

---

### 3.3 Resumen de Hitos del Embudo de Niveles (Gameplay Funnel: Niveles 1 a 15)

| Nivel | Jugadores Únicos | Partidas Jugadas | Victorias | Derrotas | Win Rate (%) | Intentos / Jugador | Retención Acumulada | Abandono Inter-Nivel | Diagnóstico de Game Design |
| :---: | ---: | ---: | ---: | ---: | ---: | ---: | ---: | ---: | :--- |
| **Nivel 1** | 7.994 | 10.207 | 7.230 | 2.977 | 70,83% | 1,28 | 100,00% | 0,00% | Onboarding fluido y atractivo |
| **Nivel 5** | 4.557 | 5.797 | 3.695 | 2.102 | 63,74% | 1,27 | 57,01% | 16,22% | Cierre de fase tutorial estable |
| **Nivel 6** | **3.680** | **11.419** | **1.920** | **9.499** | **16,81%** | **3,10** | **46,03%** | 19,25% | **Muro de Frustración (pico de derrotas)** |
| **Nivel 7** | **1.920** | 2.437 | 1.528 | 909 | 62,70% | 1,27 | 24,02% | **47,83%** | **Consecuencia del Nivel 6 (-1.760 jug.)** |
| **Nivel 10** | 960 | 1.489 | 723 | 766 | 48,56% | 1,55 | 12,01% | 19,93% | Nivel jefe intermedio exigente pero sano |
| **Nivel 14** | 280 | 356 | 161 | 195 | 45,22% | 1,27 | 3,50% | 30,00% | Antesala del end-game actual |
| **Nivel 15** | **160** | **203** | **0** | **203** | **0,00%** | **1,27** | **2,00%** | **42,86%** | **Bloqueo Técnico / Nivel Imposible** |

---

## 4. Blindaje del Hallazgo: El Muro del Nivel 15, Causalidad Temporal y Modelo Predictivo de Churn

1. **Integridad Referencial, Reconciliación Contable y Causalidad Temporal ($0$ eventos fantasma y $0$ días negativos):**
   - **Limpieza del Star Schema (7 tablas):** se eliminaron **$40$ IDs duplicados** en `usuarios` ($8.040 \rightarrow 8.000$ usuarios únicos), se aislaron **$60$ sesiones con telemetría corrupta** ($\le 0\text{ s}$ o centinela $999.999\text{ s}$, quedando **$44.885$ sesiones válidas**) y **$45$ partidas con movimientos $\le 0$** (**$61.671$ partidas válidas**), y se homologaron los importes en pesos mexicanos aplicando la paridad exacta de catálogo (`19,50 MXN = 1 EUR`).
   - **Reconciliación 100% con Marketing:** tras normalizar las $23$ grafías caóticas de canal (`ASA`, `apple_search`, `facebook`, `coin_rush`, etc.), las **$8.000$ instalaciones facturadas** en `gasto_ua` cuadran con **$0,00\%$ de discrepancia** frente a los $8.000$ usuarios registrados.
   - **Causalidad Temporal Estricta:** la función determinista `parse_fecha_robusta` corrigió la inversión de día/mes en fechas mixtas (`ISO`, `DD/MM/YYYY` y texto en español), verificando **$0$ sesiones previas a la fecha de instalación** ($\text{rango limpio de } 0 \text{ a } 34 \text{ días de vida}$).
2. **Descarte de Apatía General: Doble Fuga por el Muro del Nivel 6 y el Bloqueo del Nivel 15:**
   - El desplome del **Stickiness Ratio ($\text{DAU}/\text{MAU}$)** durante los picos de campaña de junio (**$10,37\%$**) y julio (**$11,32\%$**) frente al **$\sim 50,3\%$** de la comunidad orgánica estable no se debe a fatiga del core loop, sino a la entrada masiva de tráfico incentivado de `CoinRush` combinada con el choque de los nuevos jugadores contra el **Nivel 6 ($\text{Win Rate } 16,81\%$)**.
   - En la cúspide del embudo, el **Nivel 15 ($\text{Win Rate } 0,00\%$ en $203$ partidas)** actúa como un techo artificial que frena en seco a los $160$ jugadores más avanzados, poniendo en riesgo la retención D30 de las ballenas y delfines.
3. **Demostración Matemática mediante Machine Learning Supervisado (`Random Forest` vs. `Regresión Logística`):**
   - Entrenamos dos modelos sin *data leakage* (división estratificada $75\%$ Train [$6.000$] / $25\%$ Test [$2.000$] y escalado aislado) para predecir la deserción definitiva antes del séptimo día ($\text{Churn D7 acumulado} = 43,31\%$, $3.465$ desertores frente a $4.535$ jugadores con actividad en $\text{D7+}$):
     - **Random Forest Classifier (Campeón):** **$\text{ROC-AUC} = 0,9429$** · $\text{Recall} = 85,10\%$ · $\text{Accuracy} = 86,75\%$ · $\text{Precision} = 84,42\%$ · $\text{F1-Score} = 0,8476$.
     - **Regresión Logística (Baseline):** $\text{ROC-AUC} = 0,9415$ · $\text{Recall} = 84,99\%$ · $\text{Accuracy} = 86,90\%$ · $\text{F1-Score} = 0,8489$.
   - **Importancia de Variables (Gini Importance):** el modelo confirma que el bloqueo en el mapa de niveles es el factor determinante del abandono: **`max_nivel` lidera con el $29,36\%$ de importancia total**, seguida de **`victorias` ($23,33\%$)**, **`total_partidas` ($15,12\%$)**, **`total_sesiones` ($13,69\%$)**, **`derrotas` ($5,26\%$)**, **`win_rate` ($4,05\%$)**, **`boosters_usados` ($3,80\%$)** y **`canal_norm_CoinRush` ($3,24\%$)**. Las 4 variables de progresión y actividad concentran el **$81,50\%$** del poder predictivo.

---

## 5. Recomendación Accionable para el Comité

1. **Cortar de raíz `CoinRush` y reasignar los $1.259,99\text{ €}$ a `Apple Search Ads` y `Meta Ads` (Marketing / UA):**
   - Apagar inmediatamente `CoinRush` elimina **$-897,26\text{ €}$ de pérdidas netas** y eleva de forma instantánea el margen neto del estudio a **$+6.723,82\text{ €}$** ($\text{ROAS } 186,20\%$).
   - Reinvertir ese presupuesto al $50\%$ entre **`Apple Search Ads`** ($\text{ROAS } 191,17\%$, $\text{LTV } 4,21\text{ €}$) y **`Meta Ads`** ($\text{ROAS } 173,37\%$, $\text{LTV } 3,12\text{ €}$) proyecta generar **$\sim +2.297\text{ €}$ de ingreso bruto adicional** y **$\sim +1.037\text{ €}$ de beneficio neto extra** (llevando el margen neto total del estudio por encima de **$+7.760\text{ €}$**).
2. **Recalibrar la dificultad del Nivel 6 y lanzar un Hotfix urgente en el Nivel 15 (Producto / Game Design):**
   - Reducir los objetivos o añadir $+3$ movimientos base en el **Nivel 6** para subir su Win Rate del **$16,81\%$** actual al rango saludable del **$50\text{--}55\%$**, conteniendo la fuga del $47,83\%$ de los jugadores hacia el Nivel 7.
   - Corregir de inmediato el bloqueo del **Nivel 15 ($\text{Win Rate } 0,00\%$)** y habilitar nuevos niveles ($16\text{--}25$) para evitar que los $160$ jugadores más fieles abandonen por falta de progresión.
3. **Activar el Trigger Preventivo de Live-Ops guiado por ML y el Programa VIP para Ballenas (Data & Monetización):**
   - Conectar el scoring del modelo **Random Forest** para intervenir sobre los **$2.506$ jugadores en Riesgo Crítico ($\text{probabilidad } \ge 80\%$)** entregando automáticamente un *Pack de Rescate* ($3$ boosters + $30\text{ min}$ de vidas infinitas) al segundo fallo consecutivo en el Nivel 6.
   - Crear un **Programa VIP (Atención prioritaria + Ofertas personalizadas y Pase de Temporada Plus)** para las **$17$ Ballenas y $47$ Delfines** que sostienen el **$97,13\%$ de los ingresos IAP ($10.576,58\text{ €}$)**.

---

## 6. Gráficos de Soporte en `reports/`
- [`01_curva_retencion_y_canales.png`](01_curva_retencion_y_canales.png) — *Curva clásica de retención (D0 a D30) frente al benchmark de la industria y comparativa de retención D1, D7 y D30 por canal de adquisición.*
- [`02_embudo_niveles_muro_nivel15.png`](02_embudo_niveles_muro_nivel15.png) — *Gameplay Funnel de jugadores únicos (Niveles 1 a 15) y desplome del Win Rate en el Muro del Nivel 6 (16,81%) y el Muro Imposible del Nivel 15 (0,00%).*
- [`03_roas_ltv_cac_canales.png`](03_roas_ltv_cac_canales.png) — *LTV vs. CAC y ROAS (%) por canal de UA: la trampa del CPI barato de CoinRush (28,8% ROAS) frente a Apple Search Ads (191,2%) y Meta Ads (173,4%).*
- [`04_segmentacion_whales_y_churn_rf.png`](04_segmentacion_whales_y_churn_rf.png) — *Concentración de ingresos F2P en Ballenas/Delfines (Ley de Pareto) y Top 10 Importancia de Variables (Gini) del modelo Random Forest de Churn.*
