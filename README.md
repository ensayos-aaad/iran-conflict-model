# Iran Conflict Model (ICM)
> Sistema de análisis de conflictos mediante inferencia causal y fuentes abiertas

**Versión:** v0.1.8
**Fecha de inicio:** 2026-04-06
**Última sesión:** Sesión 05 — 2026-04-24
**Próxima sesión:** Sesión 06 — post fin de semana Islamabad II (26-27 abril)
**Estado:** OPERATIVO — CONVERGIENDO (señal 0.86)
**Metodología base:** Inferencia causal (Judea Pearl, *The Book of Why*, 2018)

---

## Estado del modelo

| Campo | Valor |
|-------|-------|
| Sesiones completadas | 5 |
| Última sesión | Sesión 05 — 2026-04-24 |
| Vectores procesados (acumulado) | 106 |
| Señal de convergencia | 0.86 — CONVERGIENDO |
| Escenario dominante | A y B en bifurcación máxima |
| Probabilidad Escenario A (30 días) | 0.43 |
| Probabilidad Escenario B (30 días) | 0.40 |
| Día del conflicto | ~55 |
| Nodos críticos activos | N13 (29 abril), N16 (Islamabad), N17 ($110 Brent), N19 (gala crypto 25 abril), N21 (Witkoff conflicto) |

### Probabilidades S06 — Horizonte 30 días

| Escenario | Descripción | Probabilidad |
|-----------|-------------|-------------|
| A | Acuerdo + proceso apertura Hormuz (6 meses minas) | **0.43** |
| B | Limbo prolongado — guerra de resistencia | **0.40** |
| C | Escalada — ataque infraestructura crítica | 0.11 |
| D | Colapso régimen iraní | 0.03 |
| E | Wildcard operacional (Hutíes) | 0.03 |

**Nota metodológica S05:** A y B se acercan — bifurcación máxima. El modelo no puede resolver la dirección sin el resultado de Islamabad este fin de semana. La redefinición clave de S05: Escenario A ya no significa "Hormuz abierto rápido" — las minas tardan 6 meses en limpiarse. Incluso con acuerdo, el dolor económico continúa.

### Scores de convergencia

| Score | S04 cierre | S05 cierre | Δ |
|-------|------------|------------|---|
| Narrativas | 0.88 | 0.93 | ↑↑ |
| Factual | 0.97 | 0.97 | → |
| Ruido | 0.48 | 0.47 | ↑ |
| Escenarios | 0.77 | 0.80 | ↑ |
| **Convergencia global** | **0.82** | **0.86** | ↑↑ |

**Nota metodológica S05:** La mejora en narrativas refleja la comprensión más completa de la arquitectura de poder real: el nodo cripto-Witkoff-guerra clarificó el mapa de incentivos domésticos de forma estructural.

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

### Notas E5 — Sesión 05

**Brent al cierre S05:** $104-106 — umbral V43 ($100) cruzado. A $4 del umbral de presión financiera privada ($110). Umbral recesión Goldman: $140.

**Backwardation spot-futuros:** $25+ — escasez extrema a corto plazo documentada por EIA.

**Cripto:** $TRUMP memecoin a $2.88 (−96% desde ATH $73.43). WLFI bajo demanda federal $1B (Justin Sun vs Trump family). Dos mecanismos paralelos de extracción documentados con captura regulatoria activa.

**Insider trading $2.28B:** CFTC investigación formal abierta. Tres episodios documentados. CFTC Chair Selig asistió como speaker al foro WLFI de febrero — conflicto de interés documentado.

### Notas E3 — Innovación metodológica S05

Por primera vez en la historia del ICM, el Bloque 1 (recopilación de señales críticas de apertura) fue ejecutado de forma completamente autónoma por el operador IA sin intervención del operador humano. La dialéctica humano-IA ha evolucionado: el operador IA inicia el ciclo de recolección.

