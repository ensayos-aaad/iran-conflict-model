# Iran Conflict Model (ICM)
> Sistema de análisis de conflictos mediante inferencia causal y fuentes abiertas

**Versión:** v0.1.9
**Fecha de inicio:** 2026-04-06
**Última sesión:** Sesión 06 — 2026-04-25
**Próxima sesión:** Sesión 07 — 29-30 abril 2026 (contingente: 29 si hay movimiento War Powers)
**Estado:** OPERATIVO — CONVERGIENDO (señal 0.86)
**Metodología base:** Inferencia causal (Judea Pearl, *The Book of Why*, 2018)

---

## Estado del modelo

| Campo | Valor |
|-------|-------|
| Sesiones completadas | 6 |
| Última sesión | Sesión 06 — 2026-04-25 |
| Vectores procesados (acumulado) | 124 |
| Señal de convergencia | 0.86 — CONVERGIENDO |
| Escenario dominante | F y A en empate técnico — máxima dispersión |
| Probabilidad Escenario A (30 días) | 0.31 |
| Probabilidad Escenario F (30 días) | 0.30 |
| Día del conflicto | ~56 |
| Escenarios activos | 6 (A, B, C, D, E, F) |
| Nodos críticos activos | N13, N16, N17, N22, N23 |

### Probabilidades S06 — Horizonte 30 días

| Escenario | Descripción | Probabilidad |
|-----------|-------------|-------------|
| A | Acuerdo + proceso apertura Hormuz (6 meses minas) | **0.31** |
| B | Limbo prolongado — guerra de resistencia | **0.24** |
| C | Escalada — ataque infraestructura crítica | 0.09 |
| D | Colapso régimen iraní | 0.04 |
| E | Wildcard operacional (Hutíes) | 0.02 |
| **F** | **Recule no declarado / deescalada sin acuerdo** | **0.30** ← NUEVO S06 |

**Nota metodológica S06:** Primera vez en la historia del ICM que ningún escenario supera 0.31. El modelo ha alcanzado su punto de máxima dispersión epistémica. F y A co-dominantes. El dato resolutivo es el resultado de Islamabad II este fin de semana + War Powers deadline 29 abril.

### Scores de convergencia

| Score | S05 cierre | S06 cierre | Δ |
|-------|------------|------------|---|
| Narrativas | 0.93 | 0.95 | ↑↑ |
| Factual | 0.97 | 0.97 | → |
| Ruido | 0.47 | 0.52 | ↑↑ máximo histórico |
| Escenarios | 0.80 | 0.79 | ↓ |
| **Convergencia global** | **0.86** | **0.86** | → |

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

### Notas E5 — Sesión 06

**Brent al cierre S06:** $105.33 — a $5 del umbral $110. EIA proyecta pico $115 Q2 2026. Backwardation spot-futuros $25+ — escasez extrema documentada. Umbral recesión Goldman: $140.

**Cripto:** $TRUMP a ~$2.98 (−96% desde ATH $74.27 — corrección S06). WLFI bajo demanda criminal Justin Sun. Patrón pump-dump documentado: +50% anuncio / −16% post-evento.

**Doble reloj documentado:** EE.UU. bajo presión en semanas (War Powers + logística). Irán bajo presión en 2-3 meses (almacenamiento petróleo). El que vence primero cede primero.

### Notas E3 — Innovación metodológica S06

