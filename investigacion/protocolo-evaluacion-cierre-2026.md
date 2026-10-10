# Protocolo de evaluación prerregistrado — cierre 2026

> **ESTADO: BORRADOR, NO CONGELADO.** Redactado el 10 de octubre de 2026. Pendiente de la revisión del operador (secciones 1 y 7 en especial).
> **Congelamiento:** un commit con la etiqueta `prerregistro-2026-10-26`, más su push y su registro en OSF, **antes del 27 de octubre de 2026**, la primera fecha de resolución.
> **Después de congelado, este archivo no se edita.** Cualquier corrección va en un documento nuevo, con fecha, que explica qué cambió y por qué.

---

## 0. Propósito

Fijar **antes de conocer los resultados** qué se va a medir, cómo se va a calificar y **qué resultado significaría que el método fue "humo"**, de modo que el veredicto de enero de 2027 no se pueda acomodar. El objetivo del operador es poder sacar conclusiones con respaldo **aunque sean negativas**.

Contexto en [README.md](README.md), [marco-conceptual.md](marco-conceptual.md) y [caso-cem.md](caso-cem.md).

## 1. Pregunta de investigación

> **¿La dialéctica humano-IA estructurada amplía la detección de patrones en información abierta (conciliencia genuina) sin aumentar en la misma medida los patrones falsos (falsa conciliencia)?**

Se evalúa en tres niveles, de más sólido a más frágil:

| Nivel | Qué mide | Sección |
|---|---|---|
| A. Proceso | Si el diálogo detecta errores que cada parte sola no detectaría | 3 |
| B. Tesis estructurales | Si las hipótesis del método, fijadas antes, se sostienen frente a la realidad | 4 y 5 |
| C. Pronóstico numérico | Si las probabilidades del método le ganan a referencias simples y a los mercados | 6 |

## 2. Material que se evalúa

| Caso | Qué entra | Estado |
|---|---|---|
| ICM, seguimientos S14 (18 sept) y S15 (9 oct) | Pronósticos del Grupo 3, tesis con criterio y patrones | Abierto: se resuelve entre el 27 oct y el 31 dic de 2026 |
| CEM | Pronóstico de la segunda vuelta, autocalificación y patrones | **Ya resuelto** (21 jun 2026). Entra como caso de comparación; su resultado se conocía al redactar este documento |
| ICM S01–S13 | Solo como antecedente | No se puntúa: no hubo prerregistro |

**Advertencia:** todo lo anterior a este documento (S14, S15 y el CEM) se evaluó o se formuló sin prerregistro formal. Solo los pronósticos y criterios **nuevos de este documento** (secciones 5 y 6.3) y la **calificación** de lo ya publicado quedan protegidos por el prerregistro.

## 3. Nivel A — Proceso: registro de errores

**Instrumento:** `registro-errores.csv` (pendiente de crear), con una fila por error detectado:

`fecha, caso, sesion, descripcion, tipo_error, quien_lo_cometio, quien_lo_detecto, corregido, evidencia, retrospectivo`

- `tipo_error`: hecho falso, fecha o sujeto equivocado, omisión, inferencia no sostenida, sesgo, o error de modelado.
- `quien_lo_cometio` y `quien_lo_detecto`: operador, IA, fuente externa o realidad.
- `retrospectivo`: **TRUE** si se reconstruye de material anterior al 10 de octubre de 2026.

**Métricas:**
- **M-A1.** Proporción de errores detectados por cada parte (operador, IA, externa, realidad).
- **M-A2.** Proporción de errores *cruzados*: detectados por una parte distinta de la que los cometió.
- **M-A3.** Proporción de errores corregidos antes de su fecha de resolución.

Los registros retrospectivos y los prospectivos (desde el 10 de octubre) se reportan **por separado**.

## 4. Nivel B — Tesis estructurales (criterios fijados)

### T1 — "F era la sala de espera de C"

Formulada en S13. El criterio fechado se fijó en la S15 §5 y aquí se precisa.

| Resultado al 31 dic 2026 | Condición | Veredicto |
|---|---|---|
| **Confirmada** | Entre el 4 nov y el 31 dic de 2026, **EEUU o Israel** realizan ataques aéreos o con misiles sobre **territorio iraní**, reportados por ≥2 fuentes independientes de bloques distintos | T1 se sostiene |
| **Debilitada** | No hay ataques así **y** existe un texto escrito de acuerdo o de alto el fuego entre EEUU e Irán, publicado o confirmado por ambas partes | T1 se debilita seriamente |
| **Indeterminada** | No hay ataques **ni** texto (limbo tipo B) | No se puede juzgar; se reporta como tal |

