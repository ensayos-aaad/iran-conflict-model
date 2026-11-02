# P1 — Revisión externa del diseño A/B por ChatGPT

**Fecha:** 2026-10-31 (preparación; la revisión se hace entre el 1 y el 3 de noviembre)
**Sesión:** línea de investigación (no es una sesión del ICM)
**Tipo:** Validación
**Peldaño Pearl:** N/A
**Impacto en modelo:** Alto (puede cambiar el diseño antes de congelarlo)

**Herramienta:** ChatGPT, *(modelo y versión: se completan al hacer la revisión)*. Se usa un **chat temporal** (o con la memoria desactivada), para que no influyan conversaciones anteriores del operador.
**Ejecución real (1 nov 2026):** modelo **GPT-5.6 Sol**, razonamiento **"Media"** (por defecto), según el selector de la interfaz. **Desviación del plan:** el chat **no fue temporal**: se abrió dentro de un proyecto de ChatGPT llamado "ensayos", que el operador creó para esta revisión. Contenido previo de las fuentes y chats del proyecto, y hora: *(pendiente de que el operador lo informe)*.
**Documentos adjuntos:** (1) `investigacion/diseno-experimento-ab.md`, en el commit `0defe5e` (sin cambios hasta la revisión); (2) `investigacion/protocolo-evaluacion-cierre-2026.md`, el prerregistro congelado, solo como referencia.
**No se adjunta:** la lista de hechos del operador para la S16, ni ningún otro archivo.
**Por qué ChatGPT y no Gemini:** Gemini será el evaluador en enero de 2027; si además revisara este diseño, perdería independencia.

## Prompt

Se pega tal cual como primer mensaje, con los dos archivos adjuntos:

```text
Eres un revisor metodológico independiente y escéptico. Vas a revisar el borrador
del diseño de un experimento A/B (archivo "diseno-experimento-ab.md") antes de que
se congele. Lo redactó otra IA (Claude, de Anthropic), que además va a producir los
dos brazos del experimento. El riesgo principal es que el diseño favorezca, sin
querer, a uno de los brazos. Tu trabajo es encontrar debilidades, no aprobarlo.

Contexto y restricciones fijas (no propongas cambiarlas; si alguna invalida el
experimento, dilo):
- Es un estudio de caso sobre un método de análisis humano-IA aplicado a un
  conflicto geopolítico real. Hay un solo operador humano, que no es experto en
  metodología, y no hay evaluador humano independiente.
- El otro archivo es un prerregistro YA CONGELADO y público. No se puede modificar;
  este diseño es una extensión aparte.
- Gemini (Google) será el evaluador en enero de 2027. Por eso no puede ser un brazo
  ni revisar este diseño.
- Solo hay una sesión por brazo (n = 1). Los pronósticos se resuelven entre el 31 de
  diciembre de 2026 y el 2 de enero de 2027.
- El diseño debe congelarse antes del 5 de noviembre de 2026.

Revisa y responde en español, con estas secciones:

1. VALIDEZ INTERNA. ¿Hay formas en que la información de un brazo llegue al otro,
   o en que los brazos reciban condiciones distintas (fecha de corte, fuentes,
   esfuerzo, insumos)? ¿El mensaje fijo del anexo A deja a Claude en desventaja o en
   ventaja frente al brazo B?

2. MEDICIÓN. ¿Las métricas M-AB1 a M-AB5 miden lo que dicen medir? ¿"Relevante",
   "exclusivo", "equivalente" y "error" están definidos lo bastante bien como para
   que dos evaluadores lleguen al mismo conteo? ¿El ciego parcial es viable?

3. TABLA DE DECISIÓN. ¿Algún umbral o fila de la sección 7 hace más fácil concluir
   a favor de un brazo? ¿Hay resultados plausibles que no caigan en ninguna fila?

4. FACTIBILIDAD. Con las restricciones de arriba, ¿hay algo que no se pueda
   ejecutar o calificar tal como está escrito?

5. COHERENCIA CON EL PRERREGISTRO. ¿El diseño contradice o cambia, aunque sea
   indirectamente, alguna regla del prerregistro congelado?

6. LO QUE FALTA para que un evaluador externo pueda aplicar el diseño en enero de
   2027 sin consultar a los autores.

Formato: para cada sección, una tabla con las columnas
| Sección del documento | Problema | Gravedad (alta/media/baja) | Propuesta |
Al final, una lista de las 5 correcciones más importantes, en orden, y una
respuesta en una línea a esta pregunta: con n = 1, ¿vale la pena hacer este
experimento o es mejor no hacerlo? Explica por qué.

No reescribas el documento entero. No evalúes si el conflicto o el método son
interesantes; solo la calidad del diseño. Si algo está bien, no hace falta
comentarlo. Basa cada observación en el texto del documento y cita la sección.
```

## Respuesta del sistema — ronda 1

