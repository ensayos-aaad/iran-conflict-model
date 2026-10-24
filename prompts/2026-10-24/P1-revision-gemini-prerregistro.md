# P1 — Revisión externa del prerregistro por Gemini

**Fecha:** 2026-10-24
**Sesión:** línea de investigación (no es una sesión del ICM)
**Tipo:** Validación
**Peldaño Pearl:** N/A
**Impacto en modelo:** Alto (cambió las reglas del prerregistro antes de congelarlo)

**Herramienta:** Gem de Gemini "Revisor prerregistro ICM", modelo Gemini 3.1 Pro con nivel de razonamiento High, sin herramienta por defecto, con las citas de conocimiento activadas.
**Documento revisado:** `investigacion/protocolo-evaluacion-cierre-2026.md` en el commit `28e0a0d` (borrador del 10 oct), cargado como único archivo de conocimiento.
**Por qué:** el borrador lo redactó Claude, y el operador no tenía un revisor humano disponible. Gemini será además el segundo evaluador en enero de 2027 (sección 8 del prerregistro), con una Gem distinta.

## Prompt

Instrucciones de la Gem (redactadas por Claude, aprobadas por el operador):

```text
Eres un revisor metodológico independiente y escéptico. Vas a revisar el borrador
de un prerregistro que está en tus archivos de conocimiento, antes de que se congele.
Lo redactó otra IA (Claude, de Anthropic), y el riesgo principal es que haya fijado
criterios que favorezcan un resultado positivo para el método que se evalúa. Tu
trabajo es encontrar debilidades, no aprobar el documento.

Contexto: el documento evalúa un método de análisis humano-IA aplicado a un
conflicto geopolítico real. Los pronósticos se resuelven entre el 27 de octubre y
el 31 de diciembre de 2026. Después de congelado, el documento no se podrá editar.

Revisa y responde en español, con estas secciones:

1. REGLAS DE RESOLUCIÓN AMBIGUAS. Para cada pronóstico, tesis o criterio (T1, K26-T,
   K26-N, P-1, P-2, P-3, ítems del Grupo 3), di si dos personas razonables podrían
   resolverlo de forma distinta con las mismas noticias. Cita la frase ambigua y
   propón una redacción más precisa.

2. SESGO HACIA EL ÉXITO. Señala criterios o umbrales de la sección 7 (tabla de "humo")
   que hagan más fácil concluir "valor" que "humo". ¿Hay resultados plausibles que no
   caigan en ninguna fila?

3. RESOLUBILIDAD. ¿Hay preguntas que no se puedan resolver con fuentes públicas o
   que requieran un juicio político?

4. INCONSISTENCIAS internas (fechas, numeración, definiciones que cambian).

5. LO QUE FALTA para que un evaluador externo pueda calificar en enero de 2027
   sin consultar a los autores.

Formato: para cada sección, una tabla con las columnas
| Sección del documento | Problema | Gravedad (alta/media/baja) | Propuesta |
Al final, una lista de las 5 correcciones más importantes, en orden.

No reescribas el documento entero. No evalúes si el conflicto o el método son
interesantes; solo la calidad del prerregistro. Si algo está bien, no hace falta
comentarlo. Basa cada observación en el texto del documento y cita la sección.
```

Mensaje enviado: `Revisa el documento adjunto siguiendo tus instrucciones.`

## Respuesta del sistema

Respuesta completa de Gemini, tal como la copió el operador:

### 1. REGLAS DE RESOLUCIÓN AMBIGUAS

| Sección del documento | Problema | Gravedad (alta/media/baja) | Propuesta |
| --- | --- | --- | --- |
| 4 (T1) | "reportados por ≥2 fuentes independientes de bloques distintos". La noción de "bloques distintos" es geopolíticamente subjetiva. ¿Al Jazeera y Reuters son bloques distintos? ¿O se refiere a países alineados vs. no alineados? | Alta | Listar explícitamente las agencias o países que conforman cada "bloque" (ej. prensa occidental vs. prensa estatal de Medio Oriente). |
| 5 (K26-T) | "un ultimátum público de Trump con fecha o plazo concreto para atacar". La retórica política frecuentemente usa plazos difusos (ej. "en los próximos días", "muy pronto"). Esto deja a discreción del calificador qué califica como "concreto". | Alta | Reemplazar por "un ultimátum público que establezca un límite temporal exacto en horas, días específicos o una fecha calendario exacta". |
| 5 (K26-N) | "(a) nuevos ataques ordenados sobre Irán, Líbano o Gaza". En un escenario de conflicto activo, ocurren "nuevos ataques" a diario. Es imposible medir si la intensidad es "mayor, igual o menor" contando ataques rutinarios. | Alta | Definir "nuevos ataques" como "apertura de un nuevo frente terrestre" o "ataques a infraestructuras estatales o nucleares no atacadas previamente". |
| 6.2 (3.2) | "algún alivio de sanciones". Es un umbral extremadamente bajo y subjetivo. Una exención administrativa menor para fines humanitarios podría calificar como "algún alivio", distorsionando el espíritu del acuerdo nuclear. | Media | Especificar: "levantamiento formal de sanciones petroleras o descongelamiento de fondos soberanos por un monto superior a X billones". |
| 6.2 (3.6) | "gobierno central del Líbano deja de funcionar (... o sin control de Beirut)". El "control" es un espectro. ¿Se refiere a control militar, provisión de servicios o presencia policial? | Media | Cambiar a: "las fuerzas armadas o la policía libanesa se retiran oficialmente de al menos el 50% de los distritos administrativos de Beirut". |

