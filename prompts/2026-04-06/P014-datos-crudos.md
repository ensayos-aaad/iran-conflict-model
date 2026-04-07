# P014 — Esquemas de datos crudos para trazabilidad

**Fecha:** 2026-04-06
**Sesión:** 01
**Tipo:** Diseño
**Peldaño Pearl:** N/A
**Impacto en modelo:** Alto

---

## Prompt

> "Se pueden crear datos crudos entradas y salidas para el modelo, esto para respaldar mas la dialectica con tablas que luego puedan ser analizadas por un analista de datos?"

---

## Respuesta del sistema

El sistema propuso y ejecutó la infraestructura completa de datos crudos:

**Archivos de entrada generados:**
- E1-prensa/schema.csv — artículos consultados por sesión
- E2-timeline/eventos.csv — línea de tiempo acumulativa con eventos fundacionales precargados
- E4-ruido-narrativo/schema.csv — posts y mensajes de actores
- E5-mercados/schema.csv — indicadores económicos por sesión

**Archivos de salida generados:**
- S1-narrativas/schema.csv — mapa de narrativas por sesión
- S2-estado-factual/schema.csv — hechos verificados por sesión
- S3-desinformacion/schema.csv — índice de desinformación por sesión
- S4-escenarios/schema.csv — escenarios prospectivos por sesión
- convergencia.csv — serie de tiempo acumulativa de la meta-salida

**Diccionario de datos:** README-datos.md con descripción completa de todos los campos, tipos, criterios y convenciones.

---

## Inferencia generada

Los datos crudos convierten el modelo de herramienta analítica a **sistema con valor científico acumulable**. La diferencia es fundamental: sin datos estructurados, las sesiones son conversaciones; con datos estructurados, las sesiones son experimentos con resultados comparables entre sí.

El archivo `convergencia.csv` es especialmente valioso — es la serie de tiempo que permite graficar la evolución del conflicto desde la perspectiva del modelo a lo largo de todas las sesiones.

---

## Impacto en el modelo

Completó la Fase 1 — infraestructura. Agregó la carpeta `datos/` al repositorio con 9 archivos de esquema. Cierra el ciclo de preparación antes de la simulación operativa.

**Commit correspondiente:** v0.1.2 — infraestructura de datos
