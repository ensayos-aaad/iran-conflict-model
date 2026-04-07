# Diccionario de datos — Iran Conflict Model (ICM)

**Versión:** v0.1.2  
**Fecha:** 2026-04-06  
**Propósito:** Definir la estructura, campos y criterios de los datos crudos capturados en cada sesión de simulación.

---

## Estructura de carpetas

```
datos/
├── README-datos.md          ← este archivo
├── entradas/
│   ├── E1-prensa/           ← artículos consultados por sesión
│   ├── E2-timeline/         ← registro cronológico de eventos
│   ├── E4-ruido-narrativo/  ← posts y mensajes de actores
│   └── E5-mercados/         ← indicadores económicos por sesión
└── salidas/
    ├── S1-narrativas/       ← mapa de narrativas por sesión
    ├── S2-estado-factual/   ← hechos verificados por sesión
    ├── S3-desinformacion/   ← índice de desinformación por sesión
    └── S4-escenarios/       ← escenarios prospectivos por sesión
```

> **Nota:** E3 (Preguntas del usuario) no genera CSV — está documentada en los archivos de prompts.

---

## Convenciones generales

| Convención | Criterio |
|------------|----------|
| Formato de fecha | YYYY-MM-DD |
| Formato de hora | HH:MM UTC |
| Separador CSV | coma (,) |
| Encoding | UTF-8 |
| Valores nulos | NULL |
| Booleanos | TRUE / FALSE |
| Nombres de archivo | YYYY-MM-DD.csv por sesión |

---

## E1 — Prensa

**Archivo:** `entradas/E1-prensa/YYYY-MM-DD.csv`  
**Frecuencia:** Una fila por artículo consultado por sesión

| Campo | Tipo | Descripción | Ejemplo |
|-------|------|-------------|---------|
| fecha | DATE | Fecha de consulta | 2026-04-06 |
| sesion | INT | Número de sesión | 2 |
| medio | STRING | Nombre del medio | Al Jazeera |
| region | STRING | Región del medio | Medio Oriente |
| url | STRING | URL del artículo | https://... |
| titulo | STRING | Título del artículo | Iran launches... |
| fecha_publicacion | DATE | Fecha de publicación | 2026-04-05 |
| tema | STRING | Tema principal | Militar / Diplomático / Humanitario / Nuclear / Político |
| actor_principal | STRING | Actor principal mencionado | IRGC |
| tono | STRING | Tono editorial | Neutral / Pro-Iran / Pro-Israel / Pro-EEUU / Crítico |
| verificable | BOOLEAN | ¿El contenido es verificable? | TRUE |
| notas | STRING | Observaciones del analista | NULL |

---

## E2 — Línea de tiempo

**Archivo:** `entradas/E2-timeline/eventos.csv`  
**Frecuencia:** Acumulativo — se agregan filas con cada nuevo evento confirmado

| Campo | Tipo | Descripción | Ejemplo |
|-------|------|-------------|---------|
| fecha | DATE | Fecha del evento | 2025-06-13 |
| hora_utc | TIME | Hora UTC si se conoce | 00:15 |
| evento | STRING | Descripción del evento | Israel lanza Operación Rising Lion |
| tipo | STRING | Tipo de evento | Militar / Diplomático / Político / Económico / Humanitario |
| actor_iniciador | STRING | Quién inició la acción | Israel |
| actor_receptor | STRING | Quién recibió la acción | Irán |
| escala | STRING | Escala del evento | Local / Regional / Global |
| fuentes | STRING | Fuentes que lo confirman | Reuters, AP, BBC |
| certeza | STRING | Nivel de certeza | Alta / Media / Baja |
| impacto_mercado | BOOLEAN | ¿Tuvo impacto en mercados? | TRUE |
| notas | STRING | Observaciones | Primer ataque directo masivo |

---

## E4 — Ruido narrativo

**Archivo:** `entradas/E4-ruido-narrativo/YYYY-MM-DD.csv`  
**Frecuencia:** Una fila por mensaje relevante capturado por sesión