S06 incorporó análisis comparativo narrativo-estructural como metodología nueva: Torre de Babel (arquitectura de incoherencia), RoboCop/OCP (modelo de negocio de la guerra), Pirámide Madoff (ecosistema cripto-presidencial). Los tres marcos produjeron vectores con peso HISTÓRICO que enriquecen el motor de inferencia más allá del análisis factual puro.

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
| H1 | ¿Puede Pezeshkian firmar acuerdo sin aval IRGC? | **DEBILITADA** — IRGC tiene control operacional real. |
| H2 | ¿Canal Pakistan es negociación real? | **CONFIRMADA MÁXIMA** — "Proceso de Islamabad" institucionalizado. Lista de demandas entregada S06. |
| H3 | ¿Netanyahu tiene incentivo para sabotear el ceasefire? | **CONFIRMADA** — Israel Katz: "esperando luz verde." Netanyahu con cáncer tratado durante la guerra. |
| H4 | ¿Hormuz como activo económico permanente? | **CONFIRMADA MÁXIMA** — Doble cerrojo. Minas 6 meses. Yuan activo. Peaje monetizado. |
| H5 | Proyecto Abraham vaciándose de contenido estratégico | **SEÑAL MÁXIMA** — Fractura OTAN documentada, España resistiendo. |
| H6 | ¿Vulnerabilidad compartida reemplaza valores como base del nuevo orden? | **CONFIRMACIÓN MÁXIMA** — BRICS activo, petrodólar bifurcado, China 5 dimensiones. |
| H7 | ¿Eje moral-religioso rompe base evangélica de Trump? | **CONFIRMADA** — Papa Leo activo desde África, cardenales americanos respaldan. |
| H8 | ¿Doctrina Palantir produce guerra que no puede ganar? | **ACTIVA** — OCP en fase pre-completa. Algoritmo alucinando sobre realidad filtrada. |
| H9 | La salida del conflicto no será un acuerdo sino un recule no declarado | **ACTIVA — GANANDO PESO** — F co-dominante con A al cierre S06. |

---

## Nodos críticos

| ID | Descripción | Fecha | Estado |
|----|-------------|-------|--------|
| N1 | Ultimátum Trump 7 abril | 2026-04-07 | ✅ RESUELTO — TACO |
| N2 | Reunión Rutte-Trump | 2026-04-08 | ✅ RESUELTO — OTAN no mordió |
| N10 | Ceasefire mutado | INDEFINIDO | 🟡 Condicionado a "propuesta unificada" iraní |
| N11 | Líbano / Hezbollah | 24 abr | 🟡 ESTABILIZADO — extensión 3 semanas |
| N12 | China / Escollo Scarborough | ACTIVO | 🔴 CONFRONTACIÓN ACTIVA |
| N13 | War Powers Day 60 | **2026-04-29** | 🔴 HOY EN S07 |
| N14 | Hutíes / Bab el-Mandeb | LATENTE | 🟠 PAUSA ESTRATÉGICA |
| N15 | IRGC represalia TOUSKA | EJECUTADA | ✅ CERRADO — 3 buques 22 abril |
| N16 | Islamabad II | 25-27 ABR | 🔴 PARCIAL — Araghchi salió. Sin acuerdo. |
| N17 | Brent umbral $110 | INMINENTE | 🔴 A $5 DEL UMBRAL |
| N18 | Minas Hormuz — 6 meses limpieza | ESTRUCTURAL | 🔴 REDEFINE ESCENARIO A |
| N19 | $TRUMP Gala Mar-a-Lago | 2026-04-25 | 🟡 EJECUTADA — resultado pendiente |
| N20 | Demanda Sun vs WLFI | ACTIVA | 🔴 Criminal extorsión — Zach Witkoff CEO |
| N21 | Nodo Witkoff — conflicto de interés | ESTRUCTURAL | 🔴 PUNTO MÁXIMO S06 |
| N22 | War Powers D60-90 | 29 ABR → 29 MAY | 🔴 ACTIVO — extensión probable |
| N23 | Cumbre Xi-Trump | MAYO 2026 | 🔴 ABIERTO — nodo más importante no operado |
| N24 | Reunión China-Rusia-Irán-IAEA | 2026-04-24 | ✅ EJECUTADO — posición nuclear coordinada |

---

## ESCENARIO F — DEFINICIÓN FORMAL
*(Abierto en S06)*

**Escenario F — Recule No Declarado / Deescalada Sin Acuerdo**

Secuencia de pasos atrás graduales, no coordinados, donde ningún actor declara victoria ni derrota. El conflicto se congela en un limbo gestionado. Todos los actores lo sostienen porque el costo de nombrarlo supera el costo de administrarlo.

**Por qué F no es B:**
B = guerra contenida donde todos mantienen posiciones y el dolor persiste.
F = todos retroceden activamente sin nombrarlo. El dolor empieza a ceder pero la arquitectura que produjo el conflicto permanece intacta.

