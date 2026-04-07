# Changelog
> Registro de versiones del Iran Conflict Model (ICM)

Todas las versiones siguen el estándar [Semantic Versioning](https://semver.org/) — MAJOR.MINOR.PATCH

---

## [v0.1.3] — 2026-04-06

### Añadido

**Diseño experimental completo**
- docs/diseno-experimental.md — documento consolidado con todo el diseño
- docs/prompt-plantilla.md — protocolo diario replicable por cualquiera
- docs/guia-captura-datos.md — instrucciones para llenar CSVs sin conocimiento técnico
- docs/guia-github.md — instrucciones para subir el repo a github.com

**Protocolo de muestreo definido**
- Frecuencia diaria a las 8:00 PM hora Colombia (UTC-5 / 01:00 UTC)
- Ventana de captura: últimas 24 horas
- Tipos de sesión: ESTANDAR / EMERGENCIA / OMITIDA
- 6 criterios de disparo para sesiones de emergencia

**Reglas de integridad**
- Hasta 2 días consecutivos omitidos → experimento válido
- 3+ días consecutivos → interrupción de serie documentada
- Más del 20% de omisiones en 90 días → validez comprometida

**Horizontes temporales simplificados**
- 7 días — horizonte táctico
- 30 días — horizonte estratégico

**Validación**
- datos/validacion/registro-validacion.csv
- datos/validacion/README-validacion.md
- Métrica: Brier Score — meta < 0.25
- Fuentes árbitro: ACLED, Uppsala, NewsGuard, PolitiFact

### Estado
Fase 1 completada. Sistema listo para primera sesión operativa.

---

## [v0.1.2] — 2026-04-06

### Añadido

**Infraestructura de datos**
- datos/README-datos.md — diccionario completo de campos
- Schemas CSV para E1, E2, E4, E5
- E2-timeline con 7 eventos históricos precargados
- Schemas CSV para S1, S2, S3, S4
- datos/salidas/convergencia.csv inicializado
- P014 documentado

### Estado
Infraestructura de datos completa.

---

## [v0.1.1] — 2026-04-06

### Añadido

**Evidencia experimental sesión 01**
- prompts/README-prompts.md
- prompts/2026-04-06/P001 a P013

### Estado
Trazabilidad completa de sesión 01.

---

## [v0.1.0] — 2026-04-06

### Añadido

**Arquitectura del sistema**
- Modelo de caja negra de ciclo cerrado
- 5 entradas, 4 salidas, 1 meta-salida, 3 lazos de retroalimentación
- Motor de inferencia basado en Escalera de Causalidad de Judea Pearl
- Punto cero histórico: junio 2025 / febrero 2026
- README.md, CHANGELOG.md, simulaciones/2026-04-06-sesion-01.md

### Estado
Arquitectura conceptual completa.

---

## [Próximas versiones]

### [v0.2.0] — pendiente
- Primera sesión operativa con datos reales

### [v0.3.x] — pendiente
- GitHub Actions — validación automática de CSVs

### [v1.0.0] — pendiente
- Sistema completo con 90+ sesiones y Brier Score calculado

## [v0.1.5] — 2026-04-06

### Sesión 02 completada — Primera sesión operativa

**17 vectores procesados:**
E3 inyecciones: Artemis 2, patrón Trump, Stargate, 
Kushner, Dimon, OTAN/Japón, bolsillo americano, 
divisas EUR/USD/CNY, FMI/BM/BRICS, ONU-grupos de 
estados, cadena de mando, logística/municiones, 
reservas de crudo, factor Epstein

**Señal de convergencia:** 0.47 → 0.75 
(INESTABLE → CONVERGIENDO)

**S4 horizonte 30 días:**
A: 0.50→0.64 | B: 0.44→0.12 | C: 0.22→0.14

**Nodos próxima sesión:**
Ultimátum 7 abril, Rutte-Trump 8 abril,
Bilderberg 10-12, FMI/BM 13-18, Bondi 14 abril

### Estado
Sesión 02 completa. Sistema en CONVERGIENDO.
Sesión 03 programada 8 abril 8PM Colombia.

---

*Formato basado en [Keep a Changelog](https://keepachangelog.com/)*