| Campo | Tipo | Descripción | Ejemplo |
|-------|------|-------------|---------|
| fecha | DATE | Fecha de captura | 2026-04-06 |
| sesion | INT | Número de sesión | 2 |
| actor | STRING | Quién publicó | Trump |
| plataforma | STRING | Dónde se publicó | Truth Social |
| tipo_actor | STRING | Tipo de actor | Gobierno / Militar / Proxy / Medio-oficial |
| bloque | STRING | Bloque geopolítico | EEUU-Israel / Iran / Rusia / China / Neutral |
| mensaje | STRING | Contenido resumido | Anuncia rendición iraní inminente |
| url | STRING | URL si disponible | https://... |
| fecha_publicacion | DATETIME | Fecha y hora de publicación | 2026-04-06 08:32 |
| intension | STRING | Intención narrativa detectada | Presión / Desinformación / Advertencia / Victoria |
| verificado | BOOLEAN | ¿Fue verificado por fuente independiente? | FALSE |
| notas | STRING | Observaciones | Contradicho por Reuters 2h después |

---

## E5 — Señales de mercado

**Archivo:** `entradas/E5-mercados/YYYY-MM-DD.csv`  
**Frecuencia:** Una fila por indicador por sesión

| Campo | Tipo | Descripción | Ejemplo |
|-------|------|-------------|---------|
| fecha | DATE | Fecha de captura | 2026-04-06 |
| sesion | INT | Número de sesión | 2 |
| indicador | STRING | Nombre del indicador | WTI Crude Oil |
| categoria | STRING | Categoría | Petróleo / Gas / Oro / Índice / Volatilidad / Shipping |
| valor | FLOAT | Valor en el momento de captura | 94.32 |
| unidad | STRING | Unidad de medida | USD/barril |
| variacion_diaria | FLOAT | Variación respecto al día anterior | +3.21 |
| variacion_pct | FLOAT | Variación porcentual | +3.52 |
| fuente | STRING | Fuente del dato | oilprice.com |
| hora_utc | TIME | Hora de captura UTC | 14:00 |
| evento_asociado | STRING | Evento del conflicto asociado si aplica | Amenaza cierre Ormuz |
| notas | STRING | Observaciones | Máximo en 6 meses |

---

## S1 — Mapa de narrativas

**Archivo:** `salidas/S1-narrativas/YYYY-MM-DD.csv`  
**Frecuencia:** Una fila por narrativa identificada por sesión

| Campo | Tipo | Descripción | Ejemplo |
|-------|------|-------------|---------|
| fecha | DATE | Fecha de análisis | 2026-04-06 |
| sesion | INT | Número de sesión | 2 |
| bloque | STRING | Bloque geopolítico | Iran |
| actor | STRING | Actor específico | IRGC |
| narrativa | STRING | Narrativa central identificada | Guerra de resistencia legítima |
| marco | STRING | Marco narrativo | Victimización / Amenaza / Victoria / Negociación |
| intensidad | STRING | Intensidad de la narrativa | Alta / Media / Baja |
| coherencia | STRING | Coherencia interna del relato | Alta / Media / Baja |
| audiencia_objetivo | STRING | A quién va dirigida | Población iraní / Mundo árabe / Occidente |
| fuentes_detectadas | INT | Número de fuentes que la replican | 4 |
| diverge_de_hechos | BOOLEAN | ¿Diverge del estado factual S2? | TRUE |
| peldaño_pearl | STRING | Peldaño de Pearl aplicado | Ver / Intervenir / Imaginar |
| notas | STRING | Observaciones del analista | NULL |

---

## S2 — Estado factual

**Archivo:** `salidas/S2-estado-factual/YYYY-MM-DD.csv`  
**Frecuencia:** Una fila por hecho analizado por sesión

| Campo | Tipo | Descripción | Ejemplo |
|-------|------|-------------|---------|
| fecha | DATE | Fecha de análisis | 2026-04-06 |
| sesion | INT | Número de sesión | 2 |
| hecho | STRING | Descripción del hecho | IRGC lanzó misiles hacia base en Bahrain |
| tipo | STRING | Tipo de hecho | Militar / Diplomático / Político / Económico |
| certeza | STRING | Nivel de certeza | Alta / Media / Baja / No confirmado |
| fuentes_confirman | INT | Número de fuentes que confirman | 3 |
| fuentes_niegan | INT | Número de fuentes que niegan | 1 |
| fuentes_principales | STRING | Fuentes que lo respaldan | Reuters, AP, BBC |
| fecha_evento | DATE | Fecha en que ocurrió | 2026-04-05 |
| impacto | STRING | Impacto estimado | Alto / Medio / Bajo |
| estado | STRING | Estado del hecho | Confirmado / En disputa / Desmentido |
| notas | STRING | Observaciones | NULL |

---

## S3 — Índice de desinformación