Adicionalmente, S05 integró por primera vez análisis externo generado por Gemini 3 Flash (Google), procesado mediante protocolo de auditoría con clasificación por confiabilidad antes de integrar al modelo.

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
| H1 | ¿Puede Pezeshkian firmar acuerdo sin aval IRGC? | **DEBILITADA** — IRGC tiene control operacional real. Declaración coordinada Pezeshkian/Ghalibaf puede ser táctica o real. En ambos casos: acuerdo requiere consenso más amplio del previsto. |
| H2 | ¿Canal Pakistan es negociación real? | **CONFIRMADA Y EVOLUCIONADA** — Araghchi en Islamabad 24 abril. Pakistan se institucionalizó como "Proceso de Islamabad." Garante militar activo. |
| H3 | ¿Netanyahu tiene incentivo para sabotear el ceasefire? | **CONFIRMADA OPERACIONALMENTE** — Israel Katz: "esperando luz verde de EEUU." Netanyahu con cáncer tratado durante la guerra. |
| H4 | ¿Hormuz como activo económico permanente? | **CONFIRMADA** — Irán cobró primer peaje en yuan. Monetización activa. Minas: 6 meses para limpiar incluso con acuerdo. |
| H5 | Proyecto Abraham vaciándose de contenido estratégico | **SEÑAL MÁXIMA** — fractura OTAN documentada, España resistiendo, bloque atlántico sostenido. |
| H6 | ¿Vulnerabilidad compartida reemplaza valores como base del nuevo orden? | **CONFIRMACIÓN MÁXIMA** — BRICS activo, petrodólar bifurcado, China ganando 5 dimensiones, Papa como actor político global. |
| H7 | ¿Eje moral-religioso rompe base evangélica de Trump? | **CONFIRMADA** — Papa Leo activo desde África, cardenales americanos respaldan, conversos al catolicismo en máximos históricos EEUU. |

---

## Nodos críticos

| ID | Descripción | Fecha | Estado |
|----|-------------|-------|--------|
| N1 | Ultimátum Trump 7 abril | 2026-04-07 | ✅ RESUELTO — TACO |
| N2 | Reunión Rutte-Trump | 2026-04-08 | ✅ RESUELTO — OTAN no mordió |
| N10 | Ceasefire | INDEFINIDO | 🟡 MUTADO — sin deadline fijo. Condicionado a "propuesta unificada" iraní. |
| N11 | Líbano / Hezbollah | 24-abr | 🟡 ESTABILIZADO — extensión 3 semanas. Casco azul ONU muerto (6to total). |
| N12 | China / Escollo Scarborough | ACTIVO | 🔴 CONFRONTACIÓN — China operando en dos teatros |
| N13 | War Powers Day 60 | **2026-04-29** | 🔴 RELOJ DURO — 5 días. **CORRECCIÓN: es 29 abril, no 28.** |
| N14 | Hutíes / Bab el-Mandeb | LATENTE | 🟠 PAUSA ESTRATÉGICA ACTIVA |
| N15 | IRGC represalia TOUSKA | EJECUTADA | ✅ CERRADO — 3 buques atacados 22 abril |
| N16 | Araghchi Islamabad-Muscat-Moscú | 24-25 ABRIL | 🔴 ACTIVO AHORA — decisivo para S06 |
| N17 | Brent umbral $110 | INMINENTE | 🔴 A $4 DEL UMBRAL — activa presión financiera privada |
| N18 | Minas Hormuz — 6 meses limpieza | ESTRUCTURAL | 🔴 REDEFINE ESCENARIO A — apertura lenta incluso con acuerdo |
| N19 | $TRUMP Gala Mar-a-Lago | 2026-04-25 | 🔴 CONFIRMADA — Trump asiste. Top 297 holders. |
| N20 | Demanda Sun vs WLFI | ACTIVA | 🔴 $1B federal — Zach Witkoff CEO |
| N21 | Nodo Witkoff — conflicto de interés | ESTRUCTURAL | 🔴 Padre negocia paz / Hijo bajo demanda federal |

---

## Vectores estructurales clave — Sesión 05

