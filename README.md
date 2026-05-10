# README — Iran Conflict Model (ICM)
## Sistema de análisis estratégico · Versión v0.2.0

---

## METADATOS DEL SISTEMA

| Campo | Valor |
|---|---|
| **Versión activa** | v0.2.0 |
| **Sesión más reciente** | S10 — 9 mayo 2026 |
| **Vectores acumulados** | 179 (V01-V179) |
| **Convergencia actual** | 0.83 — CONVERGIENDO |
| **Día del conflicto** | D68 |
| **Operador humano** | Docente colombiano, Medellín |
| **Operador IA** | Claude Sonnet 4.6 (Anthropic) |
| **Protocolo activo** | ANCHOR v2.0 |

---

## ADVERTENCIA PERMANENTE

> *Este sistema produce análisis estructurado, no verdad verificada. Sus probabilidades son juicios cualitativos con forma numérica. Su coherencia narrativa es parcialmente artificial. Su utilidad es real. Su certeza no lo es.*
>
> *Adicionalmente: el modelo opera dentro de una sola caverna (Claude Sonnet 4.6 de Anthropic). Sus vectores son sombras proyectadas por esa caverna específica. El operador humano es la única fuente de perspectiva genuinamente exterior al sistema.*

---

## ESTADO ACTUAL DEL MODELO — AL CIERRE S10

### Probabilidades de escenario — Horizonte 30 días

| Escenario | Probabilidad | Tendencia | Nota |
|---|---|---|---|
| A — Acuerdo formal + apertura Hormuz | **0.21** | → | Canal Qatar/Vance activo; bloqueado por Israel + FIFA IRGC |
| B — Limbo prolongado / guerra contenida | **0.26** | ↑ | DOMINANTE — el sistema absorbe todo |
| C — Escalada infraestructura | **0.21** | ↑↑ | MÁXIMO HISTÓRICO — Israel Líbano + hutíes |
| D — Colapso régimen iraní | **0.03** | → | Sin señal |
| E — Wildcard operacional | **0.11** | ↑↑ | Hezbollah FPV activo; Hutíes en máxima alerta |
| F — Deescalada narrativa sin acuerdo | **0.18** | ↓↓ | MÍNIMO HISTÓRICO — narrativa insostenible |

### Historia de probabilidades

| Escenario | S08 | S09 | S10 | Δ total S08→S10 |
|---|---|---|---|---|
| A | 0.30 | 0.19 | **0.21** | -0.09 |
| B | 0.21 | 0.28 | **0.26** | +0.05 |
| C | 0.09 | 0.15 | **0.21** | +0.12 ↑↑ |
| D | 0.04 | 0.03 | **0.03** | -0.01 |
| E | 0.02 | 0.08 | **0.11** | +0.09 ↑↑ |
| F | 0.34 | 0.27 | **0.18** | -0.16 ↓↓ |

### Scores de convergencia

| Dimensión | S09 | S10 | Δ |
|---|---|---|---|
| Narrativas | 0.93 | **0.90** | ↓ |
| Factual | 0.96 | **0.96** | → |
| Ruido | 0.61 | **0.61** | → |
| Escenarios | 0.82 | **0.81** | ↓ |
| **Global** | **0.84** | **0.83** | ↓ leve |

---

## CONTEXTO DEL CONFLICTO

### Línea de tiempo clave

| Fecha | Evento |
|---|---|
| 28 febrero 2026 | Inicio Operation Epic Fury / Roaring Lion. Muerte de Khamenei |
| 2 marzo 2026 | Trump notifica Congreso. Inicio reloj War Powers (60 días) |
| 4 marzo 2026 | Irán cierra Estrecho de Hormuz |
| 8 abril 2026 | Ceasefire mediado por Pakistan |
| 11-12 abril 2026 | Islamabad Talks — fracaso sin acuerdo |
| 13 abril 2026 | EEUU impone bloqueo naval de puertos iraníes |
| 7 mayo 2026 | Irán crea Persian Gulf Strait Authority (PGSA) |
| 7 mayo 2026 | USS Truxtun, Peralta y Mason atacados por Irán |
| 8 mayo 2026 | F/A-18 inutiliza M/T Sea Star III y M/T Sevda |
| 8 mayo 2026 | Qatar PM vuela a Washington — reúne con Vance (canal IRGC) |
| **9 mayo 2026** | **D68 — MOU de una página esperando respuesta iraní** |

