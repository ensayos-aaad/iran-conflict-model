# Línea de investigación post-cierre — evaluación del método ICM

**Iniciada:** 9–10 de octubre de 2026, durante y después del seguimiento extraoficial S15.
**Estado:** en construcción. El prerregistro (`protocolo-evaluacion-cierre-2026.md`) se **congeló el 25 de octubre de 2026** ([OSF](https://osf.io/xtrc8), etiqueta `prerregistro-2026-10-25`).

## Qué es esto

El modelo ICM está cerrado (v0.2.0, S13, 7 de junio de 2026), y nada de esta carpeta reabre ni corrige ese registro. Esta carpeta abre otra cosa: **una línea de investigación sobre el método**, no sobre el conflicto. La pregunta ya no es qué pasará con Irán, sino:

> **¿La dialéctica humano-IA estructurada produce conciliencia genuina (hipótesis que aciertan en hechos nuevos de otros dominios) o falsa conciliencia (coherencia narrativa que no se sostiene)?**

El objetivo declarado del operador es poder sacar conclusiones con respaldo al cierre de 2026, **incluida la conclusión de que el trabajo fue "humo"**, y hacerlo con estrictez ética en el uso de la IA.

## Casos de estudio

| Caso | Dominio | Duración | Estado | Repositorio |
|---|---|---|---|---|
| ICM — Iran Conflict Model | Geopolítica (guerra EEUU-Israel-Irán) | 98 días + seguimientos S14, S15… | Abierto: se evalúa al 31 dic 2026 | este repositorio |
| CEM — Colombia Electoral Model ("ICM Lite") | Elecciones (segunda vuelta Colombia 2026) | 21 días | **Resuelto: el modelo se equivocó** | [ensayos-aaad/modelo-electoral-colombia](https://github.com/ensayos-aaad/modelo-electoral-colombia) |

## Documentos

| Archivo | Contenido | Estado |
|---|---|---|
| [estado-del-arte.md](estado-del-arte.md) | Literatura relacionada, en ocho líneas | Borrador: las referencias con † deben verificarse |
| [marco-conceptual.md](marco-conceptual.md) | Conciliencia, el ciclo de Peirce, sesgo de automatización, detección de señales, lazo cerrado y disciplinas | Borrador |
| [patrones-candidatos.md](patrones-candidatos.md) | 12 patrones de diseño latentes del protocolo, con su evidencia | Borrador |
| [linea-de-procesos.md](linea-de-procesos.md) | El ICM, el CEM y los seguimientos como una línea de procesos, con su modelo de características y sus restricciones | Borrador |
| [caso-cem.md](caso-cem.md) | El CEM como segundo caso: resultado, puntaje y lecciones | Borrador |
| [protocolo-evaluacion-cierre-2026.md](protocolo-evaluacion-cierre-2026.md) | **Prerregistro** | **Congelado el 25 oct 2026**: etiqueta `prerregistro-2026-10-25`, [registro en OSF](https://osf.io/xtrc8) y [sello de OpenTimestamps](sello-prerregistro-2026-10-25/LEEME.md). No se edita más |
| [linea-base-k26n-2026-10.md](linea-base-k26n-2026-10.md) | Inventario de la conducta de Netanyahu del 6 al 25 oct, línea base de K26-N, más el contexto de EEUU antes de las midterms | 25 oct; se congela con el prerregistro |
| [precios-mercado-2026-10-25.md](precios-mercado-2026-10-25.md) | Precios de mercado de referencia (sección 6.5 del prerregistro) | 25 oct; se congela con el prerregistro |
| [registro-errores.csv](registro-errores.csv) | Quién detectó y quién corrigió cada error | 36 filas (24 oct); se agregan filas en cada seguimiento |
| [especificacion-protocolo.md](especificacion-protocolo.md) | El protocolo de seguimiento especificado como artefacto | SEG v1.0 (10 oct) |
| `diseno-experimento-ab.md` | La S16 en dos brazos: Claude solo frente al protocolo completo. Gemini no puede ser un brazo, porque es el segundo evaluador | Pendiente: documento aparte, congelado antes de empezar la S16; el análisis puede esperar a 2027 |

## Reglas de esta carpeta

1. **No se toca el registro cerrado** (README v0.2.0, S01–S13, CHANGELOG). Esta carpeta lo cita; no lo corrige.
2. **Toda afirmación apunta a evidencia**: un archivo, un commit o una fuente externa.
3. **Las referencias citadas de memoria llevan †** hasta verificarse. No se usan en un texto académico sin verificar.
4. **El prerregistro no se edita después de congelado.** Las correcciones van en un documento nuevo, con fecha, que explica qué cambió y por qué.
5. **Lo producido por la IA es material de estudio, no texto de tesis.** Una tesis basada en esta carpeta la escribe el operador, declarando el uso de IA según la política de su institución.

## Calendario

| Fecha | Hito |
|---|---|
| 24 oct 2026 | Revisión externa del borrador por Gemini y revisión del operador |
| 25 oct 2026 | Línea base de K26-N, precios de mercado y congelamiento del prerregistro (commit con etiqueta, push, OSF y OpenTimestamps) |
| 27 oct 2026 | Elección en Israel. Empieza la ventana de K26-N (28 oct – 17 nov) |
| 28 oct 2026 | Reunión de la Fed (contexto para la S16) |
| 29–30 oct 2026 | Cumbre Canadá–UE (contexto para la S16) |
| 3 nov 2026 | Midterms en EEUU: se resuelve 3.1; cierran las ventanas de P-1 (que ya parece Sí) y P-3 |
| 4 nov 2026 | Fin de la pausa declarada por Trump. Abren las ventanas de T1 (hasta el 31 dic) y K26-T (hasta el 2 ene 2027) |
| 17 nov 2026 | Fin de la ventana de K26-N: ya se puede comparar con la línea base |
| 18–19 nov 2026 | APEC de Shenzhen, con una posible cumbre Trump-Putin-Xi (contexto para el ítem 3.8) |
| 29 nov 2026 | Elecciones anticipadas en España (contexto para la S16) |
| 3 dic 2026 | Fusilamiento transmitido en vivo por el Pentágono (caso de prueba de las "cortinas de humo") |
| 31 dic 2026 | Corte del Grupo 3: se resuelven 3.2–3.6, P-2 y T1 |
| 2 ene 2027 | Fin de la ventana de K26-T |
| enero 2027 | Veredicto, con calificación independiente |
| feb–mar 2027 | Archivo en Zenodo, artículo y kit de réplica |

## Pendientes

Se marcan aquí a medida que se cumplen, con su fecha.

**Después del congelamiento**
- [ ] Actualizar el sello de OpenTimestamps (`ots upgrade`) cuando se ancle en Bitcoin, y hacer commit de la prueba actualizada. Instrucciones en el [LEEME del sello](sello-prerregistro-2026-10-25/LEEME.md)
- [ ] Comprobar que el registro de OSF (https://osf.io/xtrc8) quedó público; aprobarlo si OSF lo pide

**Seguimientos**
- [ ] Decidir si se hace el experimento A/B. Si se hace, `diseno-experimento-ab.md` debe congelarse **antes** de empezar la S16
- [ ] S16, sugerida entre el 5 y el 10 de noviembre, después de las midterms. El operador junta su lista de prensa desde el 27 de octubre. Ya hay temas anotados para la S16 en la sección 5 de la línea base: Lula, las protestas en Europa y Starlink en Ucrania
- [ ] S17, sugerida después del 17 de noviembre, para cerrar K26-N
- [ ] Agregar filas a `registro-errores.csv` en cada seguimiento

**Evaluación (enero de 2027)**
- [ ] Claude prepara el archivo de fuentes de resolución: solo enlaces y citas, sin conclusiones ni calificaciones. El operador revisa que no las tenga
- [ ] El operador crea una Gem nueva, "Evaluador ICM 2027", siguiendo el anexo A del prerregistro, y archiva su respuesta en `prompts/2027-01-.../`
- [ ] El operador califica por separado, sin ver la calificación de Gemini
- [ ] Construir el pipeline en Python: Brier por ítem con intervalos por *bootstrap*, entropía y métricas del registro de errores. Claude puede programarlo, pero no califica
- [ ] Aplicar la tabla de la sección 7 del prerregistro tal cual y publicar el veredicto, sea "humo" o "valor"

**Sin fecha**
- [ ] Verificar las referencias marcadas con † en `estado-del-arte.md` antes de usarlas en un texto académico