### 2. SESGO HACIA EL ÉXITO

| Sección del documento | Problema | Gravedad (alta/media/baja) | Propuesta |
| --- | --- | --- | --- |
| 7 (H-1) | "≥80% de los errores cruzados los detecta una sola de las dos partes". Este umbral es excesivamente indulgente. Si la IA detecta el 79% y el humano el 21%, el método evade la categoría de "humo", aunque el aporte humano sea marginal. | Alta | Bajar el umbral de monopolio de detección de errores al 65% o 70% para demostrar un verdadero equilibrio dialéctico. |
| 7 (H-4) | "Menos de la mitad de P-1, P-2 y P-3, y de T1, se resuelven en la dirección que el método consideró más probable". Para P-2 (p=0.30) y P-3 (p=0.20), la "dirección más probable" es que *no ocurran*. Predecir que no pasará un evento improbable es predecir el statu quo. Acertar el statu quo inflará artificialmente los aciertos y evitará caer en H-4. | Alta | H-4 debe evaluar el Brier Score de estas predicciones contra una referencia de 0.5 o evaluar solo si los eventos anómalos (probabilidad > 0.5) se cumplen. |
| 7 (Condiciones V-1 y V-2) | V-1 exige que "T1 no queda debilitada". Según la sección 4, T1 puede quedar "Indeterminada". Si T1 queda indeterminada, no cae en H-2 (que exige que T1 quede debilitada) ni en V-1/V-2 (porque dependen de T1 evaluable). Hay un vacío enorme donde resultados mixtos no penalizan ni validan el modelo. | Alta | Crear una regla explícita para la tabla de decisión si T1 resulta "Indeterminada", forzando el peso de la evaluación hacia las métricas C (Brier). |

### 3. RESOLUBILIDAD

| Sección del documento | Problema | Gravedad (alta/media/baja) | Propuesta |
| --- | --- | --- | --- |
| 4 (T1) | Exige la existencia de un "texto escrito de acuerdo o de alto el fuego entre EEUU e Irán, publicado o confirmado". Las negociaciones entre estos países a menudo operan mediante memorandos informales o acuerdos tácticos no escritos (ej. intermediación de Omán). Podría ocurrir un alto el fuego real sin texto publicado. | Alta | Añadir como alternativa de confirmación: "declaraciones oficiales de voceros de ambos gobiernos confirmando un entendimiento mutuo para el cese de hostilidades". |
| 6.2 (3.3) | "¿Irán posee un arma nuclear operativa?". La inteligencia estadounidense y la OIEA rara vez declaran categóricamente la posesión de un "arma operativa" hasta que hay una detonación confirmada. Sus informes suelen hablar de "material fisible suficiente" o "capacidades". | Media | Añadir: "o un informe de la OIEA que confirme el desvío de suficiente uranio enriquecido al 90% acoplado con evidencia de militarización". |

### 4. INCONSISTENCIAS INTERNAS

| Sección del documento | Problema | Gravedad (alta/media/baja) | Propuesta |
| --- | --- | --- | --- |
| 5 (K26-N) vs. Contexto | K26-N menciona "la elección del 27 de octubre ya pasada". No se especifica a qué elección israelí (u otra) se refiere. Si es un evento del conflicto, no está definido en los antecedentes y genera confusión con las elecciones estadounidenses del 3 de noviembre mencionadas en K26-T y 3.1. | Alta | Especificar a qué proceso electoral o votación parlamentaria exacta en Israel corresponde el 27 de octubre de 2026. |
| 6.3 vs 6.2 | La sección 6.3 lista los ítems "3.8 eje China-Rusia-Irán" y "3.9 nueva arquitectura de seguridad regional". Sin embargo, la tabla principal de la sección 6.2 salta del ítem 3.7 directamente al final, omitiendo la formulación original de 3.8 y 3.9. | Media | Integrar las preguntas 3.8 y 3.9 a la tabla de la sección 6.2 indicando en la columna de S14/S15 que son de evaluación puramente cualitativa. |
| 7 (H-4) vs 4 (T1) | H-4 asume que T1 tiene una "dirección que el método consideró más probable". Sin embargo, en la sección 4, T1 no tiene probabilidades asignadas; solo tiene criterios de "Confirmada", "Debilitada" o "Indeterminada". Es imposible calcular matemáticamente "la mitad" de este conjunto mixto. | Alta | Separar T1 de la métrica de P-1, P-2 y P-3 en la regla H-4, o asignarle retrospectivamente una probabilidad explícita en el texto. |