**Archivo:** `salidas/S3-desinformacion/YYYY-MM-DD.csv`  
**Frecuencia:** Una fila por claim analizado por sesión

| Campo | Tipo | Descripción | Ejemplo |
|-------|------|-------------|---------|
| fecha | DATE | Fecha de análisis | 2026-04-06 |
| sesion | INT | Número de sesión | 2 |
| actor | STRING | Quien hizo el claim | Trump |
| plataforma | STRING | Dónde se publicó | Truth Social |
| claim | STRING | Afirmación analizada | Iran pidió rendición total |
| verificado | STRING | Estado de verificación | TRUE / FALSE / PARCIAL |
| fuente_verificacion | STRING | Fuente que verifica o desmiente | Reuters, AP |
| distancia_factual | STRING | Distancia respecto a hechos verificados | Alta / Media / Baja |
| score_ruido | FLOAT | Score 0.0 a 1.0 — 1.0 es desinformación total | 0.91 |
| tiempo_verificacion_hrs | FLOAT | Horas hasta ser verificado/desmentido | 2.5 |
| amplificacion | STRING | Nivel de amplificación en redes | Alta / Media / Baja |
| intencion_detectada | STRING | Intención probable | Presión / Engaño / Confusión / Advertencia |
| notas | STRING | Observaciones | Contradicho por 4 fuentes independientes |

---

## S4 — Escenarios prospectivos

**Archivo:** `salidas/S4-escenarios/YYYY-MM-DD.csv`  
**Frecuencia:** Una fila por escenario por sesión

| Campo | Tipo | Descripción | Ejemplo |
|-------|------|-------------|---------|
| fecha | DATE | Fecha de análisis | 2026-04-06 |
| sesion | INT | Número de sesión | 2 |
| escenario | STRING | Nombre del escenario | Escalada total |
| descripcion | STRING | Descripción del escenario | IRGC lanza ofensiva masiva regional |
| probabilidad | FLOAT | Probabilidad 0.0 a 1.0 | 0.25 |
| horizonte | STRING | Horizonte temporal | 7 días / 30 días / 90 días |
| variables_clave | STRING | Variables que lo activan | Cierre Ormuz, ataque a base EEUU |
| supuestos | STRING | Supuestos del escenario | Sin negociación diplomática activa |
| indicadores_alerta | STRING | Señales tempranas a monitorear | VIX > 35, petróleo > 110 USD |
| peldaño_pearl | STRING | Peldaño de Pearl dominante | Imaginar (Counterfactual) |
| sesion_anterior_prob | FLOAT | Probabilidad en sesión anterior | NULL |
| delta_prob | FLOAT | Cambio respecto a sesión anterior | NULL |
| notas | STRING | Observaciones | NULL |

---

## Señal de convergencia — registro histórico

**Archivo:** `salidas/convergencia.csv`  
**Frecuencia:** Una fila por sesión — acumulativo

| Campo | Tipo | Descripción | Ejemplo |
|-------|------|-------------|---------|
| fecha | DATE | Fecha de la sesión | 2026-04-06 |
| sesion | INT | Número de sesión | 2 |
| score_narrativas | FLOAT | Estabilidad S1 — 0 caótico, 1 estable | 0.32 |
| score_factual | FLOAT | Certeza S2 — 0 incierto, 1 verificado | 0.61 |
| score_ruido | FLOAT | Nivel S3 — 0 limpio, 1 contaminado | 0.78 |
| score_escenarios | FLOAT | Dispersión S4 — 0 concentrado, 1 disperso | 0.45 |
| convergencia_global | FLOAT | Media ponderada de los cuatro scores | 0.54 |
| estado | STRING | Estado del sistema | Caótico / Inestable / Transitando / Convergiendo / Estable |
| notas | STRING | Observaciones | Primera sesión operativa — línea de base |

---

## Notas para el analista de datos

1. Los scores son asignados por el motor de inferencia — no son automáticos. Representan el juicio del sistema en cada sesión.
2. El campo `delta_prob` en S4 permite trackear la evolución de cada escenario a lo largo del tiempo.
3. El archivo `convergencia.csv` es la serie de tiempo principal del sistema — graficarla muestra la evolución del conflicto desde la perspectiva del modelo.
4. Todos los archivos por sesión usan la misma fecha en el nombre — esto permite cruzar entradas y salidas de la misma sesión fácilmente.
5. Los valores NULL indican dato no disponible — no deben interpretarse como cero.

---

*Diccionario de datos v0.1.2 — actualizar con cada cambio de esquema.*