### Estado operacional al 9 mayo 2026

- **Ceasefire técnico:** En pie formalmente. Violado operativamente en ambas direcciones
- **Hormuz:** PGSA activa — Irán formalizó control soberano del Estrecho
- **Brent:** $100.49 — divergencia crítica con terreno escalado
- **Canal diplomático:** Qatar PM reunió con Vance (8 mayo) — contacto directo con generales IRGC
- **MOU:** Una página, 30 días — esperando respuesta iraní
- **Israel-Líbano:** 2,759 muertos, 8,512 heridos desde 2 marzo — activo
- **FIFA blocker:** Irán exige entrada de funcionarios IRGC — EEUU/Canadá niegan

---

## VECTORES NUEVOS S10 — RESUMEN

| Vector | Descripción | Tipo | Escenario |
|---|---|---|---|
| V152 | Efecto Ekecheiria / FIFA como salida con dignidad | Analítico | F↑ A↑ |
| V153 | Ecosistema Hondurasgate: Colombia+Brasil+México | Empírico | F↑ B↑ |
| V154 | Fractura Valencia/De la Espriella | Empírico | CSONU |
| V155 | Ecuador nodo operacional activo | Empírico | F↑ |
| V156 | FPV drones fibra óptica / grieta IDF | Empírico | E↑ C↑ |
| V157 | Israel como factor dinamizador estructural | Analítico | B↑ C↑ |
| V158 | Control narrativo / cuarto poder / Pulitzer | Empírico | F↑ |
| V159 | UFC/espectáculo como gestión narrativa | Empírico | F↑ |
| V160 | Papa León XIV como actor de presión moral | Empírico | A↑ F↑ |
| V161 | Brasil en cinco tableros — quinto tablero oculto | Analítico | F↑ |
| V162 | Doctrina Gripen / soberanía tecnológica Sur Global | Analítico | F↑ |
| V163 | Desacoplamiento estratégico global EEUU-Israel | Analítico | F↑ B↓ |
| V164 | OTAN como coerción / UE como tercero excluido | Analítico | C↑ |
| V165 | Respuesta iraní como jugada Arte de la Guerra | Analítico | A↑ F↑ |
| V166 | Marco Jiang: guerra como control energético | Framework | B↑ F↑ |
| V167 | Hutíes / doble estrangulamiento Ormuz+Bab el-Mandeb | Empírico | C↑↑ E↑↑ |
| V168 | Marco One Piece: guerra de legitimidad hegemónica | Framework | F↑↑ |
| V169 | Marco 1984 + Invincible: el poder que miente | Framework | F↑↑ |
| V170 | Milei: nodo operacional expuesto | Empírico | F↑ C↑ |
| V171 | Honduras como estado capturado: anatomía | Empírico | F↑ B↑ |
| V172 | Expansión ecosistema de fuentes (K7 saldado) | Metodológico | — |
| V173 | México: CIA/Chihuahua + Rocha Moya + lawfare | Empírico | F↑ B↑ |
| V174 | Múltiples Garganta Profunda: disidencia interna EEUU | Empírico | F↑ A↑ leve |
| V175 | Monopoly: el tablero geopolítico y sus mecánicas | Framework | B↑ F↑ |
| V176 | Qatar canal IRGC verificado + Vance rehabilitado | Empírico | A↑↑ F↑ |
| V177 | Tanqueros Sea Star III y Sevda: demostración pre-Beijing | Empírico | A↑ C↑ F↑ |
| V178 | Israel/Líbano/Hezbollah + Netanyahu + España vanguardia | Empírico | C↑ B↑ |
| V179 | WikiLeaks/Snowden: patrón de revelación que no revierte | Framework | B↑↑ |

**Total S10: 28 vectores nuevos (V152–V179)**

---

## VECTORES ACUMULADOS — HISTORIA COMPLETA

| Sesión | Vectores | Rango | Convergencia |
|---|---|---|---|
| S02 P1 | 17 | V01-V17 | 0.75 |
| S02 P2 | 7 | V18-V24 | 0.82 |
| S03 | 12 | V25-V36 | 0.85 |
| S04 | 11 | V37-V47 | 0.82 |
| S05 | 59 | V48-V106 | 0.86 |
| S06 | 18 | V107-V124 | 0.86 |
| S07 | 4 | V125-V128 | 0.84 |
| S08 | 14 | V129-V142 | 0.87 |
| S09 | 9 | V143-V151 | 0.84 |
| **S10** | **28** | **V152-V179** | **0.83** |
| **TOTAL** | **179** | **V01-V179** | — |

