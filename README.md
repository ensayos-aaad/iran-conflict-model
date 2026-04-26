# Iran Conflict Model (ICM)
> Sistema de análisis de conflictos mediante inferencia causal y fuentes abiertas

**Versión:** v0.2.0
**Fecha de inicio:** 2026-04-06
**Última sesión:** Sesión 07 — EMERGENCIA — 2026-04-25
**Próxima sesión:** Sesión 08 — 29 abril / 1 mayo 2026 (War Powers D60 + May Day)
**Estado:** OPERATIVO — CONVERGIENDO (señal 0.84)
**Metodología base:** Inferencia causal (Judea Pearl, *The Book of Why*, 2018)

---

## Estado del modelo

| Campo | Valor |
|-------|-------|
| Sesiones completadas | 7 (incluye S07 emergencia) |
| Última sesión | Sesión 07 EMERGENCIA — 2026-04-25 |
| Vectores procesados (acumulado) | 128 |
| Señal de convergencia | 0.84 — CONVERGIENDO (↓ desde 0.86) |
| Escenario dominante | F y A — co-dominancia / F ligeramente superior |
| Probabilidad Escenario F (30 días) | 0.33 ↑ |
| Probabilidad Escenario A (30 días) | 0.27 ↓ |
| Día del conflicto | ~57 |
| Escenarios activos | 6 (A, B, C, D, E, F) |
| Nodos críticos activos | N13, N17, N22, N23, N25 |

### Probabilidades S07 — Horizonte 30 días

| Escenario | Descripción | S06 | S07 | Δ |
|-----------|-------------|-----|-----|---|
| A | Acuerdo + proceso apertura Hormuz (6 meses minas) | 0.31 | **0.27** | ↓↓ |
| B | Limbo prolongado — guerra de resistencia | 0.24 | **0.26** | ↑ |
| C | Escalada — ataque infraestructura crítica | 0.09 | **0.08** | ↓ |
| D | Colapso régimen iraní | 0.04 | **0.04** | → |
| E | Wildcard operacional (Hutíes) | 0.02 | **0.02** | → |
| **F** | **Recule no declarado / deescalada sin acuerdo** | **0.30** | **0.33** | **↑↑** |

**Nota S07:** El atentado WHCD sin atribución iraní fortalece F paradójicamente. Trump con capital político máximo post-atentado tiene más margen para concesiones sin aparentar debilidad.

### Scores de convergencia

| Score | S06 cierre | S07 cierre | Δ |
|-------|------------|------------|---|
| Narrativas | 0.95 | **0.93** | ↓ |
| Factual | 0.97 | **0.95** | ↓ |
| Ruido | 0.52 | **0.55** | ↑ |
| Escenarios | 0.79 | **0.77** | ↓ |
| **Convergencia global** | **0.86** | **0.84** | ↓ |

**Nota:** Baja leve por sesión de emergencia sin Bloque 2 del operador completado y apertura de 3 hipótesis provisionales.

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

### Notas E5 — Sesión 07

**Brent al cierre S07:** $105.33 — a $5 del umbral $110. Proyección apertura Asia lunes: $108-112. Quinto trade (V126) como señal crítica a verificar.

**Insider trading sistémico (V126):** $2.72B en 4 trades verificados, 15-20 minutos antes de cada anuncio presidencial. CFTC investigando. Van Dyke (V127) prueba el mecanismo.

**No Kings / May Day:** 8 millones el 28 marzo. Huelga general 1° mayo — coincide con War Powers deadline.

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
| H2 | ¿Canal Pakistan es negociación real? | **CONFIRMADA MÁXIMA** — colapsó en práctica S07 |
| H3 | ¿Netanyahu tiene incentivo para sabotear el ceasefire? | **CONFIRMADA** |
| H4 | ¿Hormuz como activo económico permanente? | **CONFIRMADA MÁXIMA** |
| H5 | Proyecto Abraham vaciándose de contenido estratégico | **SEÑAL MÁXIMA** |
| H6 | ¿Vulnerabilidad compartida reemplaza valores como base del nuevo orden? | **CONFIRMACIÓN MÁXIMA** |
| H7 | ¿Eje moral-religioso rompe base evangélica de Trump? | **CONFIRMADA** — Papa Leo en WHCD |
| H8 | ¿Doctrina Palantir produce guerra que no puede ganar? | **ACTIVA** — OCP avanza sin audiencias |
| H9 | La salida del conflicto no será un acuerdo sino un recule no declarado | **ACTIVA — GANANDO PESO** |
| H10 | ¿WHCD = cortina de humo sistémica funcional? | **PROVISIONAL S07** |
| H11 | ¿Arquitectura monetización info presidencial clasificada? | **PROVISIONAL S07** |
| H12 | ¿Patrón ataque simbólico sistémico por élite educada? | **PROVISIONAL S07** |

---

## Nodos críticos

