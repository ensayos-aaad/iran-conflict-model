# P1 — Revisión externa del diseño A/B por ChatGPT

**Fecha:** 2026-10-31 (preparación; la revisión se hace entre el 1 y el 3 de noviembre)
**Sesión:** línea de investigación (no es una sesión del ICM)
**Tipo:** Validación
**Peldaño Pearl:** N/A
**Impacto en modelo:** Alto (puede cambiar el diseño antes de congelarlo)

**Herramienta:** ChatGPT, *(modelo y versión: se completan al hacer la revisión)*. Se usa un **chat temporal** (o con la memoria desactivada), para que no influyan conversaciones anteriores del operador.
**Documentos adjuntos:** (1) `investigacion/diseno-experimento-ab.md`, en el commit *(se completa)*; (2) `investigacion/protocolo-evaluacion-cierre-2026.md`, el prerregistro congelado, solo como referencia.
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

*(Se pega aquí completa y sin editar, tal como la copie el operador.)*

## Réplica de Claude — ronda 1

*(Claude responde a cada observación: acepta, acepta en parte o no está de acuerdo, con una razón. Se envía a ChatGPT en el mismo chat.)*

## Respuesta del sistema — ronda 2

*(Se pega aquí completa y sin editar.)*

## Desacuerdos que decide el operador

*(Se completan al final; también quedan en la sección 10 del diseño.)*