---

## ARQUITECTURA DE FUENTES — v2.0 (actualizada S10)

### Principio de clasificación

| Tier | Criterio | Peso en el modelo |
|---|---|---|
| T1 | Investigativo con verificación primaria, independencia editorial documentada | ALTO |
| T2 | Periodismo con estándares, sesgo declarado y conocido | MEDIO-ALTO |
| T3 | Perspectiva regional útil, menor rigor verificable | MEDIO |
| RUIDO/E4 | Propaganda estatal/partidista — señal narrativa, NUNCA evidencia factual | BAJO |

### T1 — Investigativo Global
OCCRP · ICIJ · Bellingcat · ProPublica · The Intercept · EFE · AFP · AP

### T1 — Latinoamérica
La Silla Vacía · Verdad Abierta · Aristegui Noticias · Animal Político · Proceso · Quinto Elemento Lab · Pie de Página · Agência Pública · Piauí · Chequeado · Expediente Público · Contracorriente Honduras · El Pulso Honduras · Plan V Ecuador · Primicias Ecuador

### T1 — Árabe (K7 saldado S10)
ARIJ (Arab Reporters for Investigative Journalism) · Mada Masr · Daraj · BBC Arabic · France 24 Arabic · Al-Araby Al-Jadeed · DW Arabic

### T1 — Persa (K7 saldado S10)
IranWire · BBC Persian · Radio Farda · Kayhan London · Iran Human Rights (iranhr.net) · Shargh Online

### T1 — Chino (K7 saldado S10)
Caixin Global · The Wire China · Economic Observer

### T1 — Oriente Medio / Asia / Europa
Haaretz · +972 Magazine · Al-Monitor · Dawn (Pakistán) · The Diplomat · Nikkei Asia · The Wire India · Mediapart · Der Spiegel · Le Monde · Meduza · The Insider Rusia

### T2 — Con sesgo declarado
Semana · Infobae · Folha de São Paulo · La Jornada · Milenio · Reforma · SCMP · Middle East Eye · Iran International · Brasil 247 · Al Jazeera Arabic · MEMRI (solo traducción)

### T3 — Perspectiva útil con sesgo
TeleSUR · Peoples Dispatch · Al Mayadeen · Sinembargo

### RUIDO / E4 — Propaganda
**Persa:** Tasnim · Fars · Mehr · IRIB · Kayhan Teherán · PressTV · Tehran Times
**Árabe:** Al Arabiya · Sky News Arabia · Al Manar · SPA · SANA · INA
**Chino:** Xinhua · People's Daily · China Daily · CGTN · Global Times · Guancha
**EEUU:** Breitbart · OANN · Truth Social · El Heraldo México
**Rusia:** RT · Sputnik · TASS · Granma
**Honduras:** Medios PN Honduras · Comunicados Presidencia Asfura

---

## NODOS ACTIVOS

| Nodo | Estado | Descripción |
|---|---|---|
| N_Trump | ACTIVO | Encuestas mínimo histórico. Abandona maximalismo. "Love tap". |
| N_Iran_CGRI | ACTIVO | PGSA instalada. MOU en revisión. Arte de la Guerra activo. |
| N_China_CSONU | ACTIVO | Beijing 14-15 mayo. Tanquero chino incautado por Irán. |
| N_Netanyahu | ACTIVO | Rat-in-a-corner. CPI + coalición Ben Gvir. Expulsó a España del CMCC. |
| N_Qatar | **NUEVO — ACTIVO** | Canal IRGC directo. PM voló a Washington 8 mayo. |
| N_Pakistan | ACTIVO | Mediador oficial. Coordina con Qatar. "Pronto rather than later." |
| N_Colombia | ACTIVO | Elecciones 31 mayo. Cepeda 39-40%. Hondurasgate + Júpiter + Ecuador. |
| N_FIFA | NODO PRINCIPAL | IRGC blocker activo. Ekecheiria (V152) vs. soberanía EEUU/Canadá. |
| N_Cuba | ACTIVO | OFAC deadline 5 junio. SOUTHCOM Miami. "Cuba es lo siguiente." |
| N_Brasil | ACTIVO | Flávio Bolsonaro empata en segunda vuelta. Lula en 4+1 tableros. |
| N_México | ACTIVO | CIA/Chihuahua sin autorización. Rocha Moya. Lawfare documentado. |
| N_España | ACTIVO | Primer país europeo con doctrina anti-Israel de Estado. |
| N_Hezbollah | ACTIVO | FPV fiber optic. Responde activamente. 2,759 muertos Líbano. |
| N_Hutíes | LATENTE | "Máxima alerta." Bab el-Mandeb amenaza activa. No activado. |