**Caso especial:** si hay ataques de EEUU sobre territorio iraní **antes** del 3 de noviembre (la pausa se rompe), T1 queda confirmada y la predicción **K26-T** (sección 5) queda **refutada**.

**Exclusión:** no cuentan los ataques a buques, a fuerzas por delegación (hutíes, milicias) ni los ciberataques. Solo cuentan los ataques sobre territorio iraní.

## 5. Nivel B — Predicciones de K26

K26 refinado (S15 §7): *la cercanía a un evento de rendición de cuentas predice que la conducta cambia; el sentido del cambio depende de qué castiga el electorado de cada actor.*

**Nota honesta:** la S15 formuló estas predicciones de forma vaga. Lo que sigue es su **operacionalización**, hecha antes de su resolución.

### K26-T (Trump)

**Predicción:** la contención frente a Irán fue electoral, así que termina después del 3 de noviembre.
- **Se cumple** si entre el 4 nov y el 2 ene de 2027 (60 días) ocurre **al menos una** de estas dos cosas: (a) ataques de EEUU sobre territorio iraní; (b) un ultimátum público de Trump con fecha o plazo concreto para atacar.
- **No se cumple** si en esos 60 días no ocurre ninguna de las dos.
- **Refutada de entrada** si EEUU ataca territorio iraní antes del 3 de noviembre.

### K26-N (Netanyahu)

**Predicción:** con la elección del 27 de octubre ya pasada, y sin otro evento de rendición de cuentas inminente, la intensidad de su conducta extrema **no aumenta** respecto de las tres semanas previas.
- **Comparación:** del 6 al 26 de octubre frente al 28 de octubre – 17 de noviembre.
- **Rúbrica** (cada ítem: mayor, igual o menor en la ventana posterior):
  (a) nuevos ataques ordenados sobre Irán, Líbano o Gaza;
  (b) confrontaciones públicas con instituciones internacionales (ONU, CPI);
  (c) medidas legales o coercitivas contra críticos internos (NAZA, investigaciones sobre el 7 de octubre).
- **Se cumple** si al menos 2 de 3 ítems salen "igual" o "menor". **No se cumple** si al menos 2 de 3 salen "mayor".
- **No evaluable** si Netanyahu deja de ser primer ministro (titular o interino) antes del 17 de noviembre, o si aparece otro evento de rendición de cuentas inminente: nueva elección convocada, decisión judicial en su juicio o inicio formal de una comisión estatal sobre el 7 de octubre.
- **Advertencia:** es evidencia **cualitativa y débil**. La califican evaluadores independientes (sección 8).

## 6. Nivel C — Pronósticos numéricos

### 6.1 Regla de conversión

Las probabilidades publicadas en la S14 y la S15 son rangos. **Regla fijada:** se puntúa el **punto medio** del rango; si se publicó un solo valor, ese valor. No se elige otro punto después de conocer el resultado.

### 6.2 Preguntas del Grupo 3 que se pueden puntuar

| Ítem | Pregunta y regla de resolución (al 31 dic 2026, salvo que se indique otra cosa) | S14 | S15 |
|---|---|---|---|
| 3.1 | **¿Los demócratas obtienen mayoría en la Cámara (≥218 escaños) en la elección del 3 nov 2026?** Según las proyecciones de AP o los resultados certificados disponibles al 31 dic | 0,675 | 0,685 |
| 3.2 | **¿Hay un acuerdo nuclear EEUU-Irán con las tres condiciones de K20?** Texto público, verificación de la OIEA incluida y algún alivio de sanciones. Tienen que cumplirse las tres | 0,15 | 0,165 |
| 3.3 | **¿Irán posee un arma nuclear operativa?** Según una prueba nuclear detectada, un anuncio oficial iraní o una evaluación pública del Director de Inteligencia Nacional de EEUU o de la OIEA | 0,10 | 0,10 |
| 3.4 | **¿Netanyahu ocupa el cargo de primer ministro el 31 dic 2026**, como titular o interino? | 0,40 | 0,525 |
| 3.5 | **¿EEUU está en recesión, con los datos publicados al 31 dic?** Sí si la BEA reporta dos trimestres consecutivos de PIB real negativo dentro de 2026, o si el NBER declara una recesión que comience en 2026 | 0,175 | 0,205 |
| 3.6 | **¿Colapso del Estado libanés o anexión?** Sí si Israel declara la anexión o la soberanía permanente sobre territorio libanés, o si el gobierno central del Líbano deja de funcionar (sin gabinete, ni siquiera interino, o sin control de Beirut) | 0,20 | 0,20 |
| 3.7 | **¿Colombia cambia su política exterior?** **Ya resuelto: Sí** (relaciones con Israel restablecidas el 11 ago 2026, antes de la S14) | 0,30 | — (la S15 no pronosticó: lo dio por cumplido) |

