# Iran Conflict Model (ICM)
> Sistema de análisis de conflictos mediante inferencia causal y fuentes abiertas

**Versión:** v0.2.0
**Fecha de inicio:** 2026-04-06
**Última sesión:** Sesión 08 — 2026-04-30
**Próxima sesión:** Sesión 09 — 4-5 mayo 2026 (post-May Day / China CSONU activo)
**Estado:** OPERATIVO — CONVERGIENDO (señal 0.87 ↑)
**Metodología base:** Inferencia causal (Judea Pearl, *The Book of Why*, 2018)

---

## ⚠️ NOTA PRIORITARIA PARA S09

> **Agregar factor Cuba al análisis.**
> Cuba fue mencionada en las amenazas de la Doctrina Donroe (enero 2026) pero no ha sido operada como nodo independiente. Con el contexto de V141 (Doctrina Donroe + Ecuador + Colombia) y la dinámica hemisférica activa, Cuba requiere incorporación formal en S09.

---

## Estado del modelo

| Campo | Valor |
|-------|-------|
| Sesiones completadas | 8 (incluye S07 emergencia) |
| Última sesión | Sesión 08 — 2026-04-30 (~13 horas) |
| Vectores procesados (acumulado) | 142 |
| Señal de convergencia | 0.87 — CONVERGIENDO (↑ desde 0.84) |
| Escenario dominante | F y A — co-dominancia / F ligeramente superior |
| Probabilidad Escenario F (30 días) | 0.34 ↑ |
| Probabilidad Escenario A (30 días) | 0.30 ↑↑ |
| Día del conflicto | D62 (30 abril 2026) |
| Escenarios activos | 6 (A, B, C, D, E, F) |
| Nodos críticos activos | N13, N17, N22, N23, N25, N_China_CSONU, N_Colombia |

### Probabilidades S08 — Horizonte 30 días

| Escenario | Descripción | S07 | S08 | Δ |
|-----------|-------------|-----|-----|---|
| A | Acuerdo + proceso apertura Hormuz (6 meses minas) | 0.27 | **0.30** | ↑↑ |
| B | Limbo prolongado — guerra de resistencia | 0.26 | **0.21** | ↓↓ |
| C | Escalada — ataque infraestructura crítica | 0.08 | **0.09** | ↑ |
| D | Colapso régimen iraní | 0.04 | **0.04** | → |
| E | Wildcard operacional (Hutíes) | 0.02 | **0.02** | → |
| **F** | **Recule no declarado / deescalada sin acuerdo** | **0.33** | **0.34** | **↑** |

**Nota S08:** B baja significativamente por activación de China en CSONU y frente internacional coordinado. A sube por construcción de arquitectura diplomática disponible. C vigilado por Netanyahu en DC esta semana.

### Scores de convergencia

| Score | S07 cierre | S08 cierre | Δ |
|-------|------------|------------|---|
| Narrativas | 0.93 | **0.94** | ↑ |
| Factual | 0.95 | **0.96** | ↑ |
| Ruido | 0.55 | **0.57** | ↑ |
| Escenarios | 0.77 | **0.80** | ↑ |
| **Convergencia global** | **0.84** | **0.87** | ↑ |

**Nota:** Sube por deuda metodológica S07 saldada (Bloque 2 ANCHOR completado) + 14 vectores nuevos verificados en Tier 1/2.

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

### Notas E5 — Sesión 08

**Brent al cierre S08 (17:42 COT):** $120+ — N17 ACTIVADO. Umbral recesión Goldman: $140 — a $20 de distancia.

**Insider trading sistémico (V126):** $2.72B en 4 trades verificados, 15-20 minutos antes de cada anuncio presidencial. CFTC investigando. Quinto trade no verificado.

**Implosión cripto Trump (V140):** $TRUMP -95%, WLFI -74%, colateral $75M en riesgo de liquidación. WLF "al borde del colapso" (Sun demanda). Binance: $1.7B hacia proxies iraníes investigado.