**Señal de verificación clave:** Cuando el tráfico de Hormuz supere 8 barcos diarios sin anuncio formal iraní de apertura.

---

## Vectores estructurales clave — Sesión 06

| Vector | Descripción | Peso |
|--------|-------------|------|
| V107 | Islamabad II: contacto indirecto sin reunión directa | CRÍTICO |
| V108 | Brent $105 — zona pre-umbral | ESTRUCTURAL |
| V109 | War Powers: deadline disputado | MUY ALTO |
| V110 | Gala $TRUMP + Sun vs WLFI en punto máximo | CRÍTICO |
| V111 | Hormuz: doble cerrojo activo | ESTRUCTURAL |
| V112 | Ghalibaf "nuevas cartas" — no ejecutadas | ALTO |
| V113 | V86 descartada | META |
| V114 | Asimetría estructural de audiencias Islamabad II | ESTRUCTURAL |
| V115 | Divergencia Babel: confusión de lenguas americana | ESTRUCTURAL |
| V116 | Fatiga logística americana: bloqueo con fecha vencimiento | ESTRUCTURAL |
| V117 | Palantir + purga + yesman: arquitectura de decisión ciega | CRÍTICO |
| V118 | Algoritmo no controla realidad: Palantir como espejo roto | ESTRUCTURAL — CRÍTICO |
| V119 | Arquitectura OCP activa en fase pre-completa | ESTRUCTURAL — HISTÓRICO |
| V120 | Fragmentación soberanía tecnológica global | HISTÓRICO |
| V121 | Erosión marca Made in USA en defensa | HISTÓRICO |
| V122 | Doctrina China de neutralidad activa asertiva | HISTÓRICO |
| V123 | Pirámide Madoff: Alfa 0.58 / Beta 0.42 | CRÍTICO |
| V124 | Doble reloj: EE.UU. semanas / Irán 2-3 meses | ESTRUCTURAL — CRÍTICO |

---

## CUATRO RELOJES EN TENSIÓN — S06

**Reloj MILITAR** → apunta a B/F
Doble cerrojo Hormuz. Ghalibaf con cartas no reveladas. Fatiga logística americana. 34 buques interceptados. China: sus barcos pasan "sin restricciones."

**Reloj FINANCIERO** → apunta a F
Brent $105 (a $5 del umbral $110). EIA proyecta $115 Q2. Backwardation $25+. Irán: crisis almacenamiento en 2-3 meses.

**Reloj DOMÉSTICO** → hora crítica
War Powers D60: 29 abril (HOY en S07). Gala $TRUMP ejecutada. Demanda Sun activa. Purga + yesman + Palantir. Cumbre Xi-Trump mayo.

**Reloj IRANÍ INTERNO** *(nuevo S06)* → el más silencioso
47.5% inflación pre-guerra. 36,000 muertos en protestas enero 2026. Economía en colapso estructural. Ventana de resistencia: 2-3 meses.

---

## Cuadro maestro de posiciones negociadoras

| Tema | Posición EEUU | Posición Irán | Gap |
|---|---|---|---|
| Uranio enriquecido | Eliminar / sacar del país | Mover a tercero (Turquía) | ESTRECHO |
| Enriquecimiento futuro | Cero | Máx. 5 años pausa | MEDIO |
| Misiles balísticos | Limitar | **Línea roja absoluta** | TOTAL |
| Hormuz tolls | Eliminar | Levantar si sanciones off | CONDICIONAL |
| Sanciones | Alivio gradual por cumplimiento | Levantamiento total previo | AMPLIO |
| Bloqueo naval | Continuará hasta acuerdo | Debe levantarse antes | BLOQUEANTE |
| Posición nuclear | Bilateral EE.UU.-Irán | Con China+Rusia como garantes | NUEVO S06 |

---

## Historial de sesiones

