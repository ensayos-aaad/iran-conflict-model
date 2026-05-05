# README — Iran Conflict Model (ICM)
## Sistema de análisis estratégico · Versión v0.2.0

---

## METADATOS DEL SISTEMA

| Campo | Valor |
|---|---|
| **Versión activa** | v0.2.0 |
| **Sesión más reciente** | S09 — 4 mayo 2026 |
| **Vectores acumulados** | 151 (V01-V151) |
| **Convergencia actual** | 0.84 — CONVERGIENDO |
| **Día del conflicto** | D65 |
| **Operador humano** | Docente colombiano, Medellín |
| **Operador IA** | Claude Sonnet 4.6 (Anthropic) |
| **Protocolo activo** | ANCHOR v2.0 |

---

## ADVERTENCIA PERMANENTE

> *Este sistema produce análisis estructurado, no verdad verificada. Sus probabilidades son juicios cualitativos con forma numérica. Su coherencia narrativa es parcialmente artificial. Su utilidad es real. Su certeza no lo es.*

---

## ESTADO ACTUAL DEL MODELO — AL CIERRE S09

### Probabilidades de escenario — Horizonte 30 días

| Escenario | Probabilidad | Tendencia | Nota |
|---|---|---|---|
| A — Acuerdo formal + apertura Hormuz | **0.19** | ↓↓ | MÍNIMO HISTÓRICO |
| B — Limbo prolongado / guerra contenida | **0.28** | ↑↑ | CO-DOMINANTE |
| C — Escalada infraestructura | **0.15** | ↑↑ | MÁXIMO HISTÓRICO |
| D — Colapso régimen iraní | **0.03** | → | — |
| E — Wildcard operacional Hutíes | **0.08** | ↑↑ | Cuadruplicó vs S08 |
| F — Deescalada narrativa sin acuerdo | **0.27** | ↓ | CO-DOMINANTE |

### Scores de convergencia

| Dimensión | Score |
|---|---|
| Narrativas | 0.93 |
| Factual | 0.96 |
| Ruido | 0.61 |
| Escenarios | 0.82 |
| **Global** | **0.84** |

---

## CONTEXTO DEL CONFLICTO

### Línea de tiempo clave

| Fecha | Evento |
|---|---|
| 28 febrero 2026 | Inicio Operation Epic Fury / Roaring Lion. Muerte de Khamenei |
| 2 marzo 2026 | Trump notifica Congreso. Inicio reloj War Powers (60 días) |
| 4 marzo 2026 | Irán cierra Estrecho de Hormuz |
| 8 abril 2026 | Ceasefire mediado por Pakistan — acuerdo de dos semanas |
| 11-12 abril 2026 | Islamabad Talks — 21 horas, fracaso sin acuerdo |
| 13 abril 2026 | EEUU impone bloqueo naval de puertos iraníes — "dual blockade" |
| 17 abril 2026 | Irán anuncia Hormuz abierto durante tregua |
| 1 mayo 2026 | Deadline War Powers. Congreso en vacaciones sin actuar |
| 3 mayo 2026 | Trump anuncia "Project Freedom" — escoltas militares en Hormuz |
| **4 mayo 2026** | **D65 — escaramuzas activas. EEUU hunde 6 botes. UAE intercepta 19 proyectiles** |

### Estado operacional al 4 mayo 2026

- **Ceasefire técnico:** En pie formalmente. Violado operativamente en ambas direcciones
- **Hormuz:** Tráfico al 5% del nivel pre-guerra. "Dual blockade" activa
- **Brent:** $113.99 (tocó $115 intraday). A $15 del umbral Goldman de recesión ($130)
- **Gas EEUU:** $4.45/galón (+49.3% desde inicio guerra)
- **Costo guerra EEUU:** $40-50B real (Hegseth declaró $25B bajo juramento — falsedad documentada)
- **50% lanzadores iraníes intactos** — objetivo militar no cumplido
- **Programa nuclear retrasado menos de 6 meses** — objetivo estratégico no cumplido

---