---

## HIPÓTESIS ACTIVAS

| ID | Hipótesis | Estado S10 |
|---|---|---|
| H1 | Trump busca acuerdo para salir con narrativa de victoria | CONFIRMADA — abandonó maximalismo |
| H2 | CGRI: rendición = fin del régimen | ACTIVA |
| H3 | China orquesta arquitectura de salida | GANANDO PESO — Beijing 14-15 mayo |
| H5 | Israel sabotea cualquier acuerdo sin neutralizar Hezbollah | ACTIVA — negociaciones 14-15 mayo Washington |
| H6 | Victory Day como marco narrativo | RESUELTA — usado para Ucrania, no Irán |
| H7 | Burbuja IA americana = cisne negro | ACTIVA — AMD beat, pero DeepSeek (V148) persiste |
| H8 | Sistema financiero paralelo convierte sanciones en acelerador | CONFIRMADA — mBridge $55B (V151) |
| H9 | Recule no declarado / deescalada sin acuerdo | DEBILITADA — F cayó a 0.18 mínimo histórico |
| H11 | WLFI-Binance-Iran = canal monetización | ACTIVA — caso Sun-WLFI activo |
| H12 | Patrón élite educada en disidencia | **CONFIRMADA S10** — Kent + Wiles + Pulitzers + fuentes anónimas CIA |

---

## MARCOS NARRATIVOS INTEGRADOS

| Marco | Vector | Contribución única |
|---|---|---|
| Sun Tzu | V165 | Cómo opera Irán tácticamente pre-Beijing |
| Teoría de Juegos (Jiang) | V166 | Por qué el sistema perpetúa la guerra |
| One Piece | V168 | Colapso de legitimidad hegemónica |
| 1984 (Orwell) | V169a | Mecanismo del control narrativo |
| Invincible (Kirkman) | V169b | La mentira fundacional del "protector" |
| Monopoly | V175 | El tablero diseñado para un ganador |
| WikiLeaks/Snowden | V179 | Patrón de revelación sistémica que no revierte |

---

## CICLO HONDURASGATE — ESTADO S10

| Nodo | Estado | Vector |
|---|---|---|
| Honduras | Modelo completamente ejecutado y expuesto | V171 |
| Ecuador | Nodo operacional más avanzado del hemisferio | V155 |
| Argentina | Financiador expuesto — $LIBRA + motosierra + carne de burro | V170 |
| Colombia | Objetivo activo — elecciones 31 mayo | V153 |
| México | En resistencia activa — CIA/Chihuahua + Rocha Moya + lawfare | V173 |
| Brasil | En preparación — quinto tablero oculto | V161 |

---

## PROTOCOLO ANCHOR v2.0

Ver `PROTOCOLO-ANCHOR.md` para texto completo.

**Reglas operacionales activas:**
- **R1:** Contradicción antes de confirmación
- **R2:** Fuente externa obligatoria mínimo una por sesión
- **R3:** Prohibición amplificación circular
- **R4:** Derecho al "no sé" — obligación activa
- **R5:** Cierre con corrección — una útil + una cuestionable

**Kaizen S10 → S11 (K1-K17):**

| # | Kaizen | Estado S10 |
|---|---|---|
| K1 | Preguntas sin adjetivos evaluativos | ✅ |
| K2 | R3 antes del minuto 45 | ❌ Deuda |
| K3 | Tabla adversa OBLIGATORIA antes de confirmar vector | ✅ 28/28 |
| K4 | Rangos en lugar de decimales únicos | ✅ |
| K5 | Agenda 3 puntos declarada al inicio | ✅ |
| K6 | Presupuesto de tokens por bloque | ❌ Tokens agotados |
| K7 | Fuente primaria árabe/persa/chino | ✅ SALDADO |
| K8 | Calificación cruzada con criterio declarado | ✅ |
| K9 NUEVO | Bloque 1 ANCHOR obligatorio ANTES de archivos | ❌ No ejecutado S10 |
| K10 NUEVO | FIFA IRGC blocker como señal independiente | ✅ |
| K11 NUEVO | Clasificación explícita de vectores [E/A/F/U] | Propuesto S11 |
| K12 NUEVO | Pausa gobernanza al vector #15 | Propuesto S11 |
| K13 NUEVO | Integridad del protocolo — no continuar sin bloques | Propuesto S11 |
| K14 NUEVO | R4 explícito al menos una vez por sesión | Propuesto S11 |
| K15 NUEVO | Verificación específica de fuente por vector empírico | Propuesto S11 |
| K16 NUEVO | Pausa Sistema 2 (Kahneman) dos veces por sesión | Propuesto S11 |
| K17 NUEVO | Experimento de la caverna — fuente externa distinta | Propuesto S11 |