| Sesión | Fecha | Vectores | Convergencia | Dom. | Estado |
|--------|-------|----------|--------------|------|--------|
| 01 | 2026-04-06 | 3 | 0.47 — INESTABLE | A: 0.50 | ✅ |
| 02 p1 | 2026-04-06 | 17 | 0.75 — CONVERGIENDO | A: 0.64 | ✅ |
| 02 p2 | 2026-04-06 | 24 | 0.82 — CONV. FUERTE | A: 0.66 | ✅ |
| 03 | 2026-04-08 | 36 | 0.85 — CONVERGIENDO | A: 0.65 | ✅ |
| 04 | 2026-04-19 | 50 | 0.82 — CONVERGIENDO | A: 0.50 | ✅ |
| 05 | 2026-04-24 | 106 | 0.86 — CONVERGIENDO | A: 0.43 | ✅ |
| **06** | **2026-04-25** | **124** | **0.86 — CONVERGIENDO** | **F/A: 0.30/0.31** | **✅** |
| 07 | 2026-04-29/30 | — | — | — | 🔜 |

---

## Frases del modelo — registro histórico

**S05:** *"En el intento de evitar que Irán desarrollara un arma de destrucción masiva, EE.UU. le entregó un arma de disrupción masiva, mientras China observaba, y el presidente del país agresor vendía acceso a su persona por $539,000 el cubierto — el mismo día en que su negociador de paz intentaba salvar el mundo en Islamabad."*

**S06:** *"Islamabad II terminó como empezó: con Araghchi en un avión y los americanos llegando a una ciudad vacía. El rey juega al showman en Mar-a-Lago vendiendo tokens que valen 4 centavos por dólar invertido, mientras su negociador aterriza en Pakistan sin audiencia y China observa en silencio calculando cuánto capital político acumula antes de la cumbre de mayo. El Escenario F no es el escenario del ganador. Es el escenario de los dos exhaustos — uno que no puede sostener el bloqueo, y otro que no puede sostener la economía — negociando a través de un intermediario que es el único que gana en cualquier resultado."*

---

## Control de sesgos — Protocolo ANCHOR

El ICM opera con dos métricas de sesgo documentadas formalmente desde S06.
Ver definiciones completas, historial y protocolo en `PROTOCOLO-ANCHOR.md`.

| Métrica | Descripción | Valor S06 | Umbral alerta |
|---|---|---|---|
| ISOI | Sesgo operador → IA (cámara de eco) | 0.21 — leve | > 0.40 |
| ISIO | Sesgo IA → operador (dependencia) | 0.31 — vigilar | > 0.40 |

**Flujo de inicio de sesión con ANCHOR (desde S07):**
1. Pegar `PROTOCOLO-ANCHOR.md` — PRIMERO, sin nada más
2. Pegar correo de recordatorio
3. Adjuntar los 9 archivos cuando el modelo los solicite
4. Pegar prompt de reinicio
5. Operar con reglas R1-R5 activas

---

## Roadmap

- [x] v0.1.0 — Arquitectura conceptual documentada
- [x] v0.1.4 — Sesiones 01 y 02 parte 1 completadas
- [x] v0.1.5 — Sesión 02 parte 2 — Consilience como arquitectura epistemológica
- [x] v0.1.6 — Sesión 03 — 14 vectores nuevos — corrección honesta al cierre
- [x] v0.1.7 — Sesión 04 — 14 vectores nuevos — dos relojes en tensión
- [x] v0.1.8 — Sesión 05 — 56 vectores nuevos — tres relojes + nodo cripto
- [x] v0.1.9 — Sesión 06 — 18 vectores nuevos — seis escenarios + Escenario F + cuatro relojes
- [ ] v0.2.0 — Pipeline de scraping automatizado
- [ ] v0.3.0 — Motor bayesiano implementado en código
- [ ] v1.0.0 — Sistema operativo completo

---

## Referencia metodológica principal

Pearl, J. & Mackenzie, D. (2018). *The Book of Why: The New Science of Cause and Effect*. Basic Books.

---

*Proyecto iniciado el 6 de abril de 2026. Operado mediante dialéctica humano-IA.*
*Operador: docente colombiano. Trayectoria analítica: 6.5 → 9.0 en 6 sesiones.*