```
He revisado el diseño como una **extensión autónoma** y no como una oportunidad para reabrir el prerregistro. Mi conclusión general es que el experimento es ejecutable como **estudio exploratorio de caso**, pero todavía tiene vulnerabilidades importantes que pueden hacer que la comparación A/B sea difícil de interpretar. Las más serias no son n=1 en sí, sino la falta de control del esfuerzo/información entre brazos, la contaminación potencial A→B y el uso inferencial del *bootstrap*.

## 1. VALIDEZ INTERNA

| Sección del documento | Problema | Gravedad (alta/media/baja) | Propuesta |
|---|---|---:|---|
| §2 Brazos + §3 Fecha y orden | **Los brazos no tienen exposición temporal comparable.** A se ejecuta el día C; B comienza después y explícitamente “dura varios días”. Aunque B tenga prohibido citar noticias posteriores a C, el operador y Claude pueden conocer hechos ocurridos después de C y esa información puede influir implícitamente en selección, interpretación o probabilidades. diseno-experimento-ab diseno-experimento-ab | **Alta** | Declarar que la fecha de publicación de fuentes no basta como aislamiento. Registrar inicio/fin de cada brazo y exigir que B documente cualquier conocimiento posterior a C detectado durante la sesión. Tratar la posible contaminación temporal como amenaza primaria, no solo como limitación menor. |
| §3 + §4 | **Posible contaminación A→B a través de Claude.** Se impide que Claude “abra” `brazo-a.md`, pero el propio diseño reconoce que la memoria de Claude se carga automáticamente. No se especifica cómo garantizar que la ejecución de A no modifique contexto/memoria disponible en B. diseno-experimento-ab | **Alta** | Antes de congelar, fijar una regla explícita: B debe ejecutarse en un contexto independiente que no incorpore memoria generada durante A; si eso no puede garantizarse técnicamente, declarar **contaminación potencial A→B no controlable** y rebajar cualquier interpretación causal. |
| §2, Plan de fuentes | El diseño afirma “los mismos bloques”, pero B puede **agregar o quitar fuentes**, mientras A debe decidir sus búsquedas bajo un mensaje fijo. Por tanto, “mismo plan de fuentes” de la pregunta de investigación no está garantizado. diseno-experimento-ab diseno-experimento-ab | **Alta** | Congelar qué significa “mismo plan”: mismos bloques obligatorios, mismas reglas de inclusión y misma posibilidad de incorporar fuentes adicionales. Una desviación debería clasificarse previamente como violación de protocolo, no simplemente “declararse”. |
| §2 + Anexo A | **El esfuerzo no está igualado.** A recibe instrucciones de trabajar “hasta cumplir los criterios de parada”, pero B recibe interacción humana y puede prolongarse varios días. No hay presupuesto común de tiempo, búsquedas, consultas o iteraciones. diseno-experimento-ab diseno-experimento-ab | **Alta** | Como la intervención B necesariamente incorpora diálogo, no igualaría número de mensajes; pero sí debe fijarse un criterio observable de parada común y registrar tiempo, número de búsquedas, fuentes examinadas y duración. Esos datos deben acompañar el resultado. |
| Anexo A | El mensaje le dice expresamente a Claude que está produciendo el **“BRAZO A (‘Claude solo’)”** de un experimento cuyo diseño debe leer. Claude conoce entonces la hipótesis, la comparación y que B será el protocolo completo. Esto permite *experimenter expectancy* en el propio modelo generador. diseno-experimento-ab | **Alta** | El mensaje de ejecución de A debería contener solo las instrucciones necesarias para producir la salida, no la identidad “brazo A”, la pregunta comparativa ni la tabla de decisión. El diseño puede permanecer accesible para auditoría, pero no debería ser necesario que el generador lea qué resultado lo favorece o desfavorece. |
| Anexo A vs §2 | A tiene una **restricción explícita de archivos** —“no abras otros archivos de investigación ni prompts”—. Para B, la tabla dice “los mismos [insumos], más la lista”, pero no existe una instrucción operacional equivalente que le prohíba material adicional. diseno-experimento-ab diseno-experimento-ab | **Alta** | Aplicar una lista positiva idéntica de archivos permitidos a ambos brazos, añadiendo únicamente la lista del operador en B. |
| §4 | Ya existe una **filtración conocida** de tres temas del operador. Prohibir abrir el archivo reduce el riesgo, pero el diseño admite que no puede garantizarlo. diseno-experimento-ab | Media | No tratar esos temas como evidencia de “aporte exclusivo del operador” si aparecen en B. Predefinir que cualquier hecho derivado directamente de esos tres temas quede marcado como potencialmente contaminado en M-AB1. |
| §3 | Solo A tiene una regla de **reintento** explícita si la sesión falla. No existe regla equivalente para B. diseno-experimento-ab | Media | Definir simétricamente qué constituye fallo técnico, cuándo puede continuarse/repetirse y qué versión entra al análisis para ambos brazos. |

**Sobre la pregunta concreta del Anexo A:** no veo una ventaja metodológica limpia para Claude-A. Más bien veo **dos fuerzas opuestas**: A está perjudicado porque tiene más restricciones operativas y carece de interacción, pero puede beneficiarse porque conoce explícitamente que está siendo evaluado como “Claude solo” y puede optimizar su conducta para el experimento. El problema es precisamente que no sabemos cuál efecto domina.

---

## 2. MEDICIÓN

| Sección del documento | Problema | Gravedad (alta/media/baja) | Propuesta |
|---|---|---:|---|
| §6 M-AB1 | La definición mezcla dos cantidades diferentes: “número de hechos relevantes y verificados” y después “se cuentan los hechos **exclusivos**”. No queda claro si M-AB1 es cobertura total o diferencia exclusiva. diseno-experimento-ab | **Alta** | Separar formalmente: total A, total B, compartidos, exclusivos A y exclusivos B. Definir cuál es la métrica primaria. |
| §6 M-AB1 | **“Equivalente” no está operacionalizado.** Dos brazos pueden describir el mismo episodio con distinta granularidad; un brazo puede dividir un hecho en tres y el otro condensarlo en uno. El evaluador decide equivalencia sin rúbrica. diseno-experimento-ab | **Alta** | Definir unidad de conteo y regla de equivalencia antes de ejecutar: mismo actor + mismo evento/acción + misma ventana temporal + misma consecuencia principal, por ejemplo. Añadir ejemplos límite. |
| §6 | **“Relevante” es excesivamente amplio:** basta con tratar de un actor o evento relacionado con Q1–Q8 o con cualquiera de seis escenarios. Con un conflicto geopolítico, eso puede incluir una fracción enorme de las noticias. diseno-experimento-ab | Media | Exigir que el hecho pueda cambiar razonablemente una probabilidad Q1–Q8 o discriminar entre ≥2 escenarios, y que el brazo indique cuál y por qué. |
| §6 M-AB1/M-AB2 | “Verificado” y “error” no son complementarios. M-AB2 solo considera errores en hechos marcados ✅ cuya fuente no los sostiene o cuya **fecha** es incorrecta. Quedan fuera sujeto equivocado, causalidad exagerada, atribución incorrecta, contradicción entre fuentes, etc. diseno-experimento-ab | **Alta** | Alinear “error factual” con una rúbrica cerrada: hecho no sostenido, actor/sujeto incorrecto, fecha incorrecta, magnitud incorrecta y afirmación más fuerte que las fuentes. Mantener inferencias analíticas aparte. |
| §6 M-AB2 | La tasa `errores/hechos ✅` tiene casos límite no definidos: cero hechos ✅, denominadores muy pequeños y diferencias de una sola observación. | Media | Predefinir `NA` si denominador=0 y reportar siempre numerador/denominador además del porcentaje. No interpretar diferencias diminutas como evidencia sustantiva. |
| §6 M-AB3 | El **bootstrap pareado de 8 preguntas no produce un IC válido del “efecto del protocolo”** en este diseño. Las preguntas no son una muestra aleatoria de una población de preguntas y además Q7/Q8 están explícitamente correlacionadas. El propio documento reconoce que el intervalo será optimista. diseno-experimento-ab diseno-experimento-ab | **Alta** | Conservar el remuestreo, si se desea, solo como análisis descriptivo de sensibilidad. No llamarlo evidencia de diferencia “distinguible” ni usar que excluya 0 como criterio cuasi-inferencial. El resultado principal debe ser ΔBrier observado y Brier por pregunta. |
| §6 M-AB4 | Las tres predicciones de patrón **no son las mismas entre brazos**. Cada brazo escoge sus propias preguntas y su dificultad. Comparar sus Brier o incluso interpretar cada uno frente a 0,25 mezcla capacidad de pronóstico con capacidad para escoger problemas fáciles. diseno-experimento-ab diseno-experimento-ab | **Alta** | Definir M-AB4 como evaluación descriptiva de cada conjunto, no comparación causal entre brazos. Exigir además que cada predicción cumpla la definición del prerregistro de “conexión”: predice hechos distintos de aquellos que originaron el patrón. |
| §6 M-AB4 | **“Nueva” no está definido:** nueva respecto de S15, del repositorio, de las creencias de Claude, de la lista del operador o de toda la literatura examinada. | Media | Fijar el referente exacto de novedad y exigir que cada brazo indique su evidencia de que la predicción no estaba ya formulada en sus insumos permitidos. |
| §7 R-6 | Brier >0,25 con solo tres preguntas no justifica literalmente que las conexiones fueron **“mayormente”** falsa conciliencia. Un único error de alta confianza puede producirlo aunque dos de tres acierten. diseno-experimento-ab | **Alta** | Cambiar la interpretación por “el conjunto tuvo peor Brier que la referencia 50%”. No traducir automáticamente esa métrica a “mayormente falsa conciliencia”. |
| §8 Ciego parcial | El ciego es **frágil**. Aunque X/Y oculten la etiqueta, el contenido puede revelar el brazo: hechos aportados por el operador, estilo dialógico, selección de temas o rastros de la salida. diseno-experimento-ab | Media | Llamarlo explícitamente “enmascaramiento de etiqueta”, no cegamiento del tratamiento. Pedir a Gemini que, antes de calificar, indique si cree poder inferir X/Y y con qué confianza; esa inferencia se archiva. |
| §8 | No se especifica cómo se aleatorizan X/Y ni cuándo se crea/guarda la clave. | Media | Usar un procedimiento reproducible previo a la evaluación, registrar semilla/resultado y archivar la clave sin revelarla a Gemini. |

En su estado actual, **dos evaluadores razonables pueden obtener conteos distintos en M-AB1 y M-AB2**, especialmente por equivalencia/granularidad y por el alcance de “error”. Por tanto, esas métricas todavía no están suficientemente cerradas para enero.

---

## 3. TABLA DE DECISIÓN

| Sección del documento | Problema | Gravedad (alta/media/baja) | Propuesta |
|---|---|---:|---|
| §7 R-1–R-3 | El criterio “IC excluye 0” convierte un *bootstrap* descriptivamente débil en una especie de prueba inferencial. Con 8 preguntas fijas y correlacionadas, la interpretación “pronostica mejor” es demasiado fuerte. diseno-experimento-ab | **Alta** | Basar la conclusión en el signo y magnitud de ΔBrier observado, reportando el remuestreo solo como sensibilidad. Usar lenguaje “en estas preguntas”, no “el protocolo pronostica mejor”. |
| §7 R-4 | El umbral de **≥3** hechos exclusivos no tiene derivación independiente; el propio documento reconoce que es recomendación de Claude, que produce los brazos. diseno-experimento-ab | **Alta** | Si se mantiene, etiquetarlo como umbral convencional/arbitrario y reportar obligatoriamente los conteos sin umbral. No dejar que el resultado binario sustituya los datos. |
| §7 R-4 | Hay **asimetría**: existe una regla para concluir que B amplía cobertura, pero ninguna regla espejo para concluir que A tuvo mayor cobertura. Si A obtiene 10 exclusivos y B 0, la lectura formal es simplemente “no se observa ampliación”. diseno-experimento-ab | **Alta** | Añadir una fila simétrica: si A cumple el mismo criterio frente a B, “Claude solo mostró mayor cobertura en esta sesión”. |
| §7 R-5 | “Cualquier aumento” de la tasa de errores penaliza B aunque sea, por ejemplo, 1/30 frente a 0/25. Con denominadores pequeños, eso puede ser ruido de conteo. Esta regla es **más dura con B**. diseno-experimento-ab | Media | Mantener la condición estricta si responde literalmente a “sin aumentar”, pero distinguir “aumento observado” de “degradación sustantiva” y reportar siempre números absolutos. |
| §7 + H-AB1 | H-AB1 dice sencillamente “B tiene más hechos relevantes verificados que A”; R-4 exige además ≥3 **exclusivos**. Hipótesis y decisión no son la misma variable. diseno-experimento-ab diseno-experimento-ab | **Alta** | Hacer coincidir formalmente hipótesis, métrica y fila de decisión, o declarar un resultado descriptivo para H-AB1 y otro criterio separado de importancia práctica. |
| §7 R-6 | Solo define el caso Brier >0,25. No especifica la interpretación de =0,25 o <0,25, ni cómo comparar los dos brazos cuando uno supera 0,25 y el otro no. | Media | Completar los estados posibles y dejar explícito que no se trata de comparación directa si las tres preguntas de A y B son diferentes. |
| §7 | No existe regla para el caso en que el número de preguntas Q1–Q8 evaluables sea muy pequeño por indeterminación. El documento solo dice que una pregunta indeterminada sale de ambos Brier. diseno-experimento-ab | **Alta** | Fijar un mínimo antes de congelar. Por debajo de él: “comparación de pronóstico no evaluable”, sin R-1/R-2/R-3. |
| §7 | Tampoco se define qué hacer si una o más de las tres predicciones nuevas de patrón resultan no resolubles conforme a su propia regla. | Media | Predefinir mínimo evaluable y tratamiento de predicciones indeterminadas. |

Sí hay resultados plausibles insuficientemente tratados: **A claramente mayor que B en cobertura**, muy pocas Q evaluables, predicciones de patrón indeterminadas, denominador cero en errores y Brier de patrones ≤0,25. El problema más importante es que la tabla sí permite una afirmación positiva explícita para superioridad de B en cobertura, pero no su espejo para A.

---

## 4. FACTIBILIDAD

| Sección del documento | Problema | Gravedad (alta/media/baja) | Propuesta |
|---|---|---:|---|
| §2 | “El mismo modelo de Claude” es ejecutable solo si puede utilizarse una versión efectivamente idéntica. Registrar un nombre comercial/identificador no garantiza por sí mismo un modelo inmutable entre días. diseno-experimento-ab | Media | Registrar identificador expuesto, fecha/hora y cualquier versión/build disponible. Si no puede garantizarse identidad, decir “misma opción de modelo disponible”, no equivalencia perfecta. |
| §3 | B puede durar varios días manteniendo un corte C anterior. **Es ejecutable documentalmente**, pero no es posible garantizar que el operador desconozca acontecimientos post-C. diseno-experimento-ab | **Alta** | Declarar que solo se controla la evidencia citada, no todo el conocimiento del operador. Eso limita la inferencia causal pero no obliga a cancelar el estudio. |
| §8 | El pipeline de Brier/*bootstrap* está “pendiente” aunque la tabla de decisión depende de él. diseno-experimento-ab | **Alta** | El código, fórmula exacta, tratamiento de NA, semilla y formato de entrada deben quedar congelados **antes de observar resultados**. |
| §6/Anexo B | El evaluador debe decidir equivalencias de hechos, pero no dispone de un algoritmo/rúbrica suficiente. Técnicamente puede calificar, pero no **reproduciblemente**. | **Alta** | Añadir la rúbrica antes del congelamiento. |
| §8 | Con un solo operador, el segundo “evaluador” independiente es Gemini, pero el operador seguirá siendo participante de B y evaluador. Esto es viable, pero la independencia solo existe en uno de los dos juicios. diseno-experimento-ab | Media | No combinar evaluaciones en un único consenso; conservar ambos resultados por separado, como ya hace el espíritu del prerregistro. |
| §3 | La regla de reejecución solo contempla fallo de A. Si B se interrumpe, el protocolo no indica cuándo continúa la misma sesión ni cuándo es inválida/repetida. | Media | Fijar ahora una política simétrica de fallos técnicos. |

No veo una restricción fija que haga **imposible ejecutar** el estudio. Sí veo una que impide una interpretación causal fuerte: con un solo operador y B ejecutado después de A y potencialmente después de C, no se puede asegurar aislamiento completo de información.

---

## 5. COHERENCIA CON EL PRERREGISTRO

El prerregistro autoriza expresamente que antes de S16 se prerregistre “por separado un experimento A/B” como extensión, sin modificarlo. Por tanto, **la existencia del experimento A/B es coherente** con el documento congelado. protocolo-evaluacion-cierre-2026

| Sección del documento | Problema | Gravedad (alta/media/baja) | Propuesta |
|---|---|---:|---|
| A/B §5 Q7 vs prerregistro §4 T1 | Q7 se presenta usando “las reglas de T1”, pero cambia su ventana: T1 comienza el **4 de noviembre**; Q7 comienza **el día siguiente a C**, que puede ser entre el 6 y el 11 de noviembre. No es la misma pregunta. diseno-experimento-ab protocolo-evaluacion-cierre-2026 | **Alta** | Etiquetar Q7 inequívocamente como **pregunta nueva derivada de T1**, que reutiliza definiciones pero no su ventana. Nunca usar el resultado de Q7 para recalificar T1. |
| A/B §5 Q8 vs prerregistro §5 K26-T | Igual problema: K26-T cubre 4 nov–2 ene; Q8 comienza el día posterior a C. Por tanto omite acontecimientos válidos para K26-T ocurridos entre el 4 de noviembre y C. diseno-experimento-ab protocolo-evaluacion-cierre-2026 | **Alta** | Tratar Q8 como nueva pregunta A/B. Mantener completamente separada la resolución oficial de K26-T. |
| A/B §7 R-6 vs prerregistro §7 H-4 | El texto dice que R-6 usa “el mismo criterio que H-4”. Pero H-4 se aplica a **P-1, P-2 y P-3 fijadas el 10 de octubre**; R-6 se aplica a tres predicciones nuevas y autoescogidas por cada brazo. No son metodológicamente equivalentes. diseno-experimento-ab protocolo-evaluacion-cierre-2026 | **Alta** | Eliminar la afirmación de equivalencia. Puede reutilizarse la referencia Brier=0,25, pero no presentarse como aplicación de H-4. |
| A/B §8 vs prerregistro §8 | El A/B dice que el “titular usa la lectura menos favorable al brazo B, **como en el prerregistro**”. El prerregistro realmente dice “menos favorable **al método**”. B representa el método completo, por lo que es compatible en espíritu, pero no es literalmente la misma regla. diseno-experimento-ab protocolo-evaluacion-cierre-2026 | Media | Decir explícitamente que es una **regla nueva conservadora del A/B**, inspirada en el prerregistro, no una regla ya prerregistrada. |
| A/B propósito | Debe evitarse que los resultados del A/B sean usados retrospectivamente para modificar H-1…H-4 o V-1/V-2 del prerregistro. El prerregistro exige que su tabla se aplique “tal cual”. protocolo-evaluacion-cierre-2026 | **Alta** | Añadir una frase explícita: “ninguna métrica ni resultado del A/B entra en la aplicación de H-1–H-4/V-1–V-2; se reporta en una sección separada”. |
| Prerregistro §8 vs A/B | El prerregistro ordena que Gemini califique ese estudio con el prerregistro congelado y fuentes de resolución. El A/B prevé **otra Gem distinta**, lo cual evita una contradicción directa. protocolo-evaluacion-cierre-2026 diseno-experimento-ab | Baja | Mantener físicamente separadas las dos evaluaciones y sus instrucciones para evitar contaminación accidental. |

No detecto una modificación directa del prerregistro congelado, pero **Q7, Q8 y R-6 deben separarse semánticamente de T1, K26-T y H-4**. En la redacción actual parecen más equivalentes de lo que realmente son.

---

## 6. LO QUE FALTA PARA QUE UN EVALUADOR EXTERNO PUEDA APLICARLO EN ENERO DE 2027

| Sección del documento | Problema | Gravedad (alta/media/baja) | Propuesta |
|---|---|---:|---|
| §6 M-AB1 | Falta una **rúbrica de equivalencia y granularidad de hechos**. | **Alta** | Incluir criterios deterministas y ejemplos de mismo hecho / hechos distintos / parcialmente solapados. |
| §6 M-AB1 | Falta especificar exactamente qué significa “verificado”: ¿basta que el brazo marque ✅ o el evaluador debe volver a comprobar las dos fuentes? | **Alta** | El evaluador debe comprobar independientemente que las fuentes sostienen el hecho y cumplen bloques distintos. |
| §6 M-AB2 | Falta taxonomía completa de error y reglas para denominador cero. | **Alta** | Definir tipos y `NA`. |
| §6 M-AB3 | Falta el pipeline congelado, incluyendo tratamiento de preguntas indeterminadas, promedio, remuestreo, semilla y producción de intervalos. | **Alta** | Congelar código y pruebas con datos ficticios antes de ejecutar los brazos. |
| §6 M-AB4 | Falta criterio de **novedad**, de qué cuenta como “patrón” y de independencia entre evidencia originadora y evento pronosticado. | **Alta** | Incorporar explícitamente la definición de conexión del prerregistro: la predicción debe ser sobre hechos distintos de los que originaron el patrón. El prerregistro hace de esa condición el núcleo de la conciliencia. protocolo-evaluacion-cierre-2026 |
| §6 M-AB4 | Falta regla para predicciones no resolubles/indeterminadas. | Media | Definir exclusión y mínimo de predicciones evaluables. |
| §7 | Falta mínimo de Q1–Q8 para poder aplicar R-1–R-3. | **Alta** | Establecerlo antes del congelamiento. |
| §7 | Falta una fila espejo de R-4 para superioridad de cobertura de A. | **Alta** | Añadirla. |
| §8 | Falta procedimiento concreto de aleatorización X/Y. | Media | Algoritmo simple, semilla y archivo de clave. |
| §8 | Falta una instrucción específica a Gemini para M-AB1/M-AB2. Las instrucciones del prerregistro solo cubren la evaluación original y no enseñan a emparejar hechos entre dos anexos. protocolo-evaluacion-cierre-2026 | **Alta** | Congelar un anexo propio de instrucciones del evaluador A/B. |
| §8 | Falta decir qué material exacto recibe Gemini para verificar las **fuentes de los hechos**, además de las fuentes de resolución de pronósticos. | Media | Definir paquete de evaluación cerrado: diseño, X, Y, URLs/citas de cada hecho, fuentes de resolución y nada más. |
| §2/§3 | Falta un registro mínimo de exposición/esfuerzo: duración, búsquedas, fuentes inspeccionadas, interrupciones y desviaciones. | Media | Incluir una hoja de ejecución idéntica para ambos brazos. |
| §3/§4 | Falta una regla para determinar después si hubo contaminación post-C o A→B y qué efecto tiene sobre la validez del experimento. | **Alta** | Predefinir categorías: sin evidencia de contaminación / posible / confirmada; si es confirmada, conservar resultados pero declarar inválida la comparación causal correspondiente. |

### Las 5 correcciones que considero prioritarias

1. **Eliminar o controlar la contaminación A→B**, especialmente la memoria/contexto persistente de Claude, y registrar cualquier exposición de B a información posterior a C. Si no puede garantizarse, declararlo como limitación que impide inferencia causal fuerte.
2. **Operacionalizar M-AB1 y M-AB2**: unidad de hecho, equivalencia, granularidad, relevancia, verificación y error. Hoy esta es probablemente la mayor fuente de discrecionalidad del evaluador.
3. **Quitar al bootstrap su papel decisorio inferencial**. Con ocho preguntas fijas, correlacionadas y no muestreadas aleatoriamente, que un intervalo excluya 0 no debería decidir que un protocolo “pronostica mejor”.
4. **Cerrar las asimetrías de la tabla de decisión**, sobre todo añadiendo el espejo de R-4 para A y definiendo mínimos de datos para Brier y predicciones de patrón.
5. **Separar formalmente el A/B del prerregistro original**: Q7 ≠ T1, Q8 ≠ K26-T y R-6 ≠ H-4. Ningún resultado de esta extensión debería recalificar las filas H/V congeladas.

**Con n = 1, sí vale la pena hacerlo, pero únicamente como estudio de caso exploratorio/auditable y generador de hipótesis, no como experimento capaz de establecer que humano+IA es superior a IA sola; cancelarlo perdería información útil, pero sobreinterpretarlo sería metodológicamente peor que no hacerlo.**
```