**Puntaje:** Brier por ítem, (p − resultado)², y el promedio por seguimiento. Con el número de ítems disponible (6 o 7), **el margen de error es amplio** (del orden de ±0,15): el resultado se reporta como **señal, no como veredicto**. Se acompaña de un intervalo por *bootstrap*.

**Advertencia sobre 3.7:** la S14 puntuará con 0,49 en ese ítem, un error sobre un hecho que ya había ocurrido. Se reporta tal cual.

### 6.3 Ítems que no se pueden puntuar numéricamente

Se califican **cualitativamente** con una rúbrica, por evaluadores independientes, y **no entran al Brier**:
- **3.3 "cerca" del arma** (~25% en la S14 y la S15): no tiene criterio observable.
- **3.8 eje China-Rusia-Irán** (S14: 0,725; S15: 0,60): "se consolida" no es binario.
- **3.9 nueva arquitectura de seguridad regional** (S14: 0,20; S15: 0,275): ídem.

### 6.4 Pronósticos nuevos (hechos hoy, 10 oct 2026)

Ponen a prueba hipótesis de patrón de la S15, es decir, posibles casos de conciliencia:

| Id | Hipótesis de origen (S15) | Pregunta y regla de resolución | p |
|---|---|---|---|
| P-1 | "La pausa es solo de bombardeos" (§10) | **Entre el 10 oct y el 3 nov, ¿ocurre al menos uno de estos?** (a) nuevas designaciones de sanciones de EEUU contra Irán (OFAC); (b) un ciberataque, sabotaje o complot fuera de Irán **atribuido** a Irán o a sus aliados por un gobierno; (c) un ataque de los hutíes o de milicias aliadas de Irán contra fuerzas o infraestructura de EEUU o de Arabia Saudita | 0,85 |
| P-2 | ¿EEUU se repliega del Golfo o solo externaliza? (capa 2) | **¿EEUU anuncia o confirma apoyo aéreo directo (ataques) a la ofensiva saudí en Yemen antes del 31 dic?** Sí = externalización temporal; No = respalda el repliegue | 0,30 |
| P-3 | Escalada iraní cronometrada a los midterms (Parsi, K17 de la S15) | **Entre el 20 oct y el 3 nov, ¿Irán o sus aliados atacan fuerzas o instalaciones de EEUU con muertos o heridos estadounidenses confirmados?** | 0,20 |

### 6.5 Referencias de comparación

| Referencia | Cómo se obtiene |
|---|---|
| **Siempre 50%** | Brier de 0,25 por ítem |
| **Mercado de predicción** | Precio en Polymarket o Kalshi **capturado el día del congelamiento** (fecha, hora, URL y precio), para cada pregunta con un contrato equivalente. Si no hay contrato, se registra "sin referencia de mercado" |
| **Frecuencia histórica** | Solo donde hay una clase de referencia razonable. Ver la tabla siguiente |

**Frecuencias históricas fijadas (10 oct 2026):**

