🇬🇧 [English version](README.en.md)

# Portafolio de Análisis de Datos — Hector Cárdenas

**Analista de datos y de fútbol · Scouting y análisis táctico**

Ocho casos de negocio resueltos de principio a fin con Python y SQL. Cada proyecto sigue el formato de encargo de 5 días: auditoría de datos, limpieza, ranking de superficie, descubrimiento del hallazgo, control de variables de confusión y one-pager ejecutivo con visualizaciones. La pregunta común: **la métrica que se ve en el panel (volumen, facturación, ocupación) ¿coincide con la que deja dinero?**

## Proyectos

| # | Proyecto | Sector | Descripción | Carpeta |
|---|---|---|---|---|
| 1 | **BrightCart** | Retail / E-commerce de moda | Rentabilidad real de una campaña de rebajas tras devoluciones y logística inversa. | [`brightcart/`](brightcart/) |
| 2 | **PlayLoop** | Videojuegos móviles (F2P) | Retención por cohortes, embudo de niveles, ROAS/LTV por canal y modelo de churn. | [`playloop/`](playloop/) |
| 3 | **NidoHogar** | Portal inmobiliario (proptech) | Embudo visita → contacto → contrato y efecto real del anuncio destacado. | [`nidohogar/`](nidohogar/) |
| 4 | **VueltaFit** | Fitness / Gimnasios | Plan anual vs. mensual: renovación, sesgo de supervivencia y hábito de los primeros 21 días. | [`vueltafit/`](vueltafit/) |
| 5 | **RutaSabor** | Foodtech / Cocinas fantasma (delivery) | GMV vs. contribución por marca tras ingredientes, comisiones de marketplace e incidencias. | [`rutasabor/`](rutasabor/) |
| 6 | **AulaViva** | EdTech / Cursos online | Valor y LTV por canal de captación: finalización, renovación y cuota de valor. | [`aulaviva/`](aulaviva/) |
| 7 | **Ampara** | Seguros | Rentabilidad técnica por canal: Loss Ratio, Combined Ratio, renovación y margen. | [`ampara/`](ampara/) |
| 8 | **El Mirador** | Hotelería | Escalera ocupación → ADR → RevPAR → GOPPAR por hotel y canal de venta. | [`elmirador/`](elmirador/) |

## Habilidades demostradas

- **Python:** Pandas, NumPy — EDA forense, limpieza y tipado sistemático, uniones y métricas de negocio.
- **SQL:** DuckDB — rankings, `JOIN`s, embudos, cohortes y KPIs sobre tablas limpias.
- **Visualización:** Matplotlib y Seaborn — gráficos ejecutivos orientados a la decisión.
- **Machine Learning:** scikit-learn (modelo de predicción de churn en PlayLoop).
- **Métricas de negocio:** LTV, CAC, ROAS, retención por cohortes, Loss/Combined Ratio, RevPAR/GOPPAR, margen de contribución, tasa de devolución.
- **Pensamiento analítico:** control de variables de confusión (paradoja de Simpson), sesgo de supervivencia, contrafactuales.
- **Comunicación:** one-pagers ejecutivos con recomendación accionable.

## Estructura

```
<proyecto>/
├── dia_01.ipynb … dia_05.ipynb   # cuadernos con salidas
├── data/raw/ · data/clean/      # datos del caso
├── reports/                      # gráficos y ONE_PAGER.md
└── README.md
```

## Cómo ejecutar

```bash
python -m venv .venv && source .venv/bin/activate
pip install -r requirements.txt
jupyter notebook
```

## Contacto

- GitHub: [@reme1982](https://github.com/reme1982)
- LinkedIn: [hector-cardenas-datos](https://www.linkedin.com/in/hector-cardenas-datos/)
- X: [@Datos_Scout_Fut](https://x.com/Datos_Scout_Fut)

> Los datos de los casos son sintéticos y con fines formativos.