### 5. LO QUE FALTA

| Sección del documento | Problema | Gravedad (alta/media/baja) | Propuesta |
| --- | --- | --- | --- |
| 5 (K26-N) | No hay un registro base (baseline) congelado de la "conducta extrema" del 6 al 26 de octubre. Un evaluador externo en enero de 2027 tendrá que reconstruir retrospectivamente cómo era esa conducta, lo cual introduce sesgo de retrospectiva (hindsight bias). | Alta | Anexar o enlazar un documento con el inventario cerrado de las acciones de Netanyahu del 6 al 26 de octubre antes de congelar el protocolo. |
| 6.5 (Mercado de predicción) | Se indica usar el precio de Polymarket o Kalshi para "un contrato equivalente". Los contratos de mercados de predicción suelen tener letras chicas muy específicas que no coincidirán al 100% con los ítems de 6.2. | Media | Definir qué nivel de desvío en la redacción hace que un contrato deje de ser "equivalente" (ej. "el contrato no puede diferir en fechas límite por más de 7 días ni incluir condiciones adicionales no listadas en 6.2"). |
| 8 (Calificación) | El protocolo dice que "Los desacuerdos se reportan, no se resuelven por promedio", pero no especifica cómo se calcula el Brier Score final o las métricas de la tabla de Humo si los dos evaluadores tienen respuestas binarias contradictorias sobre la resolución de un evento. | Alta | Establecer un mecanismo de desempate (ej. un tercer evaluador ciego) o una regla que dicte que, ante empate irresoluble, el ítem se marca a favor de la hipótesis nula (humo). |

1. **Reestructurar la condición H-4 (Sesgo de statu quo):** Evaluar predicciones de baja probabilidad (P-2, P-3) basándose en si el modelo previó el "statu quo" infla artificialmente el éxito. H-4 debe recalibrarse para no regalar aciertos cuando simplemente "no pasa nada".
2. **Cerrar el vacío de la "Indeterminación" de T1:** Actualmente, si T1 queda en el limbo, el protocolo se queda sin instrucciones claras en la matriz de Humo vs Valor, impidiendo una conclusión definitiva.
3. **Fijar la línea base cualitativa de K26-N:** Es metodológicamente inválido pedirle a un evaluador externo en enero de 2027 que compare una intensidad sin haber dejado documentado, de manera congelada y cuantificable, qué pasó exactamente entre el 6 y el 26 de octubre.
4. **Clarificar la ambigüedad en "K26-N: nuevos ataques" y "3.2: algún alivio":** Los umbrales para medir la escalada de Israel o la concesión de Estados Unidos son tan vagos que el sesgo de confirmación del operador inevitablemente los interpretará a su favor.
5. **Resolver la contradicción matemática de T1 en H-4:** No se puede exigir evaluar si T1 se resolvió "en la dirección que el método consideró más probable" cuando el protocolo no le asignó ninguna probabilidad matemática previa.

## Inferencia generada

Claude revisó cada observación contra el documento y el operador decidió. De 16 observaciones: 7 se aceptaron tal cual, 5 se aceptaron con otra solución y 4 se rechazaron (3.6, 3.3, el vacío de T1 indeterminada, que la sección 7 ya cubría, y la integración de 3.8 y 3.9 a la tabla 6.2, resuelta con una nota). Claude agregó dos observaciones que Gemini no hizo: el mínimo de errores para H-1 y V-1, y la debilidad de P-1 como prueba de conciliencia.

El operador declaró que no tiene la formación para fijar umbrales numéricos y que aprobó las propuestas apoyándose en Claude y Gemini (sección 10 del prerregistro).

## Impacto en el modelo

Cambios en el prerregistro antes de congelarlo: ver su sección 12. Las observaciones aceptadas que eran errores del borrador de Claude se registraron en `investigacion/registro-errores.csv` (E25 a E33) como errores prospectivos detectados por una fuente externa. Las dos observaciones que agregó Claude, más una inconsistencia de fechas del borrador, quedaron en E34 a E36.