| ID | Descripción | Fecha | Estado |
|----|-------------|-------|--------|
| N1 | Ultimátum Trump 7 abril | 2026-04-07 | ✅ RESUELTO |
| N2 | Reunión Rutte-Trump | 2026-04-08 | ✅ RESUELTO |
| N10 | Ceasefire mutado | INDEFINIDO | 🟡 Vigente técnicamente |
| N11 | Líbano / Hezbollah | 24 abr | 🟡 EXTENSIÓN 3 SEMANAS |
| N12 | China / Escollo Scarborough | ACTIVO | 🔴 CONFRONTACIÓN ACTIVA |
| N13 | War Powers Day 60 | **2026-04-29** | 🔴 ESTA SEMANA |
| N14 | Hutíes / Bab el-Mandeb | LATENTE | 🟠 PAUSA ESTRATÉGICA |
| N15 | IRGC represalia TOUSKA | EJECUTADA | ✅ CERRADO |
| N16 | Islamabad II | 25-27 ABR | 🔴 COLAPSADO — Araghchi salió. Sin acuerdo. |
| N17 | Brent umbral $110 | INMINENTE | 🔴 A $5 DEL UMBRAL |
| N18 | Minas Hormuz — 6 meses limpieza | ESTRUCTURAL | 🔴 REDEFINE ESCENARIO A |
| N19 | $TRUMP Gala Mar-a-Lago | 2026-04-25 | ✅ EJECUTADA — Sin incidentes |
| N20 | Demanda Sun vs WLFI | ACTIVA | 🔴 Litigio federal en curso |
| N21 | Nodo Witkoff — conflicto de interés | ESTRUCTURAL | 🔴 PUNTO MÁXIMO |
| N22 | War Powers D60-90 | 29 ABR → 29 MAY | 🔴 ACTIVO |
| N23 | Cumbre Xi-Trump | MAYO 2026 | 🔴 ABIERTO — nodo más importante no operado |
| N24 | Reunión China-Rusia-Irán-IAEA | 2026-04-24 | ✅ EJECUTADO |
| **N25** | **WHCD Shooting** | **2026-04-25** | **🟡 PARCIALMENTE RESUELTO** |

---

## ESCENARIO F — DEFINICIÓN FORMAL

**Escenario F — Recule No Declarado / Deescalada Sin Acuerdo**

Secuencia de pasos atrás graduales, no coordinados, donde ningún actor declara victoria ni derrota. El conflicto se congela en un limbo gestionado. Todos los actores lo sostienen porque el costo de nombrarlo supera el costo de administrarlo.

**Señal de verificación clave:** Cuando el tráfico de Hormuz supere 8 barcos diarios sin anuncio formal iraní de apertura.

**Quién gana en F:**
- 🟢 Irán — sobrevive, conserva IRGC, Hormuz como activo, yuan activo
- 🟢 China — consolida de-dolarización, capital para cumbre mayo
- 🟢 Palantir/OCP — contratos renovados, más integrado
- 🟡 EE.UU. Estado — evita escalada, narrativa de "victoria" parcial
- 🔴 EE.UU. ciudadanos — $100B+, gasolina cara, dólar débil
- 🔴 OTAN — fractura consolidada

---

## Vectores estructurales clave — S07

| Vector | Descripción | Peso |
|--------|-------------|------|
| V125 | WHCD Shooting — tirador doméstico, Trump ileso, no atribución iraní | CRÍTICO |
| V126 | Insider trading $2.72B / 4 trades / 4/4 — CFTC activo | ESTRUCTURAL |
| V127 | Arquitectura Signalgate→VanDyke→Futuros — canal sistémico verificado | HISTÓRICO |
| V128 | Erosión marca EEUU desde adentro — cuatro pilares simultáneamente degradados | HISTÓRICO |

*(Vectores anteriores V107-V124 documentados en CHANGELOG v0.1.9)*

---

## CUATRO RELOJES EN TENSIÓN — S07

**Reloj MILITAR** → apunta a B/F
Sin cambio estructural. Hormuz cerrado. Fatiga logística activa. Ghalibaf "cartas" sin activar. China: sus barcos siguen pasando.

**Reloj FINANCIERO** → apunta a F
Brent $105.33 — a $5 del umbral crítico. Proyección lunes $108-112. Goldman: si Hormuz sigue cerrado un mes más → $120 Q3. Insider trading $2.72B patrón activo.

**Reloj DOMÉSTICO** → PUNTO CRÍTICO MÁXIMO
War Powers D60 martes 29 / legal 1° mayo. No Kings viernes — huelga general. WHCD shooting congela debate legislativo pero no desaparece la presión. La pinza del 1° mayo es la variable más cargada de la semana.

**Reloj IRANÍ INTERNO** → el más silencioso / el más decisivo
47.5% inflación. 36,000 muertos protestas enero. Economía en colapso. Ventana de resistencia 2-3 meses. Araghchi regresa a Teherán sin acuerdo. El reloj sigue.

---

## Cuadro maestro de posiciones negociadoras