**May Day 1° mayo:** Mercados europeos/asiáticos cerrados. Liquidez reducida = volatilidad amplificada. Brent único termómetro disponible del día.

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
| H1 | ¿Puede Pezeshkian firmar acuerdo sin aval IRGC? | **DEBILITADA** |
| H2 | ¿Canal Pakistan es negociación real? | **CERRADA NEGATIVAMENTE** — Islamabad II colapsó |
| H3 | ¿Netanyahu tiene incentivo para sabotear el ceasefire? | **CONFIRMADA +** — viaje DC esta semana |
| H4 | ¿Hormuz como activo económico permanente? | **CONFIRMADA MÁXIMA** — Brent $120+ |
| H5 | Proyecto Abraham vaciándose de contenido estratégico | **SEÑAL MÁXIMA** |
| H6 | ¿Vulnerabilidad compartida reemplaza valores como base del nuevo orden? | **CONFIRMACIÓN MÁXIMA** |
| H7 | ¿Eje moral-religioso rompe base evangélica de Trump? | **CONFIRMADA** — Papa Leo "off-ramp" |
| H8 | ¿Doctrina Palantir produce guerra que no puede ganar? | **ACTIVA** — F-15E derribado, Ford fatigado |
| H9 | La salida del conflicto no será un acuerdo sino un recule no declarado | **CO-DOMINANTE** |
| H10 | ¿WHCD = cortina de humo sistémica funcional? | **PROVISIONAL +** — instrumentalizado por Casa Blanca |
| H11 | ¿Arquitectura monetización info presidencial clasificada? | **GANANDO PESO** — WLF-Binance-Irán documentado |
| H12 | ¿Patrón ataque simbólico sistémico por élite educada? | **PROVISIONAL +** — manifiesto Allen confirmado |

---

## Nodos críticos

| ID | Descripción | Fecha | Estado |
|----|-------------|-------|--------|
| N1 | Ultimátum Trump 7 abril | 2026-04-07 | ✅ RESUELTO |
| N2 | Reunión Rutte-Trump | 2026-04-08 | ✅ RESUELTO |
| N10 | Ceasefire mutado | INDEFINIDO | 🟡 Vigente nominalmente |
| N11 | Líbano / Hezbollah | ACTIVO | 🔴 TREGUA ROTA — 28-32 muertos hoy |
| N12 | China / Escollo Scarborough | ACTIVO | 🔴 CONFRONTACIÓN ACTIVA (validado S08) |
| N13 | War Powers Day 60-61 | **VENCIDO** | 🔴 EN ZONA GRIS LEGAL |
| N14 | Hutíes / Bab el-Mandeb | LATENTE | 🟠 PAUSA ESTRATÉGICA |
| N15 | IRGC represalia TOUSKA | EJECUTADA | ✅ CERRADO |
| N16 | Islamabad II | COLAPSADO | 🔴 CERRADO NEGATIVAMENTE |
| N17 | Brent umbral $110/$120 | **ACTIVADO** | 🔴 $120+ — 17:42 COT 30 abr |
| N18 | Minas Hormuz — 6 meses limpieza | ESTRUCTURAL | 🔴 REDEFINE ESCENARIO A |
| N19 | $TRUMP Gala Mar-a-Lago | 2026-04-25 | ✅ EJECUTADA |
| N20 | Demanda Sun vs WLFI | ACTIVA | 🔴 Litigio federal activo |
| N21 | Nodo Witkoff — conflicto de interés | ESTRUCTURAL | 🔴 PUNTO MÁXIMO |
| N22 | War Powers D60-90 | ACTIVO | 🔴 EN ZONA GRIS — D61 mañana |
| N23 | Cumbre Xi-Trump | MAYO 2026 | 🔴 ABIERTO — China construye capital |
| N24 | Reunión China-Rusia-Irán-IAEA | 2026-04-24 | ✅ EJECUTADO |
| N25 | WHCD Shooting | 2026-04-25 | 🟡 INSTRUMENTALIZADO por Casa Blanca |
| **N_NUEVO** | **China CSONU** | **1° MAYO** | 🔴 **ACTIVO DESDE MAÑANA** |
| **N_NUEVO** | **Colombia elecciones** | **31 MAYO** | 🔴 **ACTIVO — Cepeda 44.3%** |
| **N_NUEVO** | **Brent $120+** | **30 ABR 17:42** | 🔴 **ACTIVADO — $20 del umbral Goldman** |

---

## ESCENARIO F — DEFINICIÓN FORMAL (vigente)

**Escenario F — Recule No Declarado / Deescalada Sin Acuerdo**

Secuencia de pasos atrás graduales, no coordinados, donde ningún actor declara victoria ni derrota. El conflicto se congela en un limbo gestionado.

