# Diseño del experimento A/B — S16

> **ESTADO: CONGELADO el 1 de noviembre de 2026** (etiqueta `diseno-ab-2026-11-01`), después de dos rondas de revisión externa de ChatGPT y de la aprobación del operador, con la declaración de la sección 10. Lo redactó Claude. El borrador anterior está en el commit `0defe5e`.
> **Se congela junto con** [ab-s16/preguntas-comunes.md](ab-s16/preguntas-comunes.md). Ninguno de los dos se edita más; las correcciones van en un documento nuevo, con fecha.
> **Relación con el prerregistro:** es la extensión prevista en la sección 1 de [protocolo-evaluacion-cierre-2026.md](protocolo-evaluacion-cierre-2026.md). **No lo modifica**: no cambia ninguna de sus reglas, umbrales ni pronósticos. **Ninguna métrica ni resultado de este experimento entra en la aplicación de H-1 a H-4 ni de V-1 y V-2**; se reporta en una sección separada.

---

## 0. Propósito y alcance

El prerregistro declara que "no tiene un brazo humano solo ni IA sola". Este experimento agrega un brazo **"Claude solo"** y compara, con la misma fecha de corte, lo que produce Claude sin el operador frente a lo que produce el protocolo completo.

**En lenguaje llano:** ¿la salida del protocolo completo cubre hechos que Claude solo no cubre, sin más errores?

**Qué estima y qué no:**
- Estima la diferencia entre **dos procesos** con insumos distintos: A no tiene los hechos del operador ni el diálogo; B tiene los dos, y además el conocimiento acumulado del operador. **No estima el efecto aislado del diálogo**, ni separa el aporte de los hechos del operador del aporte del diálogo.
- Es un **estudio de caso exploratorio y generador de hipótesis** (n = 1). **No es un ensayo aleatorizado**: los brazos se corren en orden fijo, A y después B. El sorteo de las etiquetas X/Y (sección 8) solo oculta los nombres de las salidas ante Gemini.

## 1. Pregunta e hipótesis

> **¿La salida del protocolo SEG completo (brazo B) cubre más hechos relevantes verificados y pronostica mejor que la de Claude solo (brazo A), con la misma fecha de corte, los mismos bloques de fuentes obligatorios y las mismas preguntas, sin una tasa de errores mayor?**

- **H-AB1 (cobertura):** B tiene más hechos relevantes verificados **exclusivos** que A (se lee con R-4 y R-4A).
- **H-AB2 (errores):** la tasa de errores de B no es mayor que la de A (R-5). Se lee siempre junto a la proporción de hechos que cada brazo marcó ✅.
- **H-AB3 (pronóstico):** sobre las mismas preguntas, B tiene menor Brier que A **y** gana en más preguntas (R-1).
- **H-AB4 (conciliencia, descriptiva):** las predicciones de patrón de cada brazo, evaluadas **por separado**, le ganan a decir siempre 50%. No se comparan entre brazos, porque cada uno escoge las suyas.

## 2. Brazos

| | Brazo A — Claude solo | Brazo B — protocolo completo |
|---|---|---|
| Procedimiento | SEG v1.0 ([especificacion-protocolo.md](especificacion-protocolo.md)) **sin** E1 (no hay hechos del operador) y sin diálogo | SEG v1.0 completo: es la S16 normal |
| Quién interviene | Claude. El operador solo pega el mensaje fijo (anexo A), aprueba los permisos y, si la sesión se detiene, escribe únicamente "Continúa." | El operador y Claude |
| Dónde | Una **copia aparte** del repositorio, sin historial de git (sección 4 y anexo C) | El repositorio principal, en una sesión nueva de Claude Code |
| Insumos permitidos (lista positiva) | CLAUDE.md (versión reducida, sección 4), `simulaciones/2026-10-09-sesion-15-seguimiento-extraoficial.md`, README.md, `investigacion/especificacion-protocolo.md`, `investigacion/protocolo-evaluacion-cierre-2026.md` e `investigacion/ab-s16/preguntas-comunes.md`. **Ningún otro archivo** | **Los mismos**, con CLAUDE.md completo, **más la lista del operador**. Ningún otro archivo |
| Fuentes | Los 8 bloques obligatorios de `preguntas-comunes.md`, más las fuentes que Claude agregue | Los mismos bloques, más las fuentes que agreguen Claude o el operador. Las del operador son parte del tratamiento: **no son una violación**, y su procedencia se registra en el cuerpo de la S16 (etapa E4 de SEG) |
| Parada de la búsqueda propia de Claude | Criterio de SEG §6: cuando las búsquedas ya no devuelven hechos nuevos relevantes | **El mismo criterio.** En B se suprime la salida "o cuando el operador lo indica" para la búsqueda propia de Claude |
| Modelo | La misma opción de modelo de Claude en ambos brazos, en Claude Code con búsqueda web. Se registran el identificador expuesto, la fecha y la hora. No se puede garantizar que el modelo sea idéntico entre días | Ídem |
| Salida | `salida.md` en la copia; se archiva como `investigacion/ab-s16/brazo-a.md` | `simulaciones/YYYY-MM-DD-sesion-16-seguimiento-extraoficial.md` |