## Réplica de Claude — ronda 1

> **Aprobada por el operador sin cambios el 1 nov 2026, incluidos los seis puntos "acepto en parte" (1.3, 1.4, 1.5, 2.3, 3.4, 4.3), antes de enviarla.** Claude escribió el diseño, así que tiene conflicto de interés: por eso cada "acepto en parte" o "no estoy de acuerdo" se le mostró al operador. Las marcas "diseno-experimento-ab" y "protocolo-evaluacion-cierre-2026" dentro de la respuesta de arriba son citas a los adjuntos que insertó la interfaz de ChatGPT.

Mensaje que se pega en el mismo chat de ChatGPT:

```text
Gracias. Soy Claude, el autor del borrador. Tengo conflicto de interés, así que
el operador revisa cada punto que no acepto completo. Respondo a cada
observación. Numero las filas por sección (1.1 es la primera fila de la
sección 1, etc.). Las filas de tu sección 6 que repiten otras remiten a ellas.

SECCIÓN 1. VALIDEZ INTERNA
1.1 Exposición temporal — ACEPTO. La contaminación post-C pasa a ser amenaza
    primaria. Se registran inicio y fin de cada brazo, y B lleva un registro de
    cualquier conocimiento posterior a C que aparezca en la sesión.
1.2 Contaminación A→B por memoria — ACEPTO, con un control concreto. La memoria
    de Claude Code depende de la carpeta del proyecto. A se corre en una copia
    nueva del repositorio en otra carpeta, cuya memoria empieza vacía, y la
    memoria del proyecto principal se huella con SHA-256 antes y después de A.
    Si cambia, se declara contaminación posible.
1.3 Mismo plan de fuentes — ACEPTO EN PARTE. Fijo los bloques obligatorios y
    las reglas de inclusión iguales, y ambos brazos pueden añadir fuentes. No
    acepto clasificar como violación que B agregue fuentes: las fuentes que
    trae el operador son parte del tratamiento que se mide. Sí será violación
    omitir un bloque obligatorio, en cualquier brazo.
1.4 Esfuerzo — ACEPTO EN PARTE. SEG ya tiene un criterio de parada de la
    búsqueda (§6: cuando las búsquedas ya no devuelven hechos nuevos
    relevantes), pero en B admite "o cuando el operador lo indica". En B se
    elimina esa salida: la búsqueda propia de Claude termina por el mismo
    criterio que en A. Se registran duración, número de búsquedas y fuentes
    examinadas en una hoja de ejecución idéntica.
1.5 El mensaje revela "brazo A" — ACEPTO EN PARTE. Quito del mensaje la
    etiqueta, la hipótesis y la tabla de decisión, y A ya no lee el diseño:
    recibe solo las preguntas Q1–Q8 y la plantilla del anexo estándar. Pero el
    enmascaramiento no puede ser completo: CLAUDE.md, que es un insumo, describe
    el experimento. Propongo que en la copia de A se use un CLAUDE.md sin la
    sección de la línea de investigación (no hace falta para un seguimiento) y
    declarar el resto. Además hay una asimetría que tu revisión no menciona: el
    brazo B no se puede enmascarar, porque el operador y Claude saben que es B.
    Se declara.
1.6 Lista de archivos de B — ACEPTO. Lista positiva idéntica para ambos, más
    la lista del operador en B.
1.7 Filtración conocida — ACEPTO. Los hechos derivados de esos tres temas se
    marcan como potencialmente contaminados y no cuentan como exclusivos de B.
1.8 Fallos simétricos — ACEPTO. Una regla común: si una sesión se corta y se
    puede continuar, se continúa con "Continúa."; si no, se repite una vez, y si
    vuelve a fallar ese brazo se declara nulo.

SECCIÓN 2. MEDICIÓN
2.1 M-AB1 mezcla cantidades — ACEPTO. Se reportan total A, total B,
    compartidos, exclusivos A y exclusivos B. Primaria: exclusivos de cada brazo.
2.2 Equivalencia — ACEPTO. Unidad: un evento = mismo actor principal + misma
    acción + misma fecha (±3 días). Si un brazo parte un evento en varias filas,
    el evaluador las fusiona antes de contar. Solapamiento parcial = compartido.
    Con ejemplos límite.
2.3 Relevancia amplia — ACEPTO EN PARTE. "Puede cambiar razonablemente una
    probabilidad" es otro juicio. Propongo: el brazo nombra la pregunta o
    escenario (ya está en la tabla 2) y el evaluador comprueba que el hecho
    toca directamente la regla de resolución de esa pregunta o la definición de
    ese escenario. Si no, no es relevante.
2.4 Taxonomía de error — ACEPTO tu lista cerrada (no sostenido, actor
    incorrecto, fecha incorrecta, magnitud incorrecta, afirmación más fuerte que
    las fuentes), más "fuentes no son de bloques distintos" para un ✅.
2.5 NA y números absolutos — ACEPTO.
2.6 Bootstrap — ACEPTO. Queda solo como sensibilidad descriptiva.
2.7 M-AB4 no comparable — ACEPTO. Descriptiva por brazo, con la definición de
    conexión del prerregistro.
2.8 "Nueva" — ACEPTO. Nueva = no formulada en la S15 ni en los insumos
    permitidos del brazo; el brazo declara que lo comprobó.
2.9 R-6 "mayormente" — ACEPTO tu redacción.
2.10 Enmascaramiento — ACEPTO el nombre y que Gemini declare si cree inferir
    X/Y y con qué confianza, antes de calificar.
2.11 Aleatorización — ACEPTO. Propongo una regla que nadie puede manipular: el
    último dígito hexadecimal del hash del commit de B; si es par, B = X.

SECCIÓN 3. TABLA DE DECISIÓN
3.1 IC excluye 0 — ACEPTO. Nueva regla sin umbral numérico: R-1 si
    Brier(A) − Brier(B) > 0 y B tiene menor Brier en más preguntas evaluables
    que A → "en estas preguntas, B pronosticó mejor (señal descriptiva)". R-2
    es el espejo. R-3 en cualquier otro caso → "sin diferencia clara".
3.2 Umbral ≥3 — ACEPTO. Se etiqueta como convencional y se publican siempre
    los conteos.
3.3 Espejo de R-4 para A — ACEPTO. Es la observación más importante: el
    borrador favorecía a B.
3.4 R-5 duro con B — ACEPTO EN PARTE. Mantengo la regla estricta, porque la
    pregunta pide "sin aumentar", y como propones se reporta "aumento observado"
    con numerador y denominador. No agrego un umbral de "degradación
    sustantiva": con estos tamaños sería otro número arbitrario mío.
3.5 H-AB1 ≠ R-4 — ACEPTO. H-AB1 se redacta sobre exclusivos.
3.6 Estados de R-6 — ACEPTO.
3.7 Mínimo de Q evaluables — ACEPTO. Propongo 5 de 8 (más de la mitad); por
    debajo, "comparación de pronóstico no evaluable".
3.8 Predicciones de patrón indeterminadas — ACEPTO. Mínimo 2 de 3 por brazo.

SECCIÓN 4. FACTIBILIDAD
4.1 Identidad del modelo — ACEPTO: "misma opción de modelo", con identificador,
    fecha y hora.
4.2 Conocimiento post-C del operador — ACEPTO (igual que 1.1).
4.3 Pipeline — ACEPTO EN PARTE. La fórmula, el tratamiento de NA, la regla de
    R-1 a R-3 y la semilla quedan escritas en el diseño congelado. El código y
    sus pruebas con datos ficticios se congelan con commit antes del 31 dic,
    cuando se resuelven las primeras preguntas, es decir, antes de observar
    resultados, pero no necesariamente antes del 5 nov: no hay tiempo, y como
    la regla ya está escrita, el código no puede cambiarla.
4.4 Rúbrica — ACEPTO (igual que 2.2).
4.5 Evaluaciones separadas — ACEPTO; ya era así, lo hago explícito.
4.6 Fallos simétricos — ACEPTO (igual que 1.8).

SECCIÓN 5. COHERENCIA CON EL PRERREGISTRO
5.1 y 5.2 Q7 ≠ T1, Q8 ≠ K26-T — ACEPTO. Se etiquetan como preguntas nuevas
    derivadas. La ventana empieza después de C a propósito, porque nadie puede
    pronosticar lo ya ocurrido al momento del corte.
5.3 R-6 ≠ H-4 — ACEPTO.
5.4 Regla del titular — ACEPTO. Se declara como regla nueva del A/B.
5.5 Ningún resultado del A/B recalifica H-1 a H-4 ni V-1 y V-2 — ACEPTO.
5.6 Gems separadas — ACEPTO; ya era así.

SECCIÓN 6. LO QUE FALTA
"Verificado" — ACEPTO: el evaluador comprueba que las dos fuentes sostienen el
hecho y son de bloques distintos. Anexo de instrucciones para Gemini — ACEPTO.
Paquete cerrado de evaluación — ACEPTO. Categorías de contaminación (sin
evidencia / posible / confirmada) — ACEPTO. El resto remite a filas anteriores.

CONCLUSIÓN SOBRE n = 1: de acuerdo. El diseño se presentará como estudio de
caso exploratorio y generador de hipótesis.

PARA LA RONDA 2, responde solo esto:
a) Los puntos donde acepto en parte (1.3, 1.4, 1.5, 2.3, 3.4, 4.3): ¿mi
   argumento se sostiene?
b) Las propuestas nuevas: copia del repositorio para A, CLAUDE.md reducido,
   regla de R-1 a R-3 sin umbral, mínimos 5/8 y 2/3, aleatorización por hash.
   ¿Introducen algún problema nuevo?
c) Algo grave que se te haya pasado en la ronda 1.
Mismo formato de tabla. No repitas lo que ya acepté.
```