**Señal de verificación clave:** Cuando el tráfico de Hormuz supere 8 barcos diarios sin anuncio formal iraní de apertura.

**Andamiaje disponible para F en S08:**
- China CSONU construye marco jurídico en mayo
- Victory Day 9 mayo = cobertura narrativa para Trump
- Papa Leo XIV ofreció "off-ramp" nominando a Trump directamente
- Europa dispuesta a desplegar en post-guerra (no en guerra)
- 3 barcos iraníes en custodia = palanca concreta disponible

**Quién gana en F:**
- 🟢 Irán — sobrevive, conserva IRGC, Hormuz como activo, yuan activo
- 🟢 China — consolida de-dolarización, capital para cumbre mayo
- 🟢 Palantir/OCP — contratos renovados, más integrado
- 🟡 EE.UU. Estado — evita escalada, narrativa de "victoria" parcial
- 🔴 EE.UU. ciudadanos — $50B+ real, gasolina $8 en LA, dólar débil
- 🔴 OTAN — fractura consolidada

---

## CUATRO RELOJES EN TENSIÓN — S08

**Reloj DIPLOMÁTICO** → 12:17 — CRUZÓ MEDIANOCHE
Trump tiene 3-4 semanas antes de que recular sea inevitable.
Victory Day 9 mayo + cumbre Xi = ventana para F.

**Reloj FINANCIERO** → PUNTO CRÍTICO
Brent $120 — a $20 del umbral recesión Goldman ($140).
$1B/día de costo real. Ford fatigado. Gasolina $8/galón en LA.

**Reloj DOMÉSTICO** → ZONA CRÍTICA MÁXIMA
War Powers vencido. Hegseth mintió bajo juramento. Cripto colapsa.
May Day mañana. GOP con fisuras documentadas con nombre propio.

**Reloj IRANÍ INTERNO** → ACELERADO
47.5% inflación. Protestas. Economía en colapso.
Ventana resistencia <2 meses. Ghalibaf desafía públicamente.
Paradoja: más frágil = más rígido en negociación.

---

## VECTORES ESTRUCTURALES CLAVE — S08

| Vector | Descripción | Peso |
|--------|-------------|------|
| V129 | Trump-Putin "timetable similar" + Putin advierte no reanudar ataques | CRÍTICO |
| V130 | Hegseth 6h Congreso — mentira bajo juramento — fisuras GOP | ESTRUCTURAL |
| V134 | China CSONU desde 1° mayo — Fu Cong presidente | CRÍTICO |
| V138 | Costo real guerra $50B — Hegseth mintió al Congreso | ESTRUCTURAL |
| V139 | Frente internacional coordinado no declarado | ESTRUCTURAL |
| V140 | Implosión cripto Trump — Eric Trump borrado Alt5 HOY | ESTRUCTURAL |
| V141 | Doctrina Donroe + Ecuador operaciones + Colombia presión | REGIONAL |
| V142 | Colombia elecciones: Cepeda 44.3% — CSONU junio | ESTRATÉGICO |

*(Vectores V125-V128 documentados en CHANGELOG v0.2.0)*
*(Vectores anteriores V107-V124 documentados en CHANGELOG v0.1.9)*
*(Vectores V48-V106 documentados en CHANGELOG v0.1.8)*

---

## FRASES DEL MODELO — REGISTRO HISTÓRICO

**S05:** *"En el intento de evitar que Irán desarrollara un arma de destrucción masiva, EE.UU. le entregó un arma de disrupción masiva, mientras China observaba, y el presidente del país agresor vendía acceso a su persona por $539,000 el cubierto — el mismo día en que su negociador de paz intentaba salvar el mundo en Islamabad."*

**S06:** *"Islamabad II terminó como empezó: con Araghchi en un avión y los americanos llegando a una ciudad vacía. El rey juega al showman en Mar-a-Lago vendiendo tokens que valen 4 centavos por dólar invertido, mientras su negociador aterriza en Pakistan sin audiencia y China observa en silencio calculando cuánto capital político acumula antes de la cumbre de mayo."*

**S07:** *"El rey sobrevivió. El tirador era un maestro de Caltech con una maestría en ciencias de la computación — exactamente el perfil que el manifiesto de Palantir llama a 'obligación afirmativa' con el aparato de defensa. Cuando un sistema produce las contradicciones que lo atacan, cuando sus propios mecanismos de control se convierten en canales de monetización, cuando sus mejores instituciones forman a quienes luego lo cuestionan con armas — ese sistema no está siendo atacado desde afuera. Está colapsando desde adentro."*