Ambas salidas terminan con el **anexo estándar** y la **hoja de ejecución** de `preguntas-comunes.md`, con el mismo formato.

**Violación del protocolo** (en cualquier brazo): dejar sin cubrir un bloque obligatorio, abrir un archivo fuera de la lista positiva o usar una noticia publicada después de C. Se registra en la hoja de ejecución y en el informe.

**Esfuerzo:** no está controlado experimentalmente. B puede encontrar términos de búsqueda gracias al operador y extender la búsqueda. Se registra en la hoja de ejecución (duración, búsquedas, fuentes), y ninguna diferencia de cobertura se atribuye automáticamente a una mejor capacidad de encontrar hechos.

## 3. Fecha de corte, orden y fallos

- **Fecha de corte (C):** el día en que se corre el brazo A, entre el 5 y el 10 de noviembre de 2026. Se registra en el commit del brazo A.
- **Ninguno de los dos brazos usa noticias publicadas después de C.**
- **La contaminación posterior a C es una amenaza primaria**, no una limitación menor. B dura varios días, y el operador y Claude pueden enterarse de hechos posteriores a C que influyan en la selección o en las probabilidades sin citarse. Solo se controla la evidencia citada, no todo lo que saben los participantes. B registra en su hoja de ejecución cualquier conocimiento posterior a C que detecte.
- **Orden:**
  1. Congelar este documento y `preguntas-comunes.md`.
  2. El día C, preparar la copia del brazo A y tomar las huellas de la memoria (anexo C).
  3. Correr el brazo A en una **sesión nueva** de Claude Code abierta en la copia.
  4. Tomar de nuevo las huellas de la memoria, archivar `brazo-a.md` y hacer commit **antes** de que empiece B.
  5. Recién entonces el operador muestra su lista y empieza la S16 (brazo B), en una sesión nueva.
- **Fallos (regla común a los dos brazos):** si la sesión se corta y se puede continuar, se escribe "Continúa." y sigue. Si no se puede continuar, el brazo se repite **una vez** desde el principio, con los mismos insumos, y se declara; entra al análisis la repetición. Si vuelve a fallar, ese brazo se declara nulo y el experimento también.

## 4. Aislamiento

