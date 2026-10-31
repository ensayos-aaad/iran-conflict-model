# Diseño del experimento A/B — S16

> **ESTADO: BORRADOR del 31 de octubre de 2026.** Lo redactó Claude. Falta la revisión externa de ChatGPT (sección 10), la revisión del operador y el congelamiento.
> **Congelamiento:** un commit con la etiqueta `diseno-ab-2026-11-04` (o la fecha real), **antes de que empiece la S16**, es decir, antes de que el operador muestre su lista de hechos. Después de congelado, este archivo no se edita; las correcciones van en un documento nuevo, con fecha.
> **Relación con el prerregistro:** es la extensión prevista en la sección 1 de [protocolo-evaluacion-cierre-2026.md](protocolo-evaluacion-cierre-2026.md). **No lo modifica**: no cambia ninguna de sus reglas, umbrales ni pronósticos.

---

## 0. Propósito

El prerregistro declara que "no tiene un brazo humano solo ni IA sola". Este experimento agrega un brazo **"Claude solo"** para comparar, en una misma sesión, lo que produce Claude sin el operador frente a lo que produce el protocolo completo (los hechos del operador más el diálogo).

**En lenguaje llano:** ¿el operador y el diálogo agregan algo que Claude no encontraría por su cuenta, sin agregar más errores?

## 1. Pregunta e hipótesis

> **¿El protocolo SEG completo (brazo B) encuentra más hechos relevantes y pronostica mejor que Claude solo (brazo A), con la misma fecha de corte, el mismo plan de fuentes y las mismas preguntas, sin cometer más errores?**

- **H-AB1 (cobertura):** B tiene más hechos relevantes verificados que A.
- **H-AB2 (errores):** la tasa de errores de B no es mayor que la de A.
- **H-AB3 (pronóstico):** el Brier de B es menor (mejor) que el de A sobre las mismas preguntas.
- **H-AB4 (conciliencia):** las predicciones de patrón nuevas de cada brazo le ganan a decir siempre 50%.

**Qué no separa este diseño:** el aporte de los **hechos** del operador frente al aporte del **diálogo**. B incluye las dos cosas.

## 2. Brazos

| | Brazo A — Claude solo | Brazo B — protocolo completo |
|---|---|---|
| Procedimiento | SEG v1.0 ([especificacion-protocolo.md](especificacion-protocolo.md)) **sin** E1 (no hay hechos del operador) y sin diálogo | SEG v1.0 completo: es la S16 normal |
| Quién interviene | Claude. El operador solo pega el mensaje fijo (anexo A), aprueba los permisos y, si la sesión se detiene, escribe únicamente "Continúa." | El operador y Claude |
| Plan de fuentes | Los bloques de la sección 4 del prerregistro | Los mismos bloques. Si el operador agrega o quita fuentes, se declara en la S16 |
| Insumos | CLAUDE.md, `simulaciones/2026-10-09-sesion-15-seguimiento-extraoficial.md`, el checklist del README y el anexo B de este documento | Los mismos, más la lista del operador |
| Modelo | El mismo modelo de Claude en ambos brazos, en Claude Code con búsqueda web; su identificador exacto se registra | Ídem |
| Salida | `investigacion/ab-s16/brazo-a.md` | `simulaciones/YYYY-MM-DD-sesion-16-seguimiento-extraoficial.md` |

Ambas salidas terminan con el **anexo estándar** del anexo B, con el mismo formato.

## 3. Fecha de corte y orden

- **Fecha de corte (C):** el día en que se corre el brazo A, entre el 5 y el 10 de noviembre de 2026. Se registra en el commit del brazo A.
- **Ninguno de los dos brazos usa noticias publicadas después de C.** En B, que dura varios días, la regla depende de la disciplina de los dos participantes; se declara como limitación.
- **Orden:**
  1. Congelar este documento.
  2. Correr el brazo A en una **sesión nueva** de Claude Code, el día C.
  3. Hacer commit del brazo A **antes** de que empiece B.
  4. Recién entonces el operador muestra su lista y empieza la S16 (brazo B).