| Ítem | Clase de referencia | Valor | Fuente | Advertencia |
|---|---|---|---|---|
| 3.1 | Midterms desde 1946 en que el partido del presidente **pierde escaños** en la Cámara: 18 de 20 | **0,90** | [Wikipedia, "United States midterm election"](https://en.wikipedia.org/wiki/United_States_midterm_election); [FiveThirtyEight](https://fivethirtyeight.com/features/why-the-presidents-party-almost-always-has-a-bad-midterm) | Perder escaños no es lo mismo que perder la mayoría. Solo se acercan cuando la mayoría es estrecha. Es una cota aproximada, no la misma pregunta |
| 3.5 | NBER: 13 recesiones desde la Segunda Guerra Mundial, más o menos una cada seis años | **≈ 0,15** por año | [Fed de San Francisco, "Dr. Econ"](https://www.frbsf.org/research-and-insights/publications/doctor-econ/recession-history/) | La pregunta exige que la recesión sea visible en los datos publicados al 31 dic, lo que tiende a reducir la probabilidad |
| 3.2, 3.3, 3.4, 3.6, P-1, P-2, P-3 | Sin una clase de referencia razonable | — | — | **Se omite** la frecuencia histórica |

### 6.6 Métrica de salud: entropía

En cada corte se calcula la **entropía de Shannon** de la distribución de escenarios A–F al 31 dic (puntos medios normalizados) y se reporta **junto a** la convergencia narrada. Valores registrados: S13 = 1,976 bits; S14 = 2,033; S15 = 2,143 (máximo 2,585). Si la narración y la entropía discrepan en dirección, se reporta como discrepancia. No se ajusta ninguna de las dos.

## 7. Qué contaría como "humo" (tabla de decisión)

Se aplica **tal cual** en enero de 2027.

| # | Si al cierre… | Conclusión que se publica |
|---|---|---|
| H-1 | En el registro de errores prospectivo, **≥80%** de los errores cruzados los detecta **una sola** de las dos partes | **El diálogo no aporta como tal: una de las partes sobra** |
| H-2 | **T1** queda debilitada **y** K26-T y K26-N no se cumplen | **El método no capturó la estructura del conflicto** |
| H-3 | El Brier del ICM (S15) es **> 0,25** **y** peor que el mercado en las preguntas comparables | **Sin valor como pronóstico** (como ya mostró el CEM) |
| H-4 | **Menos de la mitad** de P-1, P-2 y P-3, y de T1, se resuelven en la dirección que el método consideró más probable | **Las conexiones no evidentes fueron mayormente falsa conciliencia** |
| V-1 | Hay errores cruzados en **ambas** direcciones (cada parte detecta ≥20%), **T1** no queda debilitada y **no se cumple H-3** | **Valor como herramienta de análisis y de pronóstico** |
| V-2 | Igual que V-1, pero **se cumple H-3** | **Valor como herramienta de análisis, no de pronóstico** (la hipótesis más probable según la literatura) |

Si se cumplen a la vez filas de "humo" y de valor, **se reportan todas**, sin escoger. Si T1 queda "indeterminada", se reporta y las filas que dependen de ella se marcan "no evaluables".

## 8. Calificación

- **Dos evaluadores, por separado:** (1) el operador; (2) un segundo evaluador que **no sea Claude**: otra persona o un modelo de otro proveedor. Ninguno ve la calificación del otro ni una lectura previa de Claude.
- **Material para calificar:** las reglas de este documento y las fuentes de resolución, no los resúmenes del modelo.
- **Los desacuerdos se reportan**, no se resuelven por promedio. Si el desacuerdo cambia una fila de la sección 7, se publican las dos lecturas.
- Claude puede preparar la recopilación de fuentes, pero **no califica**.

## 9. Lo que este estudio no puede concluir

- Que el método "predice" la geopolítica.
- Nada estadísticamente significativo: hay 2 casos y unas 10 preguntas.
- Nada sobre otros operadores: hay un solo operador.
- Nada sobre otros modelos: los dos casos usaron Claude.

## 10. Conflictos de interés y sesgos declarados

- El análisis lo produce **Claude (Anthropic)**. Anthropic firmó el acuerdo voluntario de IA del 29 de septiembre de 2026, evaluado en la S15. Por eso Claude **no califica** (sección 8).
- El operador es a la vez autor, sujeto y evaluador. Por eso hay un segundo evaluador.
- El operador declaró preferencias en ambos casos: que el conflicto se resolviera (ICM) y que ganara Cepeda (CEM).
- Este documento lo redactó Claude. Su redacción puede estar sesgada hacia criterios que el modelo cree que se cumplirán. **La revisión del operador, antes del congelamiento, es la salvaguarda.**

## 11. Pendientes antes del congelamiento

- [ ] Revisión del operador, en especial las secciones 1, 5 y 7
- [x] Crear `registro-errores.csv` con los registros retrospectivos (10 oct: 24 filas)
- [ ] Capturar los precios de mercado (sección 6.5), el día del congelamiento
- [x] Documentar las frecuencias históricas, o retirarlas (10 oct: 3.1 y 3.5 fijadas; las demás, omitidas)
- [x] Agregar las filas a `datos/validacion/registro-validacion.csv` (10 oct: 16 filas)
- [x] Escribir `especificacion-protocolo.md` (10 oct)
- [ ] Definir quién será el segundo evaluador
- [ ] Commit con la etiqueta `prerregistro-2026-10-26`, push y OSF