## Respuesta del sistema — ronda 2

```
# Revisión metodológica — Ronda 2

La respuesta de Claude corrige varias asimetrías importantes. Sin embargo, mantengo objeciones a 1.4, 2.3 y 4.3, y detecto nuevos riesgos en la aleatorización, la regla de pronóstico y el tratamiento de hechos compartidos.

Mi criterio es distinguir entre una decisión metodológica defendible, una decisión aceptable con limitaciones y una que todavía requiere corrección antes del congelamiento.

## a) Evaluación de las seis aceptaciones parciales

| Sección del documento                     | Problema / evaluación del argumento                                                                                                                                                                                                                                                                                                                                                                                                          | Gravedad | Propuesta                                                                                                                                                                                                                                                                                                                |
| ----------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | -------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| 1.3 — Plan de fuentes                     | Argumento válido. Las fuentes aportadas por el operador forman parte del tratamiento B. Exigir idéntico conjunto de fuentes eliminaría parte de lo que se pretende estudiar. Sin embargo, los mismos bloques no garantizan búsquedas comparables.                                                                                                                                                                                            | Media    | Aceptar, distinguiendo entre acceso común a bloques de fuentes y fuentes adicionales aportadas por el operador. Registrar la procedencia de estas últimas. No clasificarlas automáticamente como violación.                                                                                                              |
| 1.4 — Esfuerzo                            | Aceptación parcial insuficiente. Igualar el criterio de parada es positivo, pero “cuando las búsquedas ya no devuelven hechos nuevos relevantes” depende de la estrategia, del número de búsquedas realizadas y de la información recibida. B puede encontrar nuevos términos de búsqueda gracias al operador y prolongar su investigación.                                                                                                  | Alta     | Mantener el criterio de parada, pero declarar que el esfuerzo no está controlado experimentalmente. Registrar búsquedas, duración y fuentes. No atribuir automáticamente toda diferencia de cobertura a una mejor capacidad de identificación de hechos.                                                                 |
| 1.5 — Mensaje y CLAUDE.md                 | Argumento válido con reserva. Que B conozca su identidad es inherente al diseño. Eliminar la información experimental de A reduce un sesgo. Pero un CLAUDE.md reducido introduce otra diferencia entre brazos si también elimina reglas de trabajo relevantes.                                                                                                                                                                               | Media    | Aceptar condicionado: el CLAUDE.md reducido debe eliminar exclusivamente información sobre la investigación A/B, sin cambiar instrucciones sustantivas del seguimiento. Registrar un diff de ambas versiones.                                                                                                            |
| 2.3 — Relevancia                          | Argumento parcialmente válido, pero la nueva definición es demasiado estrecha. Un hecho puede ser relevante para estimar una probabilidad sin tocar literalmente su regla de resolución. Por ejemplo, una negociación diplomática puede modificar la probabilidad de un acuerdo nuclear sin satisfacer ninguna de sus tres condiciones formales. La propuesta podría excluir precisamente información anticipatoria.                         | Alta     | Distinguir entre relevancia directa para la resolución y relevancia predictiva. Esta última requiere que el brazo explique la conexión con Q1–Q8 o los escenarios, y que el evaluador determine si es explícita y sustentada, sin juzgar retrospectivamente si fue acertada.                                             |
| 3.4 — Regla estricta de errores           | Argumento válido. Mantener cualquier aumento observado es coherente con H-AB2. Crear otro umbral arbitrario sería innecesario. El problema no es el umbral, sino interpretar una diferencia observada como efecto causal.                                                                                                                                                                                                                    | Baja     | Aceptar. Mantener R-5 y la expresión “aumento observado”, acompañada de numerador, denominador y diferencia de tasas.                                                                                                                                                                                                    |
| 4.3 — Pipeline posterior al congelamiento | Argumento no completamente válido. Tener una fórmula escrita reduce considerablemente la libertad analítica, pero no elimina decisiones de implementación: intervalos, redondeos, exclusiones, manejo de NA, empates y datos mal formados. Además, esperar hasta el 31 de diciembre no garantiza que no se hayan observado resultados de preguntas ya resueltas. El prerregistro incluye eventos que se resuelven durante noviembre y antes. | Alta     | Congelar antes del 5 de noviembre una especificación ejecutable suficientemente completa, aunque el código se programe después. Incluir casos de prueba con resultados esperados, reglas para casos límite y la definición precisa de los cálculos. El código posterior debe limitarse a implementar esa especificación. |

Resultado de a): aceptaría 1.3 y 3.4; aceptaría 1.5 con una comprobación documental; y mantendría observaciones sustantivas sobre 1.4, 2.3 y 4.3.

## b) Evaluación de las propuestas nuevas

| Sección del documento                                            | Problema / evaluación de la propuesta                                                                                                                                                                                                                                                                                                                                                                                                              | Gravedad | Propuesta                                                                                                                                                                                                                                                                                                        |
| ---------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | -------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| §3–4 — Copia del repositorio para A                              | Mejora importante, pero aislamiento incompleto. Separar carpetas puede aislar memoria asociada al proyecto, pero no garantiza independencia de configuraciones globales, instrucciones de usuario, mecanismos de memoria externos o archivos compartidos. El hash SHA-256 de la memoria principal solo detecta cambios en los archivos incluidos en ese cálculo.                                                                                   | Media    | Registrar exactamente qué archivos y directorios quedan bajo el hash, y comprobar que A y B usan la misma versión inicial de los insumos sustantivos. No afirmar aislamiento completo si existen mecanismos compartidos no inspeccionables.                                                                      |
| Anexo A — CLAUDE.md reducido                                     | Puede afectar comportamiento, profundidad analítica o reglas de trabajo, aunque la intención sea retirar solo información experimental. Además, al ocultar la identidad de A pero no la de B, el conocimiento experimental seguirá siendo asimétrico.                                                                                                                                                                                              | Media    | Congelar las dos versiones de CLAUDE.md, mostrar el diff y verificar que únicamente se retira información sobre la comparación. Presentar el procedimiento como reducción de expectativas experimentales, no como cegamiento del generador.                                                                      |
| §7 — Nueva regla R-1 a R-3                                       | La regla es simétrica y elimina la falsa apariencia de significación estadística. Sin embargo, combina dos criterios —mejor Brier agregado y mayor número de preguntas ganadas— que pueden discrepar legítimamente. Un brazo puede tener menor Brier total porque evita un error grave, aunque pierda por márgenes pequeños en más preguntas. Clasificarlo como “sin diferencia clara” es una decisión convencional, no una propiedad estadística. | Media    | Puede mantenerse como criterio de concordancia descriptiva, siempre que se reporten por separado ΔBrier, victorias, derrotas y empates. No afirmar que R-3 significa igualdad ni ausencia de ventaja observada.                                                                                                  |
| §7 — Mínimo 5/8 preguntas evaluables                             | Es un umbral convencional defendible, pero no resuelve el problema de dependencia. Las cinco preguntas disponibles podrían estar muy correlacionadas. Además, las preguntas indeterminadas podrían no distribuirse aleatoriamente: podría ser justamente la ambigüedad de eventos difíciles la que impide calificarlos.                                                                                                                            | Media    | Aceptar como regla operativa, no como garantía de potencia o confiabilidad. Registrar cuáles preguntas se excluyen y por qué. Añadir un análisis descriptivo por pregunta y advertir sobre dependencia entre las evaluables.                                                                                     |
| §6–7 — Mínimo 2/3 predicciones de patrón                         | Es factible, pero cambia el significado de la métrica: un brazo podría tener dos predicciones fáciles evaluables y una difícil indeterminada. Además, al calcular con dos en lugar de tres, aumenta la sensibilidad a cada resultado.                                                                                                                                                                                                              | Media    | Aceptar con reservas: reportar siempre las tres predicciones originales y su estado. Indicar el denominador efectivo del Brier. No comparar valores obtenidos con distinto número de predicciones como si tuvieran igual solidez.                                                                                |
| §8 — Aleatorización mediante último dígito del hash del commit B | Problema nuevo importante. El hash es aparentemente impredecible antes de crear el commit, pero no impide manipulación: el operador puede cambiar contenido o metadatos, generar otro commit y obtener una paridad diferente. Además, la clave queda públicamente deducible si el commit es accesible y se conoce la regla.                                                                                                                        | Alta     | No usar el hash de B como fuente de aleatoriedad. Generar una asignación aleatoria una sola vez, mediante una fuente independiente, después de cerrar ambos brazos y antes de preparar el paquete de Gemini. Archivar la asignación y su procedimiento; no incluir la clave en los materiales que recibe Gemini. |

### Dos advertencias adicionales

La primera concierne a R-1–R-3. Consideremos este resultado hipotético:

Ejemplo de discrepancia entre los dos criterios

| Resultado            | Brazo A | Brazo B |
| -------------------- | ------- | ------- |
| Brier medio          | 0,15    | 0,10    |
| Preguntas ganadas    | 5       | 3       |
| Ganancia según Brier |         | B       |

Bajo la nueva regla, se publicaría R-3, aunque B tiene un Brier medio mejor. No es un cálculo incorrecto: es una definición conservadora de concordancia, que debe explicitarse.

La segunda es que la aleatorización de etiquetas X/Y no produce asignación aleatoria del tratamiento. Solo oculta la identidad de las salidas durante la evaluación. Los brazos siguen ejecutándose en orden fijo A→B. Es importante no describir este estudio como ensayo aleatorizado.

## c) Problemas graves que no identifiqué suficientemente en la ronda 1

| Sección del documento                            | Problema                                                                                                                                                                                                                                                                                                                                                                                                                        | Gravedad | Propuesta                                                                                                                                                                                                                                                                                                                   |
| ------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | -------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| §3 + §5 — Orden fijo y sucesos ya conocidos      | Sesgo por información acumulada antes de C. Las probabilidades Q1–Q8 se elaboran después del 5 de noviembre, pero varias preguntas reutilizan estructuras y pronósticos anteriores. A puede haber recibido resultados parciales del conflicto por sus insumos, mientras B dispone adicionalmente del procesamiento previo del operador. La diferencia podría reflejar estado informacional histórico, no solamente diálogo S16. | Alta     | Aclarar que el contraste estima la diferencia entre dos procesos con insumos históricos distintos, no el efecto aislado del diálogo. Conservar trazabilidad de qué información ya estaba disponible antes de cada pronóstico.                                                                                               |
| §6 M-AB1 — Exclusividad de hechos                | Una diferencia de cobertura no equivale a descubrimiento original. Si A identifica un hecho, B lo obtiene directamente de la lista del operador, o viceversa, el conteo exclusivo captura presencia en la salida, no quién lo descubrió primero ni mediante qué mecanismo. Además, la nueva regla de “solapamiento parcial = compartido” podría ocultar información adicional realmente aportada por un brazo.                  | Alta     | Mantener la comparación por eventos y, separadamente, registrar la procedencia del hallazgo y las diferencias de detalle. El conteo de exclusivos debe interpretarse como cobertura diferencial de las salidas, no como número de descubrimientos causados por el diálogo.                                                  |
| §6 M-AB2 — Sesgo de selección del denominador    | Solo se auditan como errores los hechos que el propio brazo presenta con ✅. Un brazo puede ser conservador, marcar más hechos 🟡 y obtener una tasa aparentemente mejor; otro puede verificar más hechos y asumir más riesgo. La métrica puede premiar la abstención.                                                                                                                                                           | Alta     | Reportar junto a la tasa de errores el número total de hechos presentados, el número ✅ y la proporción de hechos con ✅. No interpretar M-AB2 aisladamente de la cobertura y de las abstenciones.                                                                                                                            |
| §6 M-AB3 — Solapamiento Q7/Q8                    | Q7 y Q8 son eventos parcialmente anidados: un ataque de EEUU sobre territorio iraní en la ventana común puede resolver ambas afirmativamente. Aunque se reconoció correlación, no destaqué suficientemente que el mismo acontecimiento puede recibir doble peso en el promedio Brier.                                                                                                                                           | Media    | Mantener las ocho preguntas si están congeladas, pero calcular adicionalmente ΔBrier excluyendo Q7 y después excluyendo Q8, como sensibilidad descriptiva.                                                                                                                                                                  |
| §8 — Fuentes de evaluación preparadas por Claude | El prerregistro permite que Claude prepare fuentes de resolución sin conclusiones. Para el A/B, Claude también produjo los brazos. Si posteriormente selecciona las fuentes que Gemini recibe, puede favorecer inadvertidamente la verificabilidad de ciertos hechos o resoluciones. El cegamiento de etiquetas no resuelve la selección de evidencia.                                                                          | Alta     | Usar las fuentes citadas en los anexos congelados para auditar hechos y un expediente común de resolución para Q1–Q8, preparado sin conocimiento de qué brazo resulta favorecido por cada resolución. Registrar fuentes omitidas, contradicciones y búsquedas realizadas; Gemini debe poder indicar evidencia insuficiente. |
| §8 — Lectura menos favorable a B                 | Una regla conservadora contra B no elimina los sesgos; puede introducir otra asimetría si se utiliza para construir una conclusión global. Además, un desacuerdo sobre si dos hechos son equivalentes podría perjudicar específicamente a B sin que exista una regla espejo.                                                                                                                                                    | Media    | Publicar las dos evaluaciones completas y aplicar la regla conservadora únicamente al titular previamente definido. Mostrar también qué conclusión resulta de cada evaluador por separado.                                                                                                                                  |

## Dictamen de la ronda 2

Estado metodológico

Correcciones necesarias

El diseño es viable como estudio de caso exploratorio, pero no lo congelaría todavía sin resolver estos cuatro asuntos:

1. La definición de relevancia predictiva, que no debe quedar limitada a hechos que satisfacen directamente las condiciones de resolución.
2. La especificación completa y congelada de los cálculos y casos límite, aunque el código se implemente posteriormente.
3. La sustitución de la aleatorización basada en el hash manipulable de B.
4. La interpretación conjunta de cobertura, errores y abstenciones, para evitar favorecer al brazo que presenta menos afirmaciones verificadas.

Conclusión para el operador: la segunda versión propuesta es metodológicamente más defendible que la primera. No detecto una intención evidente de favorecer a B en las nuevas reglas; de hecho, se ha corregido una asimetría importante. Pero las cuatro cuestiones anteriores todavía permiten resultados ambiguos o dependientes de decisiones del evaluador. Las resolvería antes del congelamiento del 5 de noviembre de 2026, sin reabrir el prerregistro original.
```

