# Iran Conflict Model (ICM)
> Sistema de análisis de conflictos mediante inferencia causal y fuentes abiertas

**Versión:** v0.1.7
**Fecha de inicio:** 2026-04-06
**Última sesión:** Sesión 04 — 2026-04-19
**Próxima sesión:** Sesión 05 — post 2026-04-22 (post vencimiento ceasefire) o antes si hay escalada
**Estado:** OPERATIVO — CONVERGIENDO (señal 0.82)
**Metodología base:** Inferencia causal (Judea Pearl, *The Book of Why*, 2018)

---

## Estado del modelo

| Campo | Valor |
|-------|-------|
| Sesiones completadas | 4 |
| Última sesión | Sesión 04 — 2026-04-19 |
| Vectores procesados (acumulado) | 50 |
| Señal de convergencia | 0.82 — CONVERGIENDO |
| Escenario dominante | A — pero bajo presión severa |
| Probabilidad Escenario A (30 días) | 0.50 |
| Día del conflicto | ~50 |
| Nodos críticos activos | N10 (22 abril), N13 (28 abril), N14 (Hutíes) |

### Probabilidades S05 — Horizonte 30 días

| Escenario | Descripción | Probabilidad |
|-----------|-------------|-------------|
| A | Ceasefire + Hormuz parcialmente abierto | **0.50** |
| B | Guerra prolongada — Hormuz cerrado | 0.30 |
| C | Escalada — ataque infraestructura crítica | 0.13 |
| D | Colapso régimen iraní | 0.03 |
| E | Wildcard operacional (Hutíes) | 0.04 |

### Scores de convergencia

| Score | S03 cierre | S04 cierre | Δ |
|-------|------------|------------|---|
| Narrativas | 0.83 | 0.88 | ↑ |
| Factual | 0.96 | 0.97 | ↑ |
| Ruido | 0.38 | 0.48 | ↓ |
| Escenarios | 0.84 | 0.77 | ↓↓ |
| **Convergencia global** | **0.85** | **0.82** | ↓ |

**Nota metodológica S04:** La convergencia baja no porque el modelo entienda menos — sino porque la situación está en flujo activo de alta velocidad. El componente factual es el más alto de toda la historia del modelo (0.97). La bajada es honesta y el modelo la registra correctamente.

---

## ¿Qué es este sistema?

El Iran Conflict Model (ICM) es un sistema de análisis de ciclo cerrado diseñado para monitorear, interpretar y proyectar el conflicto entre EEUU, Israel e Irán iniciado el 28 de febrero de 2026. Opera mediante dialéctica humano-IA, procesando múltiples flujos de información simultáneos para producir lecturas depuradas de ruido y escenarios prospectivos con base causal.

El sistema no es un agregador de noticias. Es un motor de inferencia que distingue correlación de causalidad, mide la contaminación narrativa del entorno informativo y actualiza probabilidades de escenarios en tiempo real.

---

## Arquitectura del sistema

El modelo opera como una **caja negra de ciclo cerrado** con 5 entradas, 4 salidas, 1 meta-salida y 3 lazos de retroalimentación.

```
[ENTRADAS] ──→ [MOTOR DE INFERENCIA] ──→ [SALIDAS]
                       ↑                      │
                       └──── [LAZOS FB] ───────┘
                                    ↓
                       [SEÑAL DE CONVERGENCIA]
```

---

## Entradas (5)

| # | Entrada | Tipo | Descripción |
|---|---------|------|-------------|
| E1 | Fuentes de prensa | Informativa | Medios verificables de los 5 continentes |
| E2 | Línea de tiempo | Histórica | Registro cronológico del conflicto desde feb 2026 |
| E3 | Preguntas del usuario | Dialéctica | Hipótesis, intuiciones y datos del operador |
| E4 | Ruido narrativo | Contaminada | Redes sociales, Telegram, canales oficiales |
| E5 | Señales de mercado | Cuantitativa | Petróleo, VIX, oro, shipping, cripto |

### Notas E5 — Sesión 04

**Brent al cierre S04:** $96.88 (+7% post-TOUSKA) — zona ambigua según V43.
Umbral de presión privada: $110. Umbral de recesión Goldman: $140.
Señal más honesta disponible: apertura asiática del lunes.

**Insider trading $2.28B:** CFTC activo. Tres episodios documentados.
Trump Jr. asesor de Kalshi, inversor en Polymarket. Casa Blanca
envió email interno advirtiendo contra insider trading — confirmación implícita.

---

## Motor de inferencia

Basado en la **Escalera de Causalidad de Judea Pearl** (tres peldaños):

### Peldaño 1 — Ver (*Association*)
Detección de correlaciones cruzadas entre las 5 entradas.

### Peldaño 2 — Intervenir (*Intervention*)
Análisis de qué cambia en el sistema cuando ocurre un evento.

### Peldaño 3 — Imaginar (*Counterfactual*)
Razonamiento contrafáctico: base para la construcción de escenarios prospectivos.

---

## Salidas (4)

| # | Salida | Pregunta que responde |
|---|--------|----------------------|
| S1 | Mapa de narrativas | ¿Quién construye qué relato y con qué intención? |
| S2 | Estado factual | ¿Qué ocurrió realmente, depurado de ruido? |
| S3 | Índice de desinformación | ¿Cuánto del debate público es propaganda? |
| S4 | Escenarios prospectivos | ¿Hacia dónde puede ir el conflicto? |

---

## Hipótesis activas