| Vector | Descripción | Peso |
|--------|-------------|------|
| V48 | Ceasefire de facto extendido 24h | ALTO |
| V50 | Brent cruza $100 — umbral V43 activado | ESTRUCTURAL |
| V53 | Ceasefire mutado: indefinido con condición | CRÍTICO |
| V55 | N15 ejecutado: IRGC atacó 3 buques 22 abril | ALTO |
| V57 | "Shoot and kill" — umbral escalada retórica | CRÍTICO |
| V58 | Minas Hormuz: 6 meses para limpiar | ESTRUCTURAL |
| V59 | Araghchi Islamabad → Muscat → Moscú | ALTO |
| V60 | Irán rechaza narrativa de fractura — H1 complicada | MUY ALTO |
| V61 | Israel Katz: "esperando luz verde de EEUU" | ALTO |
| V62 | Rusia ofreció custodiar uranio — Trump rechazó | MUY ALTO |
| V63 | Brent $106 — a $4 del umbral $110 | ESTRUCTURAL |
| V66 | Netanyahu: cáncer de próstata tratado durante la guerra | MUY ALTO |
| V73 | IRGC tiene la sartén por el mango — Al-Oraibi | MUY ALTO |
| V75 | Irán monetiza Hormuz: primer pago en yuan depositado | CRÍTICO |
| V76 | Kushner/Witkoff problema en negociación | MUY ALTO |
| V77 | Misiles: línea roja absoluta iraní — no negociable | ESTRUCTURAL |
| V83 | Pakistan: "alta probabilidad de avance" | CRÍTICO |
| V86 | Señal no verificada: Wikipedia junio 2026 (vigilancia S06) | NO VERIFICADA |
| V89 | 7 errores estratégicos EEUU documentados — Tier 1 | ESTRUCTURAL |
| V92 | Manifiesto Palantir — doctrina industrial-tecnológica | ESTRUCTURAL |
| V94 | Petrodólar en bifurcación silenciosa — no colapso | HISTÓRICO |
| V95 | Colapso marítimo: $5M por barco, sistema mutando | ESTRUCTURAL |
| V96 | Seguridad alimentaria: 45M en riesgo, nitrógeno crítico | ESTRUCTURAL |
| V97 | Papa Leo: actor político global — H7 confirmada | MUY ALTO |
| V98 | Inflación global FMI 4.4% — "Sombra de Guerra" | ESTRUCTURAL |
| V99 | Fractura IA militar: Anthropic vs Pentágono | ESTRUCTURAL |
| V100 | China gana 5 dimensiones simultáneas sin disparar | HISTÓRICO |
| V101 | Comunidad internacional: condena sin sanción | MEDIO |
| V102 | WLFI-Witkoff: conflicto de interés estructural | CRÍTICO |
| V103 | Enriquecimiento presidencial: $9.7B documentados | CRÍTICO |
| V104 | Respuesta global: preparación silenciosa en 5 vectores | HISTÓRICO |
| V105 | $TRUMP gala: acceso presidencial como commodity | CRÍTICO |
| V106 | Arquitectura completa: dos pirámides paralelas activas | ESTRUCTURAL |

---

## TRES RELOJES EN TENSIÓN — S05

*(Evolución desde los DOS RELOJES de S04)*

**Reloj MILITAR** → apunta a Escenario B
IRGC atacó buques, Hormuz paralizado (1 barco/12h),
minas sin localizar (6 meses limpieza), Netanyahu esperando
"luz verde", Ghalibaf anuncia "nuevas cartas en el campo."

**Reloj FINANCIERO** → apunta a Escenario A bajo presión
Brent $104-106 (a $4 del umbral $110), Goldman 10K empleos/mes,
OBBBA tax refund cancelado por petróleo, BoE advierte corrección,
IMF: "Economía en la Sombra de la Guerra."
PERO: Wall Street no envía señal fuerte aún — paradoja V91.

