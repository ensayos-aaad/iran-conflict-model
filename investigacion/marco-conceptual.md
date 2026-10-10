# Marco conceptual

**Fecha:** 10 de octubre de 2026 · **Estado:** borrador · Las referencias con † se citan de memoria (ver [estado-del-arte.md](estado-del-arte.md)).

---

## 1. Qué tipo de trabajo es

El ICM no es un sistema de pronóstico estadístico ni un *notebook* sobre un conjunto de datos. Es un **estudio de caso de inferencia por diálogo humano-IA**: un operador y un modelo de lenguaje buscan patrones en información abierta, con reglas explícitas (ANCHOR R1–R6, Kaizen K1–K25).

- **Replicar** aquí no significa obtener los mismos números: el modelo no responde igual dos veces, las fuentes cambian y el operador es otro. Significa que **otro operador, con otro caso, pueda aplicar el mismo protocolo, y que su trabajo se pueda auditar con los mismos criterios.**
- **El artefacto es el protocolo**, no un software. Encuadre: Design Science Research † (Hevner y otros, 2004).

## 2. Conciliencia: el antecedente estaba en el propio modelo

| Sentido | Definición | Ejemplo en el ICM |
|---|---|---|
| **Corroboración** | Varias fuentes independientes confirman el mismo hecho | Regla de "2 o más fuentes de bloques distintos" (S15) |
| **Conciliencia (Whewell †)** | Una hipótesis formulada para un tipo de hechos explica hechos **de otra clase, que no se usaron para formularla** | "La pausa es solo de bombardeos" explica hechos económicos, de seguridad, de guerra por delegación, de ciberataques y narrativos (S15, sección 10) |
| **Conciliencia (Wilson †)** | Convergencia de disciplinas hacia una explicación común | Varias disciplinas nombran el mismo error y el mismo remedio (sección 6 de este documento) |

**Antecedentes internos, no nuevos:**
- **V24 — "Consilience / convergencia ciencias duras y humanas"** ([S02, parte 2, 6 abr 2026](../simulaciones/2026-04-06-sesion-02-parte2.md)): la IA como instrumento de conciliencia por haber sido entrenada sin particiones disciplinares.
- **V33 — "Factor Chomsky"** ([S03, 8 abr 2026](../simulaciones/2026-04-08-sesion-03.md)): *"La IA puede integrar disciplinas pero sin detector de poder puede integrar narrativas capturadas con la misma eficiencia que narrativas independientes."* **Es la advertencia sobre la falsa conciliencia**, formulada dos días después de V24.
- **S02, parte 2:** *"Un modelo que solo sube con cada inyección no aprende: confirma."*

**Observación metodológica:** en las conversaciones del 9–10 de octubre, el modelo (sin leer el registro) reconstruyó la conciliencia como si fuera una idea nueva. Muestra que, sin memoria del registro, el modelo redescubre lo que el propio proyecto ya había formulado.

**El riesgo central es la falsa conciliencia:** los modelos de lenguaje producen analogías y convergencias coherentes con mucha facilidad. **Regla de trabajo:** una analogía entra al marco solo si produce **una herramienta, una medida o una predicción que se pueda probar**. Si solo suena bien, se queda como ilustración.

## 3. Las inyecciones dialécticas y el ciclo de Peirce

La "inyección dialéctica" del ICM es la contribución del operador al **atar cabos** ("pensadera y malicia", S05). Ejemplos: las 8 capas de corrupción sistémica (S12), Israel-Rusia como estructuras isomórficas, Universe 25 (D94). La S05 ya auditó una inyección como 65% hechos y 35% inferencia.

Nombres académicos de "atar cabos": **abducción** (Peirce †), **bisociación** (Koestler †), **razonamiento por analogía** (Gentner †, Hofstadter †).

| Paso de Peirce | Qué hace | Quién lo hizo en el ICM |
|---|---|---|
| Abducción | Proponer la hipótesis | El operador (inyecciones dialécticas) |
| Deducción | Derivar consecuencias y verificar hechos | La IA (estructura, fuentes, contradicción) |
| Inducción | Contrastar con lo que ocurre | La realidad (CEM 21 jun; 3 nov; 31 dic) |

**Hipótesis de trabajo** (coherente con Vaccaro y otros, 2024): el valor del diálogo, si existe, está en la **abducción**, la parte generativa, y no en el número final, la decisión.

## 4. Vibe coding, "vibe analysis" y sesgo de automatización

- **Vibe coding** (Karpathy, 2025 †): aceptar código generado por IA sin leerlo, con el criterio de "si funciona, sigue".
- **"Vibe analysis":** su versión analítica, que es aceptar texto coherente sin verificarlo. Es más peligrosa que en programación porque **el código tiene un juez inmediato (corre o falla) y el análisis no**: la realidad responde tarde y de forma ambigua.
- **Concepto académico de fondo:** sesgo de automatización y complacencia (Parasuraman y Manzey, 2010 †). "Vibe coding" sirve como gancho de divulgación, no como concepto teórico.
- **El remedio análogo al de la industria:** escribir las pruebas antes del código (TDD). Aquí el **prerregistro** cumple el papel de las pruebas.
- **Fases de "vibe analysis" en el propio ICM:** el 73% autocalificado de la S14, la prosa analítica aceptada (100% redactada por la IA según el COCREACION.md) y el escenario C, que no se consideró seriamente hasta D94.

