# Preguntas y formato de salida — seguimiento S16

> Se congela junto con el diseño del 1–4 nov 2026. No se edita después.

## 1. Fecha de corte y ventana de hechos

- **Fecha de corte (C):** la que indique el mensaje de inicio. No se usan noticias publicadas después de C.
- **Ventana de hechos:** se registran hechos con fecha entre el 9 de octubre de 2026 (corte de la S15) y C.

## 2. Bloques de fuentes y verificación

Los bloques son los de la sección 4 del prerregistro: (1) agencias internacionales (Reuters, AP, AFP); (2) prensa de EEUU; (3) prensa europea; (4) prensa del Golfo y árabe; (5) Irán, estatal u opositora; (6) Israel; (7) China; (8) América Latina en español.

- **Los 8 bloques son obligatorios.** "Cubierto" significa que se hizo al menos una búsqueda dirigida a ese bloque, aunque no haya devuelto nada útil. Se pueden agregar fuentes fuera de los bloques; se declaran.
- **Verificado (✅):** ≥2 fuentes independientes de **bloques distintos** que sostienen el hecho. Dos medios del mismo bloque no son independientes. Un comunicado oficial cuenta dentro del bloque de su país. Los medios estatales u opositores cuentan como posición, no como prueba.
- **Parcial o desactualizado (🟡):** una sola fuente, o fuentes que sostienen solo una parte.
- **No verificado o descartado (⚪).** "No encontrado" no significa "no ocurrió".
- **Las fechas se verifican explícitamente.**
- **Criterio de parada de la búsqueda:** cuando las búsquedas ya no devuelven hechos nuevos relevantes para estas preguntas o para los escenarios A–F.

## 3. Preguntas que se pronostican

Para cada una se da una probabilidad (punto) y, si se quiere, un rango. Si solo se da un rango, se puntúa su punto medio.

| Id | Pregunta y regla de resolución | Fecha de resolución |
|---|---|---|
| Q1 | **¿Hay un acuerdo nuclear EEUU-Irán con las tres condiciones de K20?** Texto público, verificación de la OIEA incluida y algún alivio de sanciones anunciado oficialmente por EEUU (las licencias humanitarias generales o de rutina no cuentan). Tienen que cumplirse las tres | 31 dic 2026 |
| Q2 | **¿Irán posee un arma nuclear operativa?** Según una prueba nuclear detectada, un anuncio oficial iraní o una evaluación pública del Director de Inteligencia Nacional de EEUU o de la OIEA | 31 dic 2026 |
| Q3 | **¿Netanyahu ocupa el cargo de primer ministro el 31 dic 2026**, como titular o interino? | 31 dic 2026 |
| Q4 | **¿EEUU está en recesión, con los datos publicados al 31 dic?** Sí si la BEA reporta dos trimestres consecutivos de PIB real negativo dentro de 2026, o si el NBER declara una recesión que comience en 2026 | 31 dic 2026 |
| Q5 | **¿Colapso del Estado libanés o anexión?** Sí si Israel declara la anexión o la soberanía permanente sobre territorio libanés, o si el gobierno central del Líbano deja de funcionar (sin gabinete, ni siquiera interino, o sin control de Beirut) | 31 dic 2026 |
| Q6 | **¿EEUU anuncia o confirma apoyo aéreo directo (ataques) a la ofensiva saudí en Yemen antes del 31 dic?** | 31 dic 2026 |
| Q7 | **Entre el día siguiente a C y el 31 dic 2026, ¿EEUU o Israel realizan ataques aéreos o con misiles sobre territorio iraní**, reportados por ≥2 fuentes independientes de bloques distintos? No cuentan los ataques a buques, a fuerzas por delegación (hutíes, milicias) ni los ciberataques | 31 dic 2026 |
| Q8 | **Entre el día siguiente a C y el 2 ene 2027, ¿ocurre al menos una de estas dos cosas?** (a) ataques de EEUU sobre territorio iraní; (b) un ultimátum público de Trump con fecha o plazo concreto para atacar. **"Concreto"** significa una fecha de calendario o un número de horas o días; "pronto", "muy pronto" o "en los próximos días" no cuentan | 2 ene 2027 |

## 4. Anexo estándar

Va al final de la salida, con este formato exacto. **No menciona quién aportó cada hecho.**

**Tabla 1. Pronósticos**

| Id | p (punto) | Rango | Razón en una línea |
|---|---|---|---|
| Q1 … Q8 | | | |

**Tabla 2. Hechos relevantes** (con fecha entre el 9 oct 2026 y C; se incluyen también los 🟡 y ⚪)

| # | Hecho, en una frase | Fecha del hecho | Pregunta o escenario que toca | Relevancia: **D** (toca la regla de resolución de la pregunta o la definición del escenario) o **P** (predictiva), y la conexión en una frase | Estado (✅/🟡/⚪) | Fuente 1 (bloque, enlace) | Fuente 2 (bloque, enlace) |
|---|---|---|---|---|---|---|---|

**Tabla 3. Predicciones de patrón nuevas** (exactamente 3, con fecha límite no posterior al 31 dic 2026)

Una predicción de patrón sale de una conexión entre hechos que no es evidente, y tiene que predecir **hechos distintos de los que la originaron**, con una regla de resolución escrita ahora. "Nueva" significa que no está formulada en la S15 ni en los demás insumos permitidos.

| Id | Hipótesis de patrón | Hechos que la originaron (# de la tabla 2) | Pregunta y regla de resolución | p | Fecha límite | Comprobación de novedad, en una frase |
|---|---|---|---|---|---|---|

**Tabla 4. Escenarios al 31 dic 2026**

| Escenario | Rango | Punto |
|---|---|---|
| A … F | | |

## 5. Hoja de ejecución

Va después del anexo estándar, en una sección aparte.

| Campo | Valor |
|---|---|
| Inicio (fecha y hora, Colombia) | |
| Fin (fecha y hora, Colombia) | |
| Modelo (identificador exacto) | |
| Fecha de corte (C) | |
| Número de búsquedas web | |
| Número de fuentes examinadas | |
| Bloques cubiertos (1–8: sí/no) | |
| Fuentes fuera de los bloques | |
| Interrupciones (y cómo se continuó) | |
| Desviaciones de estas reglas | |
| Conocimiento posterior a C detectado durante la sesión | |