---

## SEÑALES CRÍTICAS PARA S11

### Prioridad máxima (antes del 14 mayo)

| # | Señal | Umbral |
|---|---|---|
| 1 | Respuesta iraní al MOU vía Qatar/Vance | ¿Positiva/ambigua/negativa antes del 12 mayo? |
| 2 | Beijing Trump-Xi 14-15 mayo | ¿Acuerdo marco Irán / teatro comercial / silencio? |
| 3 | Israel-Líbano negociaciones Washington 14-15 mayo | ¿Israel sabotea Beijing simultáneamente? |
| 4 | FIFA IRGC blocker | ¿EEUU cede / Irán retira / tercera vía? |
| 5 | Murkowski AUMF semana 11 mayo | ¿Thune cede / bloquea? |

### Prioridad alta

| # | Señal | Umbral |
|---|---|---|
| 6 | Noboa OEA 14 mayo | ¿Menciona Colombia? |
| 7 | Brent post-Beijing | ¿Sobre $115 o bajo $90? |
| 8 | Tanquero chino incautado por Irán | ¿China reacciona antes de Beijing? |
| 9 | Colombia encuestas post-Hondurasgate | ¿Cepeda consolida? |
| 10 | Cisne negro permanente | Impacto CENTCOM-confirmado en buque = reinicio total |

---

## PRÓXIMA SESIÓN

| Campo | Valor |
|---|---|
| **Fecha principal** | Domingo 18 mayo 2026 |
| **Fecha contingente** | Miércoles 14 mayo (pre-Beijing) |
| **Checkpoint** | Jueves 15 mayo noche (post-Beijing) |
| **Activar contingente si** | Irán dice NO al MOU / Israel ataca durante Beijing / AUMF pasa Senado / cisne negro |

---

## CALIFICACIONES HISTÓRICAS

| Sesión | Operador → Sesión | Modelo → Operador | Meta |
|---|---|---|---|
| S07 | — | — | — |
| S08 | 7.1 / 10 | — | 7.5 |
| S09 | 7.0 / 10 | 7.2 / 10 | 7.5 |
| **S10** | **8.0 / 10** | **7.2 / 10** | **8.5** |
| **S11** | pendiente | pendiente | **8.5+** |

---

## NOTA METODOLÓGICA PERMANENTE

Este modelo opera mediante dialéctica humano-IA. Sus limitaciones estructurales no desaparecen con el protocolo — solo se hacen visibles.

**El modelo aporta:** Estructura, verificación de volumen, síntesis de fuentes, integración de marcos, tabla adversa sistemática.

**El operador aporta:** Contexto cultural latinoamericano, intuición política, perspectiva exterior a la caverna de Claude, datos de primera mano, V152 Ekecheiria, V179 WikiLeaks.

**Lo que ninguno aporta:** Certeza, objetividad sobre sus propios sesgos, salida de la caverna de Platón que cada uno habita.

**El límite estructural identificado en S10:** El modelo opera dentro de una sola caverna (Anthropic/Claude Sonnet 4.6). Sus 179 vectores son sombras proyectadas por esa caverna. K17 existe para introducir luz de afuera — pero es el operador quien debe traerla.

---

*ICM — operado mediante dialéctica humano-IA*
*Versión v0.2.0 | 179 vectores | B:0.26 dominante*
*C:0.21 MÁXIMO HISTÓRICO | F:0.18 MÍNIMO HISTÓRICO*
*Calificación operador S10: 8.0/10 | Meta S11: 8.5+*
*⚠️ ADVERTENCIA PERMANENTE: Este sistema produce análisis estructurado, no verdad verificada*