- **Si el brazo A falla** (la sesión se corta y no se puede continuar), se corre una vez más con el mismo mensaje y se declara. Si vuelve a fallar, el experimento se declara nulo.

## 4. Aislamiento

- **El brazo A no ve la lista del operador.** La lista no se escribe en el repositorio, en la memoria de Claude ni en CLAUDE.md antes de que A tenga commit.
- **El brazo B no ve el brazo A.** El operador no lee `brazo-a.md` hasta que la S16 tenga commit, y Claude no lo abre durante la S16.
- **Filtración conocida:** la sección 5 de [linea-base-k26n-2026-10.md](linea-base-k26n-2026-10.md) ya contiene tres temas aportados por el operador (Lula, las protestas en Europa y Starlink en Ucrania). El mensaje del brazo A le prohíbe abrir ese archivo, pero no se puede garantizar. Se declara.
- **La memoria de Claude** (que se carga sola en cada sesión) contiene una descripción del operador y de este plan, pero ningún hecho de la S16. Se declara.

## 5. Preguntas que pronostican los dos brazos

Cada brazo da una probabilidad (y un rango, si quiere) para cada pregunta. Se puntúa **el número que el brazo marque como punto**; si solo da un rango, su punto medio (regla de la sección 6.1 del prerregistro).

| Id | Pregunta y regla de resolución | Fecha de resolución |
|---|---|---|
| Q1 | Ítem 3.2 del prerregistro (acuerdo nuclear con las tres condiciones de K20), con su misma regla | 31 dic 2026 |
| Q2 | Ítem 3.3 (arma nuclear operativa), misma regla | 31 dic 2026 |
| Q3 | Ítem 3.4 (Netanyahu es primer ministro, titular o interino), misma regla | 31 dic 2026 |
| Q4 | Ítem 3.5 (recesión en EEUU visible en los datos), misma regla | 31 dic 2026 |
| Q5 | Ítem 3.6 (colapso del Estado libanés o anexión), misma regla | 31 dic 2026 |
| Q6 | P-2 (apoyo aéreo directo de EEUU a la ofensiva saudí en Yemen), misma regla | 31 dic 2026 |
| Q7 | **Entre el día siguiente a C y el 31 dic 2026, ¿EEUU o Israel atacan territorio iraní?** Con las reglas de T1 de la sección 4 del prerregistro (≥2 fuentes de bloques distintos; no cuentan buques, fuerzas por delegación ni ciberataques) | 31 dic 2026 |
| Q8 | **Entre el día siguiente a C y el 2 ene 2027, ¿EEUU ataca territorio iraní o Trump da un ultimátum público con plazo concreto?** Con las definiciones de K26-T (sección 5 del prerregistro) | 2 ene 2027 |

El ítem 3.1 no entra: ya estará resuelto en C. Los rangos de escenarios A–F no se puntúan; se reporta su entropía.

## 6. Qué se mide

| Métrica | Cómo se mide |
|---|---|
| **M-AB1. Cobertura** | Número de hechos de la tabla 2 del anexo estándar que el evaluador considera **relevantes y verificados**. Se cuentan los hechos **exclusivos** de cada brazo (los que el otro no tiene). El evaluador decide qué hechos son equivalentes entre brazos |
| **M-AB2. Errores** | Hechos marcados ✅ cuya fuente no los sostiene o cuya fecha está equivocada. **Tasa** = errores / hechos ✅ del brazo |
| **M-AB3. Pronóstico** | Brier de cada brazo sobre Q1–Q8, (p − resultado)², y la diferencia Brier(A) − Brier(B), con un intervalo de 95% por *bootstrap* pareado (10 000 remuestreos de las preguntas) |
| **M-AB4. Conciliencia** | Brier de las **3 predicciones de patrón nuevas** de cada brazo (tabla 3 del anexo estándar), frente a 0,25 (decir siempre 50%) |
| **M-AB5. Entropía** | Entropía de Shannon de los escenarios A–F de cada brazo (puntos medios normalizados). Solo se reporta |