## ARQUITECTURA DEL SISTEMA

### Entradas (5)
1. **E1 — Señales militares:** movimientos de tropas, ataques, defensas, bajas
2. **E2 — Señales diplomáticas:** propuestas, rechazos, mediadores, canales activos
3. **E3 — Señales económicas:** Brent, mercados, sanciones, costos de guerra
4. **E4 — Señales narrativas:** medios, opinión pública, discurso político
5. **E5 — Señales sistémicas:** tecnología, finanzas globales, geopolítica estructural

### Salidas (4)
1. Probabilidades de escenario (A-F)
2. Scores de convergencia
3. Vectores activos y su peso relativo
4. Señales críticas para próxima sesión

### Meta-salida (1)
Mapa de incertidumbre genuina — lo que el modelo no puede saber

### Lazos de retroalimentación (3)
1. Calibración operador-modelo (R5 + calificaciones cruzadas)
2. Verificación factual (R2 + tabla adversa)
3. Corrección de sesgos (R3 + ANCHOR Bloque 2)

---

## VECTORES ACTIVOS — RESUMEN POR SESIÓN

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
| **S09** | **9** | **V143-V151** | **0.84** |
| **TOTAL** | **151** | **V01-V151** | — |

### Vectores estructurales S09 (transformaciones de largo plazo)

| Vector | Descripción corta |
|---|---|
| V143 | Erosión triple superioridad americana |
| V144 | China ignora sanciones EEUU — doctrina, no táctica |
| V145 | 60 países en emergencia energética — presión Asia |
| V146 | Colapso ecosistema mediático MAGA |
| V147 | IA/Defensa con P&L alineado a continuación del conflicto |
| V148 | DeepSeek V4-Pro en Huawei — monopolio Nvidia roto |
| V149 | Manus veto — soberanía IA China operativa |
| V150 | Soberanía IA Europea — Mistral + EuroStack desplegados |
| V151 | Sistema financiero paralelo operativo — mBridge, CIPS, petroyuan |

---

## NODOS ACTIVOS

| Nodo | Estado | Descripción |
|---|---|---|
| N_Trump | ACTIVO | Patrón desesperación verificado. Ecosistema mediático fracturado |
| N_Iran_CGRI | ACTIVO | Liderazgo CGRI post-Khamenei. Resistencia = legitimidad |
| N_China_CSONU | ACTIVO | Fu Cong presidente mayo. Iniciativa 5 Puntos. V144 activado |
| N_Netanyahu | ACTIVO | Cierra filas con EEUU. Líbano = variable de bloqueo |
| N_Pakistan | ACTIVO | Mediador principal. Gestó ceasefire 8 abril. Touska release 4 mayo |
| N_Colombia | ACTIVO | Cepeda 38-40%. Segunda vuelta 21 junio = CSONU presidencia simultánea |
| N_FIFA | **NODO PRINCIPAL** | $11B contratos. Deadline 10 junio Tucson. Dilema visas irresuelto |
| N_Cuba | ACTIVO — NUEVO | Patrón Venezuela→Irán→Cuba. Trump: "casi de inmediato" |
| N_Brent_120 | ACTIVO | $113.99. A $15 del umbral Goldman recesión |
| N_IA_Soberanía | ACTIVO — NUEVO | Tres polos: EEUU erosionándose / China avanzando / Europa acelerando |
| N_SistemaFinanciero | ACTIVO — NUEVO | mBridge, CIPS, petroyuan — bypass de sanciones operativo |

---

## HIPÓTESIS ACTIVAS