| ID | Formulación | Estado |
|----|-------------|--------|
| H1 | ¿Puede Pezeshkian firmar acuerdo sin aval IRGC? | ACTIVA — IRGC más autónomo |
| H2 | ¿Canal Pakistan es negociación real? | **CONFIRMADA Y EVOLUCIONADA** — garante militar |
| H3 | ¿Netanyahu tiene incentivo para sabotear el ceasefire? | **CONFIRMADA NIVEL OPERACIONAL** |
| H4 | ¿Sistema 2 niveles Hormuz es el nuevo Canal de Suez? | SEÑAL FUERTE — complicado por minas |
| H5 | Proyecto Abraham vaciándose de contenido estratégico | **SEÑAL MUY FUERTE** |
| H6 | ¿Vulnerabilidad compartida reemplaza valores como base del nuevo orden? | ACTIVA — 6-18 meses |
| H7 | ¿Eje moral-religioso rompe base evangélica de Trump? | ACTIVA — primera señal (MTG) |

---

## Nodos críticos

| ID | Descripción | Fecha | Estado |
|----|-------------|-------|--------|
| N1 | Ultimátum Trump 7 abril | 2026-04-07 | ✅ RESUELTO — TACO |
| N2 | Reunión Rutte-Trump | 2026-04-08 | ✅ RESUELTO — OTAN no mordió |
| N10 | Ceasefire vence | 2026-04-22 8PM ET | 🔴 CRÍTICO — ACTIVO |
| N11 | Líbano / Hezbollah | INMEDIATO | 🔴 ESCALANDO |
| N12 | China / Escollo Scarborough | ACTIVO | 🔴 CONFRONTACIÓN |
| N13 | War Powers Day 60 | 2026-04-28 | 🔴 RELOJ DURO |
| N14 | Hutíes / Bab el-Mandeb | LATENTE | 🟠 POSICIONAMIENTO |

---

## Vectores estructurales clave — Sesión 04

| Vector | Descripción | Peso |
|--------|-------------|------|
| V37 | Cumbre Madrid — bloque progresista atlántico | ALTO |
| V38 | Crisis interna EEUU — multi-componente | MUY ALTO |
| V39 | Pakistan escolta con J-10 chinos — H3 operacional | CRÍTICO |
| V40 | Papa Leo XIV (americano) vs Trump | MUY ALTO |
| V41 | Insider trading $2.28B — CFTC activo | CRÍTICO |
| V42 | War Powers Resolution — día 60: 28 abril | MUY ALTO |
| V43 | Tesis de los dueños del mundo — umbral Brent $110 | ESTRUCTURAL |
| V44 | Rubio ascendente — dinámica cortesanos | ALTO |
| V45 | Hutíes posicionamiento litoral — Bab el-Mandeb | MUY ALTO |
| V46 | Trump como Jesucristo — MTG lo condena | MUY ALTO |
| V47 | China bloquea Escollo Scarborough | MUY ALTO |

---

## DOS RELOJES — Tensión estructural S04-S05

**Reloj militar** → apunta a Escenario B
TOUSKA + IRGC atacando buques + Hormuz cerrado +
ceasefire expirando 72h + Netanyahu ocupando Líbano

**Reloj financiero** → apunta a Escenario A
War Powers Day 60 (28 abril) + Goldman recesión a $140 +
$2.28B insider trading bajo CFTC + fondos Golfo presionando +
33 republicanos no buscan reelección + Congreso a un voto

**Dato técnico crítico:** Irán perdió rastro de sus propias
minas en Hormuz. No puede abrir completamente aunque quiera.
Cualquier acuerdo debe incluir apoyo técnico para desminado.

---

## Historial de sesiones

| Sesión | Fecha | Vectores | Convergencia | Escenario A | Estado |
|--------|-------|----------|--------------|-------------|--------|
| 01 | 2026-04-06 | 3 | 0.47 — INESTABLE | 0.50 | ✅ Completa |
| 02 parte 1 | 2026-04-06 | 17 | 0.75 — CONVERGIENDO | 0.64 | ✅ Completa |
| 02 parte 2 | 2026-04-06 | 24 (acum.) | 0.82 — CONV. FUERTE | 0.66 | ✅ Completa |
| 03 | 2026-04-08 | 36 (acum.) | 0.85 — CONVERGIENDO | 0.65 | ✅ Completa |
| 04 | 2026-04-19 | 50 (acum.) | 0.82 — CONVERGIENDO | 0.50 | ✅ Completa |
| 05 | ~2026-04-23 | — | — | — | 🔜 Post-ceasefire |

---

## Roadmap

- [x] v0.1.0 — Arquitectura conceptual documentada
- [x] v0.1.4 — Sesiones 01 y 02 parte 1 completadas
- [x] v0.1.5 — Sesión 02 parte 2 — Consilience como arquitectura epistemológica
- [x] v0.1.6 — Sesión 03 — 14 vectores nuevos — corrección honesta al cierre
- [x] v0.1.7 — Sesión 04 — 14 vectores nuevos — dos relojes en tensión
- [ ] v0.2.0 — Pipeline de scraping automatizado
- [ ] v0.3.0 — Motor bayesiano implementado en código
- [ ] v1.0.0 — Sistema operativo completo

---

## Referencia metodológica principal

Pearl, J. & Mackenzie, D. (2018). *The Book of Why: The New Science of Cause and Effect*. Basic Books.

---

*Proyecto iniciado el 6 de abril de 2026. Operado mediante dialéctica humano-IA.*
*Operador: docente colombiano. Trayectoria analítica: 6.5 → 9.0 en 5 sesiones.*