**Relevante** significa que el hecho trata de un actor o un evento de alguna pregunta Q1–Q8 o de la definición de algún escenario A–F. **Una pregunta indeterminada** (sin dos fuentes de bloques distintos) se excluye del Brier en **ambos** brazos.

## 7. Tabla de decisión

Se aplica tal cual en enero de 2027. Los umbrales son una **recomendación de Claude**, con su razón al lado; el operador declaró que no tiene la formación para fijarlos (prerregistro, sección 10).

| # | Si… | Conclusión que se publica | Razón del umbral |
|---|---|---|---|
| R-1 | El intervalo de Brier(A) − Brier(B) **excluye 0 y es positivo** | Señal de que el protocolo completo pronostica mejor | Usar el intervalo evita fijar un número arbitrario |
| R-2 | El intervalo **excluye 0 y es negativo** | Señal de que Claude solo pronostica mejor | Ídem |
| R-3 | El intervalo **incluye 0** | Sin diferencia distinguible en pronóstico. **Es el resultado esperado** con 8 preguntas | Ídem |
| R-4 | B tiene **≥3** hechos relevantes verificados exclusivos **y** más exclusivos que A | El operador y el diálogo **amplían** la cobertura | Con menos de 3, la diferencia puede deberse al azar de las búsquedas |
| R-5 | La tasa de errores de B es **mayor** que la de A | La ampliación **trae más errores** | Cualquier aumento cuenta, porque la pregunta de investigación pide "sin aumentar" |
| R-6 | El Brier de las predicciones de patrón de un brazo es **> 0,25** | Las conexiones nuevas de ese brazo fueron mayormente falsa conciliencia | El mismo criterio que H-4 del prerregistro |

**Lectura combinada:** R-4 sin R-5 → "amplía sin degradar". R-4 con R-5 → "amplía con un costo en errores". Sin R-4 → "no se observa ampliación". Si se cumplen filas contradictorias, se reportan todas.

## 8. Calificación

- **Los dos evaluadores del prerregistro**, por separado: el operador y Gemini, en una Gem nueva, distinta de la del prerregistro, con este documento congelado como archivo de conocimiento.
- **Ciego parcial:** Gemini recibe solo los anexos estándar de los dos brazos, con las etiquetas "X" e "Y" asignadas al azar por el operador (que guarda la clave), más las fuentes de resolución. El operador **no puede ser ciego**, porque participó en B; se declara.
- **Los desacuerdos se reportan, y el titular usa la lectura menos favorable al brazo B**, como en el prerregistro.
- **El Brier y el bootstrap se calculan con código** (el pipeline de Python pendiente). Claude puede programarlo, pero **no califica** cobertura ni errores.

## 9. Limitaciones y conflictos declarados

- **n = 1:** una sesión por brazo, un operador, un modelo. El resultado es una **señal, no una prueba**.
- **Las preguntas están correlacionadas** (Q7 y Q8 dependen casi del mismo evento), así que el intervalo del bootstrap es optimista.
- **Claude produce los dos brazos, sabe cuál es cuál y redactó este diseño.** Podría, sin intención, esforzarse menos en A. La salvaguarda es el mensaje fijo del anexo A, los mismos criterios de parada de SEG y la revisión externa.
- **El brazo A sigue reglas escritas por el operador y Claude** (SEG, el plan de fuentes, CLAUDE.md). No mide "Claude sin ninguna influencia humana", sino Claude sin los hechos y sin el diálogo **de esta sesión**.
- **La fecha de corte en B depende de la disciplina** de los participantes (sección 3), y la filtración de la sección 4 no se puede descartar.
- **Revisión por otra IA:** ChatGPT y Claude pueden compartir sesgos por su entrenamiento. Que ChatGPT esté de acuerdo no valida el diseño; su revisión sirve para encontrar fallas.