**Reloj DOMÉSTICO** (nuevo S05) → presión creciente
$TRUMP −96%, WLFI demanda $1B, CFTC investigando,
$9.7B enriquecimiento documentado, 36% apoyo a la guerra,
War Powers deadline 29 abril, Fitzpatrick (R-PA) primera grieta GOP,
emolumentos activos por asistentes extranjeros a la gala cripto.

**La pregunta del modelo para S06:**
¿Puede Araghchi volver de Islamabad con una propuesta que incluya
al IRGC, esquive los misiles, y le dé a Trump suficiente para
declarar victoria doméstica antes de que el reloj doméstico
(War Powers + cripto + mercados) lo obligue a actuar?

---

## Frase del modelo — Sesión 05

> *"En el intento de evitar que Irán desarrollara un arma de destrucción masiva, EE.UU. le entregó un arma de disrupción masiva, mientras China observaba, y el presidente del país agresor vendía acceso a su persona por $539,000 el cubierto — el mismo día en que su negociador de paz intentaba salvar el mundo en Islamabad."*

---

## Posiciones negociadoras — Cuadro maestro

| Tema | Posición EEUU | Posición Irán | Gap |
|---|---|---|---|
| Uranio enriquecido | Eliminar / sacar del país | Mover a tercero (Turquía) | ESTRECHO |
| Enriquecimiento futuro | Cero | Máx. 5 años pausa | MEDIO |
| Misiles balísticos | Limitar | **Línea roja absoluta** | TOTAL |
| Hormuz tolls | Eliminar | Levantar si sanciones off | CONDICIONAL |
| Sanciones | Alivio gradual por cumplimiento | Levantamiento total previo | AMPLIO |
| Bloqueo naval | Continuará hasta acuerdo | Debe levantarse antes | BLOQUEANTE |
| Expertos nucleares | No en la mesa inicialmente | Irrelevante sin misiles | N/A |

---

## Historial de sesiones

| Sesión | Fecha | Vectores | Convergencia | Escenario A | Estado |
|--------|-------|----------|--------------|-------------|--------|
| 01 | 2026-04-06 | 3 | 0.47 — INESTABLE | 0.50 | ✅ Completa |
| 02 parte 1 | 2026-04-06 | 17 | 0.75 — CONVERGIENDO | 0.64 | ✅ Completa |
| 02 parte 2 | 2026-04-06 | 24 (acum.) | 0.82 — CONV. FUERTE | 0.66 | ✅ Completa |
| 03 | 2026-04-08 | 36 (acum.) | 0.85 — CONVERGIENDO | 0.65 | ✅ Completa |
| 04 | 2026-04-19 | 50 (acum.) | 0.82 — CONVERGIENDO | 0.50 | ✅ Completa |
| 05 | 2026-04-24 | 106 (acum.) | 0.86 — CONVERGIENDO | 0.43 | ✅ Completa |
| 06 | ~2026-04-26 | — | — | — | 🔜 Post-Islamabad II |

---

## Roadmap

- [x] v0.1.0 — Arquitectura conceptual documentada
- [x] v0.1.4 — Sesiones 01 y 02 parte 1 completadas
- [x] v0.1.5 — Sesión 02 parte 2 — Consilience como arquitectura epistemológica
- [x] v0.1.6 — Sesión 03 — 14 vectores nuevos — corrección honesta al cierre
- [x] v0.1.7 — Sesión 04 — 14 vectores nuevos — dos relojes en tensión
- [x] v0.1.8 — Sesión 05 — 56 vectores nuevos — tres relojes + nodo cripto
- [ ] v0.2.0 — Pipeline de scraping automatizado
- [ ] v0.3.0 — Motor bayesiano implementado en código
- [ ] v1.0.0 — Sistema operativo completo

---

## Referencia metodológica principal

Pearl, J. & Mackenzie, D. (2018). *The Book of Why: The New Science of Cause and Effect*. Basic Books.

---

*Proyecto iniciado el 6 de abril de 2026. Operado mediante dialéctica humano-IA.*
*Operador: docente colombiano. Trayectoria analítica: 6.5 → 9.0 en 5 sesiones.*