| Tema | Posición EE.UU. | Posición Irán | Gap | Δ S07 |
|---|---|---|---|---|
| Uranio enriquecido | Eliminar / sacar del país | Mover a tercero (Turquía) | ESTRECHO | → |
| Enriquecimiento futuro | Cero | Máx. 5 años pausa | MEDIO | → |
| Misiles balísticos | Limitar | **LÍNEA ROJA ABSOLUTA** | TOTAL | → |
| Hormuz tolls | Eliminar | Levantar si sanciones off | CONDICIONAL | → |
| Sanciones | Alivio gradual | Levantamiento total previo | AMPLIO | → |
| Bloqueo naval | Continuará hasta acuerdo | Levantar antes de negociar | BLOQUEANTE | → |
| Posición nuclear | Bilateral EE.UU.-Irán | Con China+Rusia como garantes | NUEVO S06 | → |

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
| **07** | **2026-04-25** | **EMERGENCIA** | **128** | **0.84** | **F: 0.33** | **✅** |
| 08 | 2026-04-29/30 | — | — | — | — | 🔜 |

---

## Frases del modelo — registro histórico

**S05:** *"En el intento de evitar que Irán desarrollara un arma de destrucción masiva, EE.UU. le entregó un arma de disrupción masiva, mientras China observaba, y el presidente del país agresor vendía acceso a su persona por $539,000 el cubierto — el mismo día en que su negociador de paz intentaba salvar el mundo en Islamabad."*

**S06:** *"Islamabad II terminó como empezó: con Araghchi en un avión y los americanos llegando a una ciudad vacía. El rey juega al showman en Mar-a-Lago vendiendo tokens que valen 4 centavos por dólar invertido, mientras su negociador aterriza en Pakistan sin audiencia y China observa en silencio calculando cuánto capital político acumula antes de la cumbre de mayo. El Escenario F no es el escenario del ganador. Es el escenario de los dos exhaustos — uno que no puede sostener el bloqueo, y otro que no puede sostener la economía — negociando a través de un intermediario que es el único que gana en cualquier resultado."*

**S07:** *"El rey sobrevivió. El tirador era un maestro de Caltech con una maestría en ciencias de la computación — exactamente el perfil que el manifiesto de Palantir llama a 'obligación afirmativa' con el aparato de defensa. El movimiento que se llama 'No Kings' tiene 8 millones de personas y llega al mismo día que la ley constitucional que debería limitar al rey. Alguien apostó $2.72 billion cuatro veces en 15 minutos antes de que el rey hablara, y acertó las cuatro. Cuando un sistema produce las contradicciones que lo atacan, cuando sus propios mecanismos de control se convierten en canales de monetización, cuando sus mejores instituciones forman a quienes luego lo cuestionan con armas — ese sistema no está siendo atacado desde afuera. Está colapsando desde adentro."*

---

## Control de sesgos — Protocolo ANCHOR

El ICM opera con el Protocolo ANCHOR v2.0 desde S07.

**Lo que el protocolo hace:** Obliga a nombrar las limitaciones del sistema antes de operar. No mide nada. No certifica rigor. No elimina sesgos.

**Lo que el protocolo no hace:** No convierte las probabilidades en mediciones reales. No garantiza independencia del operador. No resuelve que el modelo de cada sesión es una instancia nueva sin memoria genuina.

**Advertencia permanente del sistema:**
Las probabilidades son juicios cualitativos con forma numérica.
La convergencia es una metáfora cuantificada, no una medición.
La utilidad del ICM es real. Su certeza no lo es.

**Anomalía S07:** Bloque 2 del operador no completado. ISIO implícito elevado. La sesión operó sin contrapeso humano verificado durante ~5 horas. S08 debe saldar esta deuda metodológica.

---

## Roadmap

- [x] v0.1.0 — Arquitectura conceptual documentada
- [x] v0.1.4 — Sesiones 01 y 02 parte 1 completadas
- [x] v0.1.5 — Sesión 02 parte 2 — Consilience como arquitectura epistemológica
- [x] v0.1.6 — Sesión 03 — 14 vectores nuevos — corrección honesta al cierre
- [x] v0.1.7 — Sesión 04 — 14 vectores nuevos — dos relojes en tensión
- [x] v0.1.8 — Sesión 05 — 56 vectores nuevos — tres relojes + nodo cripto
- [x] v0.1.9 — Sesión 06 — 18 vectores nuevos — seis escenarios + Escenario F + cuatro relojes
- [x] **v0.2.0 — Sesión 07 EMERGENCIA — 4 vectores sistémicos + 3 hipótesis provisionales + WHCD shooting**
- [ ] v0.3.0 — Motor bayesiano implementado en código
- [ ] v1.0.0 — Sistema operativo completo

---

## Referencia metodológica principal

Pearl, J. & Mackenzie, D. (2018). *The Book of Why: The New Science of Cause and Effect*. Basic Books.

---

*Proyecto iniciado el 6 de abril de 2026. Operado mediante dialéctica humano-IA.*
*Operador: docente colombiano.*