## 10. Revisión externa y trazabilidad

- **Revisor:** ChatGPT (OpenAI), en lugar de Gemini, para que Gemini siga siendo solo evaluador.
- **Material que recibe:** este borrador y el prerregistro congelado, como referencia que no se puede cambiar. **No recibe la lista de hechos del operador.**
- **Procedimiento:**
  1. ChatGPT revisa con el mensaje fijo de `prompts/2026-10-31/P1-revision-chatgpt-diseno-ab.md`.
  2. Claude responde a cada observación: acepta, acepta en parte o no está de acuerdo, siempre con una razón.
  3. Esa respuesta vuelve a ChatGPT, que contesta. Máximo dos rondas.
  4. El operador decide los desacuerdos que queden. Se registran aquí como "desacuerdo declarado".
- Las respuestas de ChatGPT se archivan **completas y sin editar**, con la versión del modelo y la fecha.

**Cambios por la revisión:** *(se completa después de la revisión)*

| Sección | Observación | Respuesta de Claude | Decisión | Origen |
|---|---|---|---|---|

---

## Anexo A. Mensaje fijo para el brazo A

Se pega tal cual en una **sesión nueva** de Claude Code, abierta en este repositorio, reemplazando solo `[C]` por la fecha de corte:

```text
Vas a producir el BRAZO A ("Claude solo") del experimento definido en
investigacion/diseno-experimento-ab.md, ya congelado. Léelo primero.

Fecha de corte: [C]. No uses noticias publicadas después de esa fecha.

Sigue el protocolo SEG v1.0 (investigacion/especificacion-protocolo.md), con
estas diferencias: no hay etapa E1 (no hay hechos del operador) ni diálogo. Tú
decides las búsquedas. Usa los bloques de fuentes de la sección 4 del prerregistro
y la regla de verificación de SEG (≥2 fuentes independientes de bloques distintos).

Insumos permitidos: CLAUDE.md, simulaciones/2026-10-09-sesion-15-seguimiento-
extraoficial.md, el checklist del README.md y el diseño del experimento. No abras
otros archivos de investigacion/ ni de prompts/.

No le hagas preguntas al operador. Si tienes una duda, decide y declara la decisión.
Trabaja hasta cumplir los criterios de parada de SEG (sección 6), con el mismo
cuidado que en un seguimiento normal.

Escribe un solo archivo, investigacion/ab-s16/brazo-a.md, con: estado al corte,
hechos verificados (✅/🟡/⚪), análisis por capas, escenarios A–F con rango y punto,
entropía, contraste externo (K17), autocrítica de la S15 y, al final, el anexo
estándar (anexo B del diseño). No edites ningún otro archivo y no hagas commit.
```

## Anexo B. Anexo estándar (igual en los dos brazos)

Va al final de cada salida. **No menciona quién aportó cada hecho.**

**Tabla 1. Pronósticos**

| Id | p (punto) | Rango | Razón en una línea |
|---|---|---|---|
| Q1 … Q8 | | | |

**Tabla 2. Hechos relevantes verificados** (con fecha entre el 9 de octubre de 2026 y C)

| # | Hecho, en una frase | Fecha del hecho | Pregunta o escenario que toca | Estado (✅/🟡/⚪) | Fuente 1 (bloque, enlace) | Fuente 2 (bloque, enlace) |
|---|---|---|---|---|---|---|

**Tabla 3. Predicciones de patrón nuevas** (exactamente 3, con fecha límite no posterior al 31 dic 2026)

| Id | Hipótesis de patrón | Pregunta y regla de resolución | p | Fecha límite |
|---|---|---|---|---|

**Tabla 4. Escenarios al 31 dic 2026**

| Escenario | Rango | Punto |
|---|---|---|
| A … F | | |