## 5. Niveles de automatización y estilos de uso

| Modo de uso | ICM S01–S13 | CEM | S14–S15 |
|---|---|---|---|
| Chat con asistente | Sí | Sí | Sí |
| Búsqueda con fuentes | Sí | Sí | Sí |
| Prompt estructurado (ANCHOR) | Sí | Versión liviana | Sí |
| Ingeniería de contexto (memoria y archivos) | Proyecto claude.ai | Proyecto claude.ai | CLAUDE.md |
| Agente con herramientas | No | No | **Sí, con puntos de control humanos** |
| Automatización sin humano | No | No | No |

- **Sheridan y Verplank †:** el trabajo está en los niveles intermedios: la máquina propone y el humano aprueba.
- **Centauro y cyborg (Dell'Acqua y otros †):** el ICM fue más "centauro" (reparto declarado en el COCREACION.md) y la S15 más "cyborg" (corrección mutua paso a paso).

## 6. El aporte desde señales, control y ciencia de datos

| Concepto | En el ICM/CEM | ¿Produce algo medible? |
|---|---|---|
| Detección: falsa alarma frente a no detección (ROC) | Apofenia frente a ceguera | Sí: tasa de patrones falsos y tasa de patrones perdidos |
| Relación señal/ruido | Ruido narrativo (E4) y desinformación (S3); diferencia de cobertura (Nemkova) | Parcial |
| Diversidad y desvanecimiento correlacionado | Fuentes por bloques; dos medios del mismo bloque fallan juntos | Sí: regla de bloques |
| Estimación bayesiana, Kalman | Motor bayesiano (P1); K21 como limitación de ganancia | Pendiente (P1) |
| **Entropía de Shannon** | **Medir la convergencia en lugar de estimarla** | **Sí: ver abajo** |
| Conjunto de prueba, fuga de datos | Prerregistro; analizar sabiendo el resultado = fuga | Sí |
| Sobreajuste | Las 32 versiones del CEM persiguieron cada señal de campaña | Descriptivo |
| **Identificación en lazo cerrado** | Con realimentación humana no se separan humano, modelo y método sin excitación externa | **Sí: justifica el experimento A/B** |

### La entropía contradice la convergencia narrada

Entropía de la distribución de escenarios A–F al 31 de diciembre (máximo para 6 escenarios: log₂ 6 = 2,585 bits). Para S14 y S15 se usaron los puntos medios de los rangos, normalizados:

| Corte | Distribución usada | Entropía | Fracción del máximo | Convergencia narrada |
|---|---|---|---|---|
| S13 (7 jun) | C .52 · F .22 · B .10 · A .06 · E .06 · D .04 | 1,976 bits | 0,764 | 0,51 |
| S14 (18 sept) | puntos medios (suma 1,065, normalizada) | 2,033 bits | 0,786 | 0,42–0,48 (baja) |
| S15 (9 oct) | puntos medios (suma 1,02, normalizada) | 2,143 bits | 0,829 | **0,44–0,50 (sube)** |

**Discrepancia registrada:** la S15 narró que la convergencia *subía*, pero la entropía de la distribución a fin de año *aumenta*: hay más incertidumbre, no menos. La S15 justificó la subida con fechas-bisagra de corto plazo, mientras que la entropía mide la distribución al 31 de diciembre. **Las dos cosas miden horizontes distintos, pero la S15 no lo distinguió en su cifra.** Es un ejemplo concreto de juicio narrativo que contradice una medida simple, y un argumento para sustituir la "convergencia" estimada por una métrica calculada.

## 7. El observador dentro del sistema

El operador es a la vez quien mide, quien es medido y quien evalúa (cibernética de segundo orden, von Foerster †). Evidencia: en el CEM, la autocalificación pasó de 96/100 antes del resultado a 78/100 después. **Consecuencia de diseño:** la calificación independiente y posterior es obligatoria.

## 8. Ubicación disciplinar

No hay una sola disciplina. Las que tocan directamente el trabajo:
- **Núcleo:** interacción humano-computador y factores humanos, y sistemas de información (Design Science).
- **Antecedente:** ingeniería del conocimiento (sistemas expertos; ANCHOR como base de reglas, el operador como experto del dominio y el modelo como motor de inferencia).
- **Aplicación:** análisis de inteligencia y OSINT, prospectiva y escenarios, periodismo de verificación.
- **Marco:** cibernética, filosofía de la ciencia (conciliencia), y señales y control.

**Pregunta de investigación propuesta:**

> ¿La dialéctica humano-IA estructurada amplía la detección de patrones en información abierta (conciliencia genuina) sin aumentar en la misma medida los patrones falsos (falsa conciliencia)?