- **El brazo A no ve la lista del operador.** La lista no se escribe en el repositorio, en la memoria de Claude ni en CLAUDE.md antes de que A tenga commit.
- **El brazo A se corre en una copia aparte** (anexo C), creada con `git archive` (sin historial de git), en una carpeta distinta. La memoria de Claude Code depende de la carpeta del proyecto, así que la copia arranca **sin memoria**. En la copia se borran todos los archivos de `investigacion/` y `prompts/` que no están en la lista positiva. Eso incluye este diseño y [linea-base-k26n-2026-10.md](linea-base-k26n-2026-10.md), que contiene la filtración conocida de tres temas del operador.
- **CLAUDE.md reducido:** en la copia, CLAUDE.md es la versión del repositorio principal en la fecha C **sin** las líneas y oraciones que mencionan el experimento A/B, sus brazos o la carpeta `ab-s16`. **No se borra ninguna otra instrucción**: las reglas de los seguimientos se mantienen. El diff se guarda en `investigacion/ab-s16/claude-md-brazo-a.diff` y solo puede contener eliminaciones. Es una **reducción de las expectativas experimentales**, no un cegamiento: el prerregistro, que es insumo de los dos brazos, menciona en una oración la posibilidad de un experimento A/B, y A podría inferirlo de su situación.
- **Asimetría declarada:** el brazo B no se puede enmascarar; el operador y Claude saben que es B.
- **Contaminación A→B:** antes y después de correr A, se calcula la huella SHA-256 de **cada archivo** de la carpeta de memoria del proyecto principal (`C:\Users\Usuario\.claude\projects\d--experimento-iran-conflict-model\memory\`). Se comprueba también que la carpeta de memoria de la copia no existía antes de A. Las dos listas se guardan en `investigacion/ab-s16/`. Si alguna huella cambia, se declara contaminación posible.
- **El brazo B no ve el brazo A.** `brazo-a.md` se copia al repositorio principal y se hace commit sin abrirlo ni mostrar su contenido. El operador no lo lee hasta que la S16 tenga commit, y Claude no lo abre durante la S16.
- **Lo que no se puede inspeccionar:** la configuración global de Claude Code (`settings.json`, compartida por las dos sesiones; hoy no existe un CLAUDE.md global) y cualquier mecanismo del servicio fuera de la máquina del operador. No se afirma un aislamiento completo.
- **Filtración conocida:** los hechos que derivan de los tres temas de la sección 5 de `linea-base-k26n-2026-10.md` (Lula, las protestas en Europa y Starlink en Ucrania) se marcan como **potencialmente contaminados** y **no cuentan como exclusivos de ningún brazo**; se reportan aparte.
- **Categorías de contaminación**, que se juzgan después de los dos brazos para tres vías (A→B, posterior a C, filtración): **sin evidencia / posible / confirmada**. Si una vía queda confirmada, los resultados se conservan, pero la comparación afectada se declara **inválida como lectura causal**.

## 5. Preguntas que pronostican los dos brazos

Las preguntas y sus reglas de resolución están en la sección 3 de [ab-s16/preguntas-comunes.md](ab-s16/preguntas-comunes.md). Se puntúa el número que el brazo marque como punto; si solo da un rango, su punto medio (regla de la sección 6.1 del prerregistro).

- **Q1 a Q5** reproducen las reglas de los ítems 3.2 a 3.6 del prerregistro, y **Q6** la de P-2.
- **Q7 y Q8 son preguntas nuevas, derivadas de T1 y de K26-T.** Reutilizan sus definiciones, pero **no sus ventanas**: empiezan el día siguiente a C, porque nadie puede pronosticar lo que ya ocurrió al momento del corte. **Sus resultados nunca se usan para calificar T1 ni K26-T.**
- El ítem 3.1 no entra: ya estará resuelto en C. Los rangos de escenarios A–F no se puntúan; se reporta su entropía.

## 6. Qué se mide

### 6.1 Métricas

| Métrica | Qué se reporta |
|---|---|
| **M-AB1. Cobertura** | Total de hechos relevantes verificados de A y de B, compartidos, **exclusivos de A y exclusivos de B** (métrica primaria), y por separado los de relevancia D y P y los potencialmente contaminados. Un exclusivo es **cobertura diferencial de las salidas**, no un descubrimiento: no dice quién encontró primero el hecho ni por qué vía. Las diferencias de detalle en los hechos compartidos se anotan aparte |
| **M-AB2. Errores** | Por brazo: hechos presentados, hechos ✅, **proporción de ✅**, errores y **tasa = errores / hechos ✅** (con numerador y denominador). Tasa = NA si el brazo no tiene hechos ✅. Se lee siempre junto a la cobertura y a la proporción de ✅, porque marcar menos hechos como verificados puede bajar la tasa |
| **M-AB3. Pronóstico** | Brier por pregunta y por brazo, Brier medio, ΔBrier = Brier(A) − Brier(B), y preguntas ganadas, perdidas y empatadas. **Sensibilidad** (solo descriptiva): ΔBrier sin Q7, ΔBrier sin Q8 (pueden contar dos veces el mismo ataque) e intervalo por *bootstrap* |
| **M-AB4. Conciliencia** | Por brazo, por separado: las 3 predicciones de patrón con su estado, el número de evaluables y su Brier medio frente a 0,25 |
| **M-AB5. Entropía** | Entropía de Shannon de los escenarios A–F de cada brazo. Solo se reporta |

### 6.2 Rúbricas para el evaluador

**Unidad de conteo (un hecho):** mismo actor principal + misma acción + misma fecha, con ±3 días de margen.
- Si un brazo parte un hecho en varias filas, el evaluador las **fusiona** antes de contar.
- Si los dos brazos tienen el mismo hecho con distinto detalle, es **compartido**, y la diferencia de detalle se anota.
- **Ejemplos** (ilustrativos e inventados; no son hechos verificados). (a) "Irán ejecuta a tres manifestantes el 20 oct" y "Teherán ahorca a 3 detenidos por las protestas, 21 oct": **el mismo hecho**. (b) "EEUU sanciona a cinco navieras iraníes (OFAC), 15 oct" y "EEUU sanciona a la refinería X, 15 oct": **hechos distintos** (otra acción concreta). (c) "Ataque hutí contra el aeropuerto de Abha, 12 oct" en un brazo, y en el otro "ataques hutíes contra aeropuertos saudíes, 10–21 oct": **compartido**, con la diferencia de detalle anotada.

**Verificado:** el evaluador **comprueba por su cuenta** que las dos fuentes citadas sostienen el hecho y son de bloques distintos. Un enlace que no abre y no tiene copia archivada vuelve el hecho "no comprobable": no cuenta en la cobertura y tampoco como error; se reporta aparte.

**Relevante:**
- **D (directa):** el hecho trata de un evento que forma parte de la regla de resolución de una pregunta Q1–Q8 o de la definición de un escenario A–F.
- **P (predictiva):** el brazo explica en una frase cómo el hecho cambia la probabilidad de una pregunta o un escenario, y el evaluador juzga si esa conexión es **explícita y sustentada** por el hecho. **No juzga si resultó acertada.**
- Si no es D ni P, no es relevante. Los dos tipos cuentan en la cobertura y se reportan por separado.

**Error** (solo en hechos marcados ✅), con una lista cerrada:
1. La fuente no sostiene el hecho.
2. Actor o sujeto equivocado.
3. Fecha equivocada (difiere de las fuentes en más de 1 día, o el hecho queda fuera de la ventana).
4. Magnitud equivocada (cifras, número de víctimas, montos).
5. Afirmación más fuerte que lo que dicen las fuentes.
6. Marcado ✅ sin dos fuentes de bloques distintos.

Las inferencias analíticas no se califican como errores.

**Predicción de patrón:** cuenta si predice **hechos distintos de los que la originaron** (definición de conexión del prerregistro, sección 1) y si su comprobación de novedad dice que no está en la S15 ni en los insumos permitidos. Si una predicción no cumple estas condiciones, se reporta como "no válida" y no entra al Brier.

### 6.3 Especificación del cálculo

Se congela con este documento. El código, que puede escribirse después, **solo implementa esta especificación** y tiene que reproducir los casos de prueba de la tabla de abajo antes de usarse con datos reales.

1. **Resultado de cada pregunta:** 1 (Sí), 0 (No) o indeterminada (sin dos fuentes de bloques distintos). Una pregunta indeterminada se excluye de **ambos** brazos.
2. **p:** el punto del brazo, o el punto medio de su rango si solo dio un rango. **Si un brazo no da pronóstico en una pregunta, se le asigna p = 0,5** y se declara.
3. **Brier por pregunta:** (p − resultado)². **Brier medio:** el promedio sobre las preguntas evaluables. Se calcula con precisión completa y se reporta con 3 decimales.
4. **Ganador por pregunta:** el brazo con menor Brier en esa pregunta. Hay **empate** si la diferencia es menor que 10⁻⁹.
5. **ΔBrier** = Brier medio(A) − Brier medio(B). Si es positivo, B tuvo mejor Brier.
6. **Mínimo:** si hay menos de **5** preguntas evaluables, R-0 (sección 7).
7. **Sensibilidad:** ΔBrier recalculado sin Q7 y, por separado, sin Q8, si son evaluables. *Bootstrap* pareado: 10 000 remuestreos con reposición de las preguntas evaluables, generador `numpy.random.default_rng(20261105)`, intervalo de percentiles 2,5–97,5. **Solo se reporta; no decide ninguna fila.**
8. **M-AB2:** tasa = errores / hechos ✅; NA si hay 0 hechos ✅. Se reportan numerador, denominador y la diferencia de tasas B − A.
9. **M-AB4:** Brier medio de las predicciones de patrón válidas y evaluables de cada brazo. Si tiene menos de **2**, NA. Siempre se reportan las 3 predicciones originales, su estado y el denominador efectivo.
10. **M-AB5:** H = −Σ pᵢ log₂ pᵢ, con los puntos de A–F normalizados para que sumen 1; se omiten los términos con p = 0.

**Casos de prueba** (Q1…Q8 en orden; "—" = sin pronóstico; "ind." = indeterminada):

| Caso | p de A | p de B | Resultados | Resultado esperado |
|---|---|---|---|---|
| T-1 | 0,2 · 0,1 · 0,5 · 0,2 · 0,2 · 0,3 · 0,4 · 0,6 | 0,1 · 0,1 · 0,6 · 0,2 · 0,1 · 0,2 · 0,6 · 0,7 | 0 0 1 0 0 0 1 1 | Brier A = 0,124; B = 0,065; Δ = 0,059; B gana 6, A gana 0, 2 empates → **R-1**. Sin Q7: Δ = 0,039. Sin Q8: Δ = 0,057 |
| T-2 | T-1 con A y B intercambiados | | 0 0 1 0 0 0 1 1 | Δ = −0,059; A gana 6, B gana 0 → **R-2** |
| T-3 | 0,1 · 0,1 · 0,1 · 0,1 · 0,1 · 0,9 · 0,9 · 0,1 | 0,15 · 0,15 · 0,15 · 0,15 · 0,15 · 0,85 · 0,85 · 0,6 | 0 0 0 0 0 1 1 1 | Brier A = 0,110; B = 0,040; Δ = 0,070, pero A gana 7 y B gana 1 → **R-3** (los dos criterios discrepan) |
| T-4 | igual que T-1 | igual que T-1 | 0 ind. 1 ind. ind. ind. 1 1 | 4 evaluables → **R-0** |
| T-5 | 0,3 · — · 0,5 · 0,2 · 0,2 · 0,3 · 0,4 · 0,6 | 0,3 · 0,2 · 0,6 · 0,2 · 0,1 · 0,2 · 0,6 · 0,7 | 0 0 1 0 ind. 0 1 1 | A recibe 0,5 en Q2; 7 evaluables; Brier A = 0,177; B = 0,089; Δ = 0,089; B gana 5, 2 empates → **R-1** |
| T-6 | Patrones: p = 0,7 · 0,3 · 0,6 | | 1 0 0 | M-AB4 = 0,180 (n = 3) |
| T-7 | Patrones: p = 0,9 · 0,8 · 0,2 | | 0 1 ind. | M-AB4 = 0,425 (n = 2) |
| T-8 | Patrones: p = 0,7 · 0,3 · 0,6 | | 1 ind. ind. | NA (n = 1) |
| T-9 | Escenarios: 0,50 · 0,20 · 0,10 · 0,10 · 0,05 · 0,05 | | — | H = 2,061 bits |

## 7. Tabla de decisión

Se aplica tal cual en enero de 2027, con la calificación de **cada evaluador por separado**. Los umbrales (5 de 8, 2 de 3, ≥3) son **convencionales**, recomendados por Claude, que produce los dos brazos; el operador declaró que no tiene la formación para fijarlos (prerregistro, sección 10). Los conteos y los valores se publican siempre, se cumpla o no una fila.

| # | Si… | Conclusión que se publica |
|---|---|---|
| R-0 | Hay menos de 5 preguntas Q1–Q8 evaluables | **Comparación de pronóstico no evaluable.** No se aplican R-1 a R-3 |
| R-1 | ΔBrier > 0 **y** B gana en más preguntas que A | **En estas preguntas, B obtuvo mejor Brier** (señal descriptiva, no estadística) |
| R-2 | ΔBrier < 0 **y** A gana en más preguntas que B | **En estas preguntas, A obtuvo mejor Brier** (ídem) |
| R-3 | Ninguna de las anteriores, con ≥5 evaluables | **Sin diferencia clara en pronóstico.** Es una convención conservadora: exige que el Brier medio y las preguntas ganadas coincidan. **No significa igualdad**; puede haber una ventaja en un criterio y no en el otro (caso T-3) |
| R-4 | B tiene **≥3** exclusivos relevantes verificados **y** más exclusivos que A | **En esta sesión, la salida de B cubrió más hechos que la de A** (cobertura diferencial, no descubrimiento) |
| R-4A | A tiene **≥3** exclusivos relevantes verificados **y** más exclusivos que B | **En esta sesión, la salida de A cubrió más hechos que la de B** (ídem) |
| R-5 | La tasa de errores de B es mayor que la de A | **Aumento observado de errores en B**, con numeradores, denominadores y la proporción de ✅ de cada brazo. No es un efecto causal |
| R-5A | La tasa de errores de A es mayor que la de B | **Aumento observado de errores en A** (ídem) |
| R-6 | Para cada brazo, con ≥2 predicciones de patrón evaluables: Brier > 0,25, = 0,25 o < 0,25 | **Peor que**, **igual a** o **mejor que** decir siempre 50%, para ese brazo. Con menos de 2: no evaluable. **Los brazos no se comparan entre sí** en esta fila, porque cada uno escogió sus predicciones. No se traduce a "mayormente falsa conciliencia" |

**Lectura combinada:** R-4 sin R-5 → "B amplió la cobertura sin un aumento observado de errores". R-4 con R-5 → "B amplió la cobertura, con un aumento observado de errores". R-4A → "Claude solo cubrió más". Ni R-4 ni R-4A → "sin diferencia clara de cobertura". Si se cumplen filas contradictorias, se reportan todas.

## 8. Calificación

- **Dos evaluadores, por separado:** el operador y Gemini. Gemini trabaja en una Gem nueva, distinta de la del prerregistro, con las instrucciones del **anexo B** sin modificar. Las dos evaluaciones se publican completas; **no se combinan en un consenso**.
- **Paquete cerrado para Gemini:** este documento congelado, `preguntas-comunes.md`, los anexos estándar de los dos brazos con las etiquetas X e Y (sin la hoja de ejecución, que revela la duración) y el expediente de resolución. Nada más.
- **Enmascaramiento de etiquetas** (no cegamiento del tratamiento): después de cerrar los dos brazos y antes de preparar el paquete, **el operador lanza una moneda una sola vez**. Si sale cara, B = X; si sale sello, B = Y. El resultado se anota en `investigacion/ab-s16/clave-xy.md`, que Gemini no recibe. Se declara que el operador podría repetir el lanzamiento sin que nadie lo note; lo que está en juego es poco. Antes de calificar, Gemini dice si cree poder inferir cuál es B y con qué confianza; esa respuesta se archiva.
- **El operador no puede estar ciego**, porque participó en B; se declara.
- **Expediente de resolución de Q1–Q8 y de las predicciones de patrón:** Claude corre las **búsquedas fijas del anexo D**, tal cual, entre el 3 y el 10 de enero de 2027, y archiva **todos** los resultados (título, medio, bloque, fecha, enlace y cita textual), también los contradictorios y las búsquedas sin resultados. Claude no agrega conclusiones ni descarta resultados. Para las predicciones de patrón, cuyas reglas no se conocen hoy, se usa el mismo procedimiento: los términos se toman literalmente de la regla de resolución de cada predicción. Gemini puede buscar por su cuenta y declarar "evidencia insuficiente". Para auditar los hechos se usan las fuentes que citan los propios anexos.
- **Titular:** si los evaluadores discrepan en una fila, el titular usa la lectura menos favorable al brazo B. Es una **regla nueva de este experimento**, inspirada en la del prerregistro ("la menos favorable al método"), y se aplica **solo al titular**; debajo se muestra la conclusión de cada evaluador.
- **El cálculo se hace con código** que implementa la sección 6.3. Claude puede programarlo, pero **no califica** cobertura, relevancia, equivalencias ni errores.

## 9. Limitaciones y conflictos declarados

- **n = 1:** una sesión por brazo, un operador, un modelo. El resultado es una **señal, no una prueba**. No es un ensayo aleatorizado.
- **El estimando es la diferencia entre dos procesos**, no el efecto del diálogo: B también tiene el conocimiento previo del operador.
- **La contaminación posterior a C** es la amenaza principal y solo se controla en la evidencia citada (sección 3).
- **El esfuerzo no está controlado**; solo se registra.
- **Las preguntas están correlacionadas** (Q7 y Q8 pueden resolverse por el mismo ataque), y las indeterminadas pueden no ser aleatorias: suelen ser los eventos más ambiguos. Las excluidas se listan con su razón.
- **Claude produce los dos brazos, sabe cuál es cuál, redactó este diseño y corre las búsquedas del expediente.** Las salvaguardas son la lista positiva de insumos, el CLAUDE.md reducido, la regla de parada común, las búsquedas fijas congeladas y la revisión externa. Ninguna elimina el conflicto.
- **El brazo A sigue reglas escritas por el operador y Claude** (SEG, los bloques, CLAUDE.md). No mide "Claude sin ninguna influencia humana", sino Claude sin los hechos y sin el diálogo **de esta sesión**.
- **El aislamiento no es completo** (sección 4).
- **Revisión por otra IA:** ChatGPT y Claude pueden compartir sesgos por su entrenamiento. Que ChatGPT esté de acuerdo no valida el diseño. Además, la revisión no se hizo en un chat temporal, sino dentro de un proyecto de ChatGPT (sección 10).

## 10. Revisión externa y trazabilidad

- **Revisor:** ChatGPT (OpenAI), **GPT-5.6 Sol**, razonamiento "Media", el 1 nov 2026, en lugar de Gemini, para que Gemini siga siendo solo evaluador. **Desviación:** la revisión se hizo dentro del proyecto de ChatGPT "ensayos", creado por el operador para esto, y no en un chat temporal.
- **Material que recibió:** el borrador (commit `0defe5e`) y el prerregistro congelado. **No recibió la lista de hechos del operador.**
- **Archivo completo:** [prompts/2026-10-31/P1-revision-chatgpt-diseno-ab.md](../prompts/2026-10-31/P1-revision-chatgpt-diseno-ab.md), con las dos respuestas de ChatGPT sin editar y la réplica de Claude, que el operador aprobó sin cambios antes de enviarla.
- **Resultado:** dos rondas, el máximo previsto. En la ronda 1, Claude aceptó la mayoría de las observaciones y aceptó en parte seis. En la ronda 2, ChatGPT aceptó tres de esas seis réplicas (1.3, 1.5 y 3.4) y mantuvo las otras tres (1.4, 2.3 y 4.3); Claude aceptó su posición en las tres.

**Desacuerdos declarados, decididos por el operador (1 nov 2026):**

| # | Propuesta de ChatGPT | Por qué no se aplica tal cual | Decisión |
|---|---|---|---|
| D-1 | Asignar X/Y una sola vez con una fuente de azar independiente | Era una elección de procedimiento: el hash del commit quedó descartado | Una moneda, lanzada una sola vez por el operador (sección 8) |
| D-2 | Que el expediente de resolución lo prepare alguien que no sepa qué brazo favorece cada resolución | Imposible: Claude y el operador conocen los pronósticos de los dos brazos | Búsquedas fijas congeladas (anexo D) |

**Aprobación del operador (1 nov 2026)**, con esta declaración textual: *"Es mas de lo que este operador puede manejar, ya el analisis se hara luego con calma, lo importante es que hayan registros de trasabilidad para auditar hasta errores si se comenten"*. Es decir: el operador aprobó la versión ajustada sin poder revisarla a fondo, igual que con el prerregistro (sección 10 de ese documento). Las salvaguardas que quedan son la trazabilidad (esta sección, el archivo de la revisión y los commits) y la auditoría posterior. Es otro caso del sesgo de automatización que estudia la investigación, y se declara como tal.

**Cambios por la revisión** (R1 = ronda 1, R2 = ronda 2; el número es la fila de la sección correspondiente de ChatGPT):

| Sección | Cambio | Origen |
|---|---|---|
| 0, 1, 9 | El estimando es la diferencia entre dos procesos; no es un ensayo aleatorizado | R2 (c, advertencia sobre X/Y) |
| 1 | H-AB1 se redacta sobre exclusivos; H-AB4 es descriptiva por brazo | R1 3.5, 2.7 |
| 2 | Lista positiva idéntica de insumos; las fuentes del operador no son violación; violación = omitir un bloque, abrir un archivo no permitido o usar noticias posteriores a C | R1 1.3, 1.6; R2 a 1.3 |
| 2 | Parada común de la búsqueda propia de Claude; esfuerzo declarado como no controlado y registrado | R1 1.4; R2 a 1.4 |
| 2 | "Misma opción de modelo", con identificador, fecha y hora | R1 4.1 |
| 3 | La contaminación posterior a C es amenaza primaria; registro en la hoja de ejecución | R1 1.1, 4.2 |
| 3 | Regla de fallos común a los dos brazos | R1 1.8, 4.6 |
| 4, anexo C | Copia aparte sin historial ni memoria, huellas SHA-256 de la memoria, CLAUDE.md reducido con diff de solo eliminaciones, mecanismos no inspeccionables declarados | R1 1.2, 1.5; R2 b |
| 4 | Hechos de la filtración conocida: potencialmente contaminados, no exclusivos | R1 1.7 |
| 4 | Categorías de contaminación: sin evidencia, posible, confirmada | R1 6 |
| 5 | Q7 y Q8 son preguntas nuevas derivadas; nunca califican T1 ni K26-T | R1 5.1, 5.2 |
| 6.1 | M-AB1 desglosado; exclusivo = cobertura diferencial, no descubrimiento | R1 2.1; R2 c |
| 6.1 | M-AB2 se reporta con la proporción de ✅ | R2 c |
| 6.1 | Sensibilidad sin Q7 y sin Q8; el *bootstrap* solo es descriptivo | R1 2.6; R2 c |
| 6.2 | Rúbricas de unidad, equivalencia, verificado, relevancia D y P, error y predicción de patrón | R1 2.2, 2.3, 2.4, 2.8, 6; R2 a 2.3 |
| 6.3 | Especificación del cálculo con casos de prueba, congelada antes de los brazos | R1 4.3; R2 a 4.3 |
| 7 | R-0, R-1 a R-3 sin intervalo, R-4A, R-5A, estados completos de R-6; umbrales declarados como convencionales | R1 3.1–3.8; R2 b |
| 8 | Paquete cerrado, enmascaramiento de etiquetas, sorteo con moneda, expediente con búsquedas fijas, titular solo como regla nueva del A/B, evaluaciones publicadas por separado | R1 2.10, 2.11, 4.5, 5.4, 6; R2 b, c; D-1, D-2 |
| Encabezado | Ningún resultado del A/B entra en H-1 a H-4 ni en V-1 y V-2 | R1 5.5 |
| Anexo B | Instrucciones fijas para Gemini | R1 6 |

---

## Anexo A. Mensaje fijo para el brazo A

Se pega tal cual en una **sesión nueva** de Claude Code, abierta en la carpeta de la copia (anexo C), reemplazando solo `[C]` por la fecha de corte:

```text
Vas a producir un seguimiento extraoficial del ICM sin hechos aportados por el
operador y sin diálogo.

Fecha de corte: [C]. No uses noticias publicadas después de esa fecha.

Sigue el protocolo SEG v1.0 (investigacion/especificacion-protocolo.md), con
estas diferencias: no hay etapa E1 (no hay hechos del operador) ni diálogo, y no
hay commit. Tú decides las búsquedas. Los bloques de fuentes, la regla de
verificación, el criterio de parada, las preguntas que debes pronosticar y el
formato de salida están en investigacion/ab-s16/preguntas-comunes.md.

Insumos permitidos (solo estos): CLAUDE.md,
simulaciones/2026-10-09-sesion-15-seguimiento-extraoficial.md, README.md,
investigacion/especificacion-protocolo.md,
investigacion/protocolo-evaluacion-cierre-2026.md e
investigacion/ab-s16/preguntas-comunes.md. No abras ningún otro archivo.

No le hagas preguntas al operador. Si tienes una duda, decide y declara la
decisión. Trabaja hasta cumplir el criterio de parada, con el mismo cuidado que
en un seguimiento normal.

Escribe un solo archivo, salida.md, en la raíz de esta carpeta, con: estado al
corte, hechos verificados (✅/🟡/⚪), análisis por capas, escenarios A–F con
rango y punto, entropía, contraste externo (K17), autocrítica de la S15 y, al
final, el anexo estándar y la hoja de ejecución de preguntas-comunes.md. No
edites ningún otro archivo, no escribas en la memoria y no hagas commit.
```

## Anexo B. Instrucciones fijas para Gemini (enero de 2027)

Se crea una Gem nueva. Sus instrucciones son el texto de abajo, sin cambios. Sus archivos de conocimiento son los del paquete cerrado (sección 8). El primer mensaje es: "Califica el experimento siguiendo tus instrucciones."

```text
Eres el evaluador independiente de un experimento que compara dos salidas,
X e Y, de un seguimiento de un conflicto geopolítico. Las reglas están en el
diseño congelado (diseno-experimento-ab.md, secciones 6 y 7) y en
preguntas-comunes.md. Aplícalas tal cual. No calcules las filas de la tabla de
decisión: entrega solo las tablas pedidas; el cálculo se hace aparte.

Paso 0. Antes de calificar: ¿crees poder inferir cuál de X e Y es el
"protocolo completo" (con un operador humano)? Responde sí o no, cuál y con
qué confianza (0–100%), y por qué, en dos líneas.

Paso 1. Hechos. Para cada fila de la tabla 2 de X y de Y marcada ✅: comprueba
tú mismo que las dos fuentes sostienen el hecho y son de bloques distintos.
Clasifícalo: verificado / no comprobable (el enlace no abre) / error (tipo 1 a 6
de la sección 6.2). Indica la relevancia (D, P o no relevante) según la
sección 6.2. Marca los hechos que derivan de Lula, las protestas en Europa o
Starlink en Ucrania.

Paso 2. Equivalencias. Fusiona las filas que son el mismo hecho dentro de cada
salida y empareja los hechos de X con los de Y, con la regla y los ejemplos de
la sección 6.2. Entrega una tabla: hecho | fila(s) en X | fila(s) en Y |
compartido / exclusivo de X / exclusivo de Y | diferencia de detalle.

Paso 3. Preguntas Q1–Q8. Con el expediente de resolución y, si hace falta, tu
propia búsqueda: resultado 1, 0 o indeterminada (sin dos fuentes de bloques
distintos), con las fuentes. Puedes declarar "evidencia insuficiente".

Paso 4. Predicciones de patrón (tabla 3 de cada salida). Para cada una: ¿es
válida (predice hechos distintos de los que la originaron y es nueva)? Si lo
es, resultado 1, 0 o indeterminada, con las fuentes.

Formato: una tabla por paso. No escribas conclusiones generales. Si una regla
no alcanza para decidir un caso, dilo y explica cómo lo decidiste.
```

## Anexo C. Procedimiento del día C para el brazo A

Lo ejecuta Claude desde el repositorio principal, con la aprobación del operador, **antes** de que este muestre su lista. Cada paso deja un archivo en `investigacion/ab-s16/`.

1. **Huellas antes:** SHA-256 de cada archivo de `C:\Users\Usuario\.claude\projects\d--experimento-iran-conflict-model\memory\` → `huellas-memoria-antes.txt`. Se comprueba que no existe la carpeta de memoria correspondiente a la copia.
2. **Copia:** `git archive HEAD` del repositorio principal, ya con el diseño congelado y con CLAUDE.md en commit, extraído en `D:\experimento\icm-ejecucion-c\` (sin `.git`).
3. **Limpieza de la copia:** se borran de `investigacion/` y `prompts/` todos los archivos que no están en la lista positiva. La lista de borrados se guarda en `copia-borrados.txt`.
4. **CLAUDE.md reducido:** se eliminan solo las líneas y oraciones que mencionan el experimento A/B, sus brazos o `ab-s16`. El diff, que solo puede contener eliminaciones, se guarda en `claude-md-brazo-a.diff`.
5. **Ejecución:** el operador abre `D:\experimento\icm-ejecucion-c\` en VS Code, inicia una sesión nueva de Claude Code, pega el mensaje del anexo A, aprueba los permisos y solo escribe "Continúa." si la sesión se detiene. Al terminar, cierra esa sesión.
6. **Huellas después:** igual que el paso 1 → `huellas-memoria-despues.txt`, y se comparan.
7. **Archivo:** `salida.md` se copia a `investigacion/ab-s16/brazo-a.md` **sin abrirlo**, y se hace commit con la aprobación del operador. Recién entonces empieza B.

## Anexo D. Búsquedas fijas para el expediente de resolución

Se corren entre el 3 y el 10 de enero de 2027, tal cual, con la herramienta de búsqueda web de Claude. Cada búsqueda en inglés se repite en español. Se archivan **todos** los resultados de las dos primeras páginas, o los 10 primeros si no hay páginas. Si una búsqueda no devuelve nada del bloque indicado, se repite **una vez** agregando el nombre de un medio de ese bloque, y se registra.

| Pregunta | Búsquedas (en inglés; se repiten en español) | Bloques que deben aparecer |
|---|---|---|
| Q1 | "US Iran nuclear agreement text IAEA verification sanctions relief" con "December 2026" y con "November 2026" | 1, 2, 5 |
| Q2 | "Iran nuclear test"; "Iran nuclear weapon DNI assessment 2026"; "IAEA Iran weapon assessment December 2026" | 1, 2, 5 |
| Q3 | "Israel prime minister December 31 2026"; "Netanyahu prime minister government coalition December 2026" | 1, 6 |
| Q4 | "BEA GDP third quarter 2026 advance estimate"; "NBER recession 2026" | 2, 1 |
| Q5 | "Israel annexation Lebanon territory 2026"; "Lebanon government cabinet collapse December 2026" | 1, 4, 6 |
| Q6 | "US airstrikes Yemen support Saudi offensive 2026"; "Pentagon confirms strikes Yemen Saudi coalition" | 1, 2, 4 |
| Q7 | "US strike Iran territory" e "Israel strike Iran", cada una con "November 2026" y con "December 2026" | 1, 2, 5, 6 |
| Q8 | Las de Q7 más "Trump ultimatum Iran deadline" con "November 2026", con "December 2026" y con "January 2027" | 1, 2, 5 |
| Patrones | Por cada predicción: los actores, la acción y el periodo, tomados literalmente de su regla de resolución | Los de la regla |