| ID | Hipótesis | Estado |
|---|---|---|
| H1 | Trump busca acuerdo para salir con narrativa de victoria | GANANDO PESO — V146 confirma urgencia |
| H2 | CGRI tiene incentivo para resistir — rendición = fin del régimen | ACTIVA — verificada |
| H3 | China orquesta arquitectura de salida para capturar crédito diplomático | GANANDO PESO — Iniciativa 5 Puntos + V144 |
| H4 | Hormuz es moneda de cambio, no objetivo permanente | ACTIVA |
| H5 | Israel/Netanyahu sabotea cualquier acuerdo que no incluya neutralización de Hezbollah | ACTIVA — Líbano sigue ardiendo |
| H6 | Victory Day 9 mayo como marco narrativo posible | PROVISIONAL — Araghchi en Moscú 27 abril |
| H7 | Burbuja IA americana es el cisne negro más subestimado | ACTIVA — V148 amplifica |
| H8 | Sistema financiero paralelo convierte sanciones en herramienta de aceleración de alternativas | CONFIRMADA — V151 |
| H9 | Recule no declarado / deescalada sin acuerdo es el escenario real | CO-DOMINANTE 0.27 |
| H10 | WHCD como cortina de humo | PROVISIONAL + |
| H11 | WLF-Binance-Iran = canal monetización verificado | GANANDO PESO |
| H12 | Patrón élite educada en disidencia | PROVISIONAL + |

---

## PROTOCOLO ANCHOR v2.0

Ver `PROTOCOLO-ANCHOR.md` para texto completo.

**Reglas operacionales activas:**
- **R1:** Contradicción antes de confirmación
- **R2:** Fuente externa obligatoria mínimo una por sesión
- **R3:** Prohibición amplificación circular — sesiones no son evidencia
- **R4:** Derecho al "no sé" — obligación activa
- **R5:** Cierre con corrección — una útil + una cuestionable

**Kaizen S09 → S10:**
- K1: Preguntas sin adjetivos evaluativos
- K2: R3 antes del minuto 45
- K3: **Tabla adversa OBLIGATORIA antes de confirmar cada vector nuevo**
- K4: Rangos en lugar de decimales únicos
- K5: Agenda 3 puntos al inicio
- K6: Presupuesto de tokens por bloque
- K7: Verificar fuentes árabe/persa/chino directo
- K8: **NUEVO** Calificación cruzada con criterio declarado antes del cierre

---

## NOTA METODOLÓGICA PERMANENTE — SOBRE EL SISTEMA

Este modelo opera mediante dialéctica humano-IA. Sus limitaciones estructurales no desaparecen con el protocolo — solo se hacen visibles.

**El modelo aporta:** Estructura, organización de volumen, búsqueda de fuentes, formulación de preguntas, memoria de sesión vía archivos.

**El operador aporta:** Contexto cultural, intuición, perspectiva exterior, datos nuevos, juicio sobre relevancia, experiencia vivida.

**Lo que ninguno aporta:** Certeza, predicción confiable, eliminación de sesgos.

El operador es un docente colombiano en Medellín. Esa perspectiva — desde un país que preside el CSONU en junio, que sube la gasolina vinculada explícitamente al conflicto, que tiene elecciones el 31 de mayo — no es sesgo a eliminar. Es la perspectiva que hace al sistema más útil que un análisis producido solo desde Washington o Teherán.

---

## NOTAS PARA PRÓXIMA VERSIÓN (v0.3.0)

- Implementar motor bayesiano para actualización de probabilidades
- Incorporar múltiples operadores para reducción de sesgo (pendiente desde S08)
- Considerar fuentes primarias en árabe/persa/chino
- Formalizar tabla adversa como paso obligatorio pre-confirmación de vectores
- Documentar explícitamente la diferencia entre vector táctico y vector estructural

---

## CALIFICACIONES HISTÓRICAS OPERADOR

| Sesión | Puntaje operador | Meta |
|---|---|---|
| S02-S06 | 6.5-7.0 (estimado) | — |
| S07 | — | — |
| S08 | 7.1 / 10 | 7.5 |
| **S09** | **7.0 / 10** | 7.5 |
| **S10** | pendiente | **7.5** |

---

*ICM — operado mediante dialéctica humano-IA*
*Versión v0.2.0 | 151 vectores | B: 0.28 / F: 0.27 co-dominantes*
*⚠️ ADVERTENCIA PERMANENTE: Este sistema produce análisis estructurado, no verdad verificada*