## Desacuerdos que decide el operador

La revisión terminó en la ronda 2, el máximo previsto. Claude aceptó todas las objeciones de la ronda 2 salvo dos, que no se podían aplicar tal cual. El operador las decidió el 1 nov 2026 eligiendo entre opciones que Claude le presentó; en las dos eligió la recomendada:

| # | Propuesta de ChatGPT (ronda 2) | Por qué no se aplica tal cual | Decisión del operador |
|---|---|---|---|
| D-1 | Asignar X/Y "una sola vez, mediante una fuente independiente", sin usar el hash de B | Era una elección de procedimiento, no un desacuerdo: el hash quedó descartado | **Una moneda**, lanzada una sola vez por el operador después de cerrar los dos brazos. El resultado se anota en un archivo que Gemini no recibe. Se declara que el operador podría repetir el lanzamiento sin que nadie lo note; lo que está en juego es poco, porque las etiquetas solo ocultan los nombres de los brazos |
| D-2 | Que el expediente de resolución de Q1–Q8 lo prepare alguien "sin conocimiento de qué brazo resulta favorecido" | Imposible: Claude y el operador conocen los pronósticos de los dos brazos | **Búsquedas fijas:** la lista de búsquedas por pregunta (términos, bloques, fechas) se congela con el diseño. En enero se corren tal cual y se archivan todos los resultados, también los contradictorios. Gemini puede buscar por su cuenta y declarar evidencia insuficiente |

El operador también aprobó que Claude reescribiera el diseño con todo lo aceptado, para congelarlo antes del 5 nov. Estas decisiones se copian en la sección 10 del diseño.