**S08:** *"China no necesita ganar la guerra de Irán. Solo necesita ser el actor que la termina. Eso vale más que cualquier victoria militar — y cuesta menos que un portaaviones. Trump tiene dos relojes: el diplomático marca 3-4 semanas para recular, el político marca 4-6 meses de margen. Si los sincroniza bien, sobrevive. Si no, los dos cruzan medianoche juntos. La Torre de Babel no colapsa porque la ataquen desde afuera. Colapsa porque los constructores ya no hablan el mismo idioma. Y Colombia — la provincia que tiene un asiento en el Consejo de Seguridad en junio — no es espectadora de nada de esto. Nunca lo fue."*

---

## Historial de sesiones

| Sesión | Fecha | Tipo | Vectores | Conv. | Dom. | Estado |
|--------|-------|------|----------|-------|------|--------|
| 01 | 2026-04-06 | Regular | 3 | 0.47 | A: 0.50 | ✅ |
| 02 p1 | 2026-04-06 | Regular | 17 | 0.75 | A: 0.64 | ✅ |
| 02 p2 | 2026-04-06 | Regular | 24 | 0.82 | A: 0.66 | ✅ |
| 03 | 2026-04-08 | Regular | 36 | 0.85 | A: 0.65 | ✅ |
| 04 | 2026-04-19 | Regular | 50 | 0.82 | A: 0.50 | ✅ |
| 05 | 2026-04-24 | Regular | 106 | 0.86 | A: 0.43 | ✅ |
| 06 | 2026-04-25 | Regular | 124 | 0.86 | F/A: 0.30/0.31 | ✅ |
| 07 | 2026-04-25 | EMERGENCIA | 128 | 0.84 | F: 0.33 | ✅ |
| **08** | **2026-04-30** | **Regular** | **142** | **0.87** | **F/A: 0.34/0.30** | **✅** |
| 09 | 2026-05-04/05 | — | — | — | — | 🔜 |

---

## Control de sesgos — Protocolo ANCHOR

El ICM opera con el Protocolo ANCHOR v2.0 desde S07.

**Advertencia permanente del sistema:**
Las probabilidades son juicios cualitativos con forma numérica.
La convergencia es una metáfora cuantificada, no una medición.
La utilidad del ICM es real. Su certeza no lo es.

**Estado S08:** Bloque 2 completado. Deuda metodológica S07 saldada.
Sesgo operador declarado: (a) quiere resolución del conflicto.
Contrapeso activo: desafiar señales de desescalada antes de integrarlas.

---

## Roadmap

- [x] v0.1.0 — Arquitectura conceptual documentada
- [x] v0.1.4 — Sesiones 01 y 02 parte 1 completadas
- [x] v0.1.5 — Sesión 02 parte 2 — Consilience como arquitectura epistemológica
- [x] v0.1.6 — Sesión 03 — 14 vectores nuevos
- [x] v0.1.7 — Sesión 04 — 14 vectores nuevos — dos relojes en tensión
- [x] v0.1.8 — Sesión 05 — 56 vectores nuevos — tres relojes + nodo cripto
- [x] v0.1.9 — Sesión 06 — 18 vectores nuevos — seis escenarios + Escenario F
- [x] **v0.2.0 — Sesión 07 EMERGENCIA — 4 vectores + 3 hipótesis provisionales + WHCD**
- [x] **v0.2.0 — Sesión 08 — 14 vectores + Colombia nodo activo + Brent $120 + China CSONU**
- [ ] v0.3.0 — Motor bayesiano implementado en código
- [ ] v0.3.0 — Factor Cuba incorporado como nodo independiente
- [ ] v0.3.0 — Múltiples operadores para reducción de sesgo
- [ ] v1.0.0 — Sistema operativo completo

---

## Referencia metodológica principal

Pearl, J. & Mackenzie, D. (2018). *The Book of Why: The New Science of Cause and Effect*. Basic Books.

---

*Proyecto iniciado el 6 de abril de 2026. Operado mediante dialéctica humano-IA.*
*Operador: docente colombiano, Medellín.*
*S08: sesión más larga del ICM — ~13 horas | 142 vectores | 60 fuentes | Convergencia 0.87*
