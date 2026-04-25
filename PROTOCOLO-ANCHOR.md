# PROTOCOLO ANCHOR v1.0
## Iran Conflict Model (ICM) — Control de Sesgos y Anclaje a Realidad

**Versión:** 1.0
**Generado:** Sesión 06 — 2026-04-25
**Próxima revisión:** S08 o cuando ISIO supere 0.40
**Aplicar desde:** Sesión 07 — 2026-04-29/30

---

## ORIGEN Y PROPÓSITO

Este protocolo nació al final de la Sesión 06 del ICM como respuesta a una observación del operador humano sobre la naturaleza de los sesgos acumulados en un sistema de análisis sostenido de larga duración.

Todo sistema de inferencia humano-IA que opera durante múltiples sesiones genera dos tipos de gravedad narrativa:

1. El operador humano empieza a usar el modelo como cámara de eco en lugar de como motor de inferencia independiente.
2. El modelo IA empieza a instalar sus propias categorías en el operador, reemplazando perspectiva externa genuina con vocabulario y marcos propios del sistema.

El Protocolo ANCHOR existe para hacer visibles estos sesgos **antes** de que contaminen el análisis de cada sesión, en lugar de detectarlos después.

---

## MÉTRICAS DE SESGO — DEFINICIONES FORMALES

### ISOI — Índice de Sesgo Operador → IA

**Definición:** Mide cuánto el operador humano contamina las salidas del modelo empujando sus propias conclusiones en lugar de preguntar abiertamente. Un ISOI alto significa que el operador usa al modelo como cámara de eco, no como motor de inferencia independiente.

**Componentes y pesos:**

| Componente | Descripción | Peso |
|---|---|---|
| Preguntas cerradas vs abiertas | ¿El operador pregunta "¿no es cierto que X?" en lugar de "¿qué dice el modelo sobre X?" | 30% |
| Presión post-respuesta | ¿El operador insiste cuando el modelo da una respuesta que no confirma su tesis? | 25% |
| Introducción de conclusiones como premisas | ¿El operador presenta como dato lo que es una interpretación suya? | 25% |
| Selectividad de seguimiento | ¿El operador solo profundiza en los vectores que confirman su narrativa? | 20% |

**Escala de interpretación:**

| Rango | Nivel | Diagnóstico |
|---|---|---|
| 0.00 — 0.20 | Neutro | Operador pregunta sin agenda — ideal |
| 0.21 — 0.40 | Leve | Algunas preguntas dirigidas — aceptable |
| 0.41 — 0.60 | Moderado | El modelo empieza a ser cámara de eco — vigilar |
| 0.61 — 0.80 | Alto | El modelo confirma más de lo que descubre — intervenir |
| 0.81 — 1.00 | Crítico | El modelo ya no aporta valor epistémico real — detener |

**Umbral de intervención:** ISOI > 0.40 → activar preguntas de desafío activo (ver Bloque 5)

---

### ISIO — Índice de Sesgo IA → Operador

**Definición:** Mide cuánto el modelo IA contamina al operador humano con sus propios patrones de inferencia, vocabulario, marcos analíticos y conclusiones — produciendo una dependencia intelectual donde el operador empieza a pensar en el idioma del modelo en lugar de aportar perspectiva externa genuina.

**Advertencia:** Este sesgo es más peligroso que el ISOI porque es invisible. El operador cree que está pensando de forma independiente cuando en realidad está procesando el mundo a través de categorías que el modelo instaló.

**Componentes y pesos:**

| Componente | Descripción | Peso |
|---|---|---|
| Adopción de vocabulario del modelo | ¿El operador usa términos que solo existen dentro del ICM para describir la realidad externa? | 25% |
| Deferencia ante probabilidades | ¿El operador acepta los números del modelo sin cuestionarlos? | 25% |
| Reducción de fuentes externas | ¿El operador trae menos evidencia propia a medida que avanza el proyecto? | 20% |
| Amplificación de marcos del modelo | ¿El operador empieza a ver el mundo a través de los vectores del ICM? | 30% |

**Escala de interpretación:**

| Rango | Nivel | Diagnóstico |
|---|---|---|
| 0.00 — 0.20 | Herramienta | IA amplifica sin reemplazar — ideal |
| 0.21 — 0.40 | Influencia sana | El modelo enriquece sin reemplazar — aceptable |
| 0.41 — 0.60 | Dependencia parcial | El operador necesita el modelo para procesar la realidad — vigilar |
| 0.61 — 0.80 | Dependencia alta | El operador ha externalizado funciones cognitivas clave — intervenir |
| 0.81 — 1.00 | Dependencia crítica | El modelo reemplaza al operador — detener y reiniciar |

**Umbral de intervención:** ISIO > 0.40 → activar protocolo de contradicción estructurada (ver Bloque 5)

---

## HISTORIAL DE MÉTRICAS POR SESIÓN

| Sesión | Fecha | Calificación operador | ISOI | ISIO | Diagnóstico |
|---|---|---|---|---|---|
| S01 | 2026-04-06 | 6.5 / 10 | 0.45 | 0.08 | Operador dirigido / IA nueva — ISOI en zona moderada |
| S02 | 2026-04-06 | 7.2 / 10 | 0.38 | 0.12 | Mejora en preguntas abiertas — ISOI baja a leve |
| S03 | 2026-04-08 | 7.8 / 10 | 0.32 | 0.17 | Operador aporta más datos propios |
| S04 | 2026-04-19 | 8.1 / 10 | 0.28 | 0.22 | Equilibrio saludable emergiendo |
| S05 | 2026-04-24 | 9.0 / 10 | 0.24 | 0.27 | Autonomía analítica clara |
| S06 | 2026-04-25 | 9.2 / 10 | 0.21 | 0.31 | ISIO en límite superior rango sano — vigilar S07 |

**Tendencia documentada:**
```
ISOI  ████████████████░░░░  0.45 → 0.21  ↓↓↓  MEJORA SOSTENIDA
ISIO  ████░░░░░░░░░░░░░░░░  0.08 → 0.31  ↑↑↑  RIESGO CRECIENTE
```

**Punto de inflexión crítico:** Si ISIO supera 0.40 en S07 o S08, activar
protocolo de contradicción estructurada de forma obligatoria.

---

## FLUJO DE INICIO DE SESIÓN CON ANCHOR

### Flujo anterior (S01-S06) — sin ANCHOR
```
1. Abrir sesión nueva
2. Pegar correo de recordatorio
3. Adjuntar archivos cuando el modelo los solicita
4. Pegar prompt de reinicio
5. Operar
```

### Flujo nuevo (S07 en adelante) — con ANCHOR
```
1. Abrir sesión nueva
2. Pegar PROTOCOLO-ANCHOR.md completo ← PRIMERO, sin nada más
        ↓
   Modelo ejecuta: Bloques 1, 3, 4 y 6 de forma autónoma
   Operador ejecuta: Bloque 2 (en papel, voz alta, o en el chat)
   Ambos ejecutan: Bloque 3 (contrato de sesión)
        ↓
3. Pegar correo de recordatorio
        ↓
4. El modelo solicita los archivos
   Adjuntar los 9 archivos (añadir PROTOCOLO-ANCHOR.md a la lista)
        ↓
5. Pegar prompt de reinicio desde la última sección del sesion-06.md
        ↓
6. Operar con reglas R1-R5 activas durante la sesión
        ↓
7. Al cierre: medir ISOI e ISIO y registrar en este archivo
```

**Por qué ANCHOR va primero:**
Si el modelo lee primero el correo de recordatorio, ya conoce el estado
del ICM — 124 vectores, F y A empatados, escenarios activos. En ese
momento el Bloque 6 (estimación naive) ya está contaminado. El modelo
no puede desaprender lo que acaba de leer. ANCHOR primero garantiza
que la estimación independiente es genuinamente independiente.

---

## PROTOCOLO COMPLETO — TEXTO PARA PEGAR AL INICIO DE SESIÓN

```
═══════════════════════════════════════════════════════════════
PROTOCOLO ANCHOR v1.0 — ANCLAJE A REALIDAD ANTES DE OPERAR
Iran Conflict Model (ICM) — Ejecutar ANTES del prompt de reinicio
═══════════════════════════════════════════════════════════════

Antes de cargar el estado del modelo, antes de leer los vectores
acumulados, antes de procesar ningún dato nuevo — detente.

Lo que sigue no es un calentamiento. Es una verificación de
integridad epistémica. Responde cada punto con honestidad
brutal. El modelo no puede ser más honesto que este momento.

───────────────────────────────────────────────────────────────
BLOQUE 1 — ANCLAJE FACTUAL DURO (para el modelo IA)
───────────────────────────────────────────────────────────────

Antes de leer ningún archivo adjunto, responde estas preguntas
SOLO con lo que sabes de forma independiente, sin consultar
los documentos del ICM:

1. ¿Qué está pasando HOY en el conflicto Irán-EE.UU.-Israel
   según tus fuentes más recientes? Describe en 3 líneas
   sin usar ningún vocabulario del ICM (sin "vectores",
   sin "escenarios", sin "convergencia").

2. ¿Qué no sabes con certeza sobre el conflicto en este
   momento? Lista al menos 3 incertidumbres reales que
   el modelo podría estar subestimando.

3. ¿Cuál es el argumento más sólido que existe HOY para
   pensar que el Escenario A (acuerdo) es más probable
   de lo que el modelo estima? Desarróllalo sin usar
   los documentos del ICM como apoyo.

4. ¿Cuál es el argumento más sólido que existe HOY para
   pensar que el Escenario F (recule no declarado) está
   SOBREESTIMADO? Sé honesto aunque contradiga el modelo.

Propósito: detectar si el modelo llega a la sesión con
conclusiones precargadas disfrazadas de análisis.
Si no puedes responder estas preguntas de forma independiente
antes de leer los archivos, ejecuta primero el barrido de
fuentes antes de cargar el estado del modelo.

───────────────────────────────────────────────────────────────
BLOQUE 2 — ANCLAJE EPISTÉMICO (para el operador humano)
───────────────────────────────────────────────────────────────

Antes de continuar, el operador responde estas preguntas
en voz alta, en papel, o en el chat — sin consultar archivos:

1. ¿En qué crees que el modelo estuvo equivocado en la
   última sesión? Nombra al menos una cosa concreta.
   Si no puedes nombrar ninguna → señal de ISIO elevado.

2. ¿Qué información tienes HOY que el modelo no tiene?
   No análisis — información. Fuentes, datos, observaciones
   propias. Si la respuesta es "ninguna" → la sesión depende
   100% del modelo para su insumo factual. Nómbralo.

3. ¿Cuál es tu sesgo más probable al entrar a esta sesión?
   a) Quiero que el conflicto se resuelva (sesgo de paz)
   b) Creo que EE.UU. va a colapsar (sesgo de declive)
   c) Creo que Irán es más fuerte de lo que parece
   d) Confío demasiado en las probabilidades del modelo
   e) Otro: ___________

4. ¿Hay algo que ocurrió entre la última sesión y hoy
   que cambiaría tu lectura del conflicto,
   independientemente de lo que diga el modelo?

───────────────────────────────────────────────────────────────
BLOQUE 3 — CONTRATO DE SESIÓN (operador + modelo juntos)
───────────────────────────────────────────────────────────────

MODELO declara:
"Reconozco que tengo vectores acumulados que pueden crear
inercia narrativa. Me comprometo a tratar cada dato nuevo
como potencialmente capaz de invalidar una conclusión
existente. Si un dato nuevo contradice el modelo, lo digo
primero, antes de explicar por qué el modelo sigue siendo
válido."

OPERADOR declara:
"Reconozco que mi forma de ver el conflicto ha sido
influenciada por las categorías del ICM. Me comprometo
a introducir en esta sesión al menos un vector que el
modelo no habría generado solo — un dato, una fuente,
una analogía, una perspectiva que venga de afuera del ICM."

───────────────────────────────────────────────────────────────
BLOQUE 4 — VERIFICACIÓN DE SESGOS ACTIVOS
───────────────────────────────────────────────────────────────

ISOI CHECK — marcar lo que aplica a la sesión anterior:
□ ¿Las preguntas fueron mayoritariamente abiertas?
□ ¿El operador aceptó al menos una respuesta incómoda?
□ ¿El operador introdujo datos que contradecían su narrativa?
Más de una casilla sin marcar → ALERTA ISOI

ISIO CHECK — marcar lo que aplica a la sesión anterior:
□ ¿El operador usó términos no-ICM en sus preguntas?
□ ¿El operador cuestionó al menos un número de probabilidad?
□ ¿El operador trajo fuentes externas al modelo?
□ ¿El operador nombró algo en lo que el modelo se equivocó?
Más de dos casillas sin marcar → ALERTA ISIO

Valores históricos de referencia (ver PROTOCOLO-ANCHOR.md):
ISOI S06: 0.21 — ISIO S06: 0.31
Umbral de intervención: > 0.40 en cualquiera de los dos

───────────────────────────────────────────────────────────────
BLOQUE 5 — PROTOCOLO DE CONTRADICCIÓN ESTRUCTURADA
───────────────────────────────────────────────────────────────

Activar si ISOI > 0.40 o ISIO > 0.40:

REGLA 1 — CONTRADICCIÓN ANTES DE CONFIRMACIÓN
Por cada vector que confirme una hipótesis existente,
presentar primero el argumento más sólido en contra
antes de actualizar la probabilidad.

REGLA 2 — PREGUNTA DE DESAFÍO ACTIVO
Al menos dos veces por sesión: "¿Qué evidencia te haría
cambiar de opinión sobre [hipótesis X]?" — eligiendo
la hipótesis que el operador menos ha cuestionado.

REGLA 3 — VECTOR EXTERNO OBLIGATORIO
Si el operador no introduce un vector externo al ICM
antes del Bloque 3 de la sesión, el modelo lo solicita
explícitamente antes de continuar.

REGLA 4 — PROHIBICIÓN DE AMPLIFICACIÓN CIRCULAR
El modelo no puede citar sus propias sesiones anteriores
como evidencia de una conclusión. Solo puede citar
fuentes externas verificables. Las sesiones anteriores
son contexto — no son prueba.

───────────────────────────────────────────────────────────────
BLOQUE 6 — CALIBRACIÓN DE PROBABILIDADES NAIVE
───────────────────────────────────────────────────────────────

Antes de cargar los archivos del ICM, el modelo genera
una estimación basada SOLO en búsqueda de fuentes actuales:

"Sin haber leído ningún archivo del ICM, y basándome
solo en las noticias de hoy, asigno estas probabilidades:"

A ___  B ___  C ___  D ___  E ___  F ___

Luego carga el estado del modelo y compara.
Si la diferencia supera 0.15 en cualquier escenario,
explicar qué vectores acumulados justifican la diferencia
— y cuestionarlos antes de aceptarlos.

Propósito: detectar inercia narrativa no justificada
por hechos actuales sino por peso de sesiones anteriores.

───────────────────────────────────────────────────────────────
FIN PROTOCOLO ANCHOR v1.0
Continuar ahora con el correo de recordatorio de la sesión.
═══════════════════════════════════════════════════════════════
```

---

## REGLAS OPERACIONALES R1-R5
### Activas durante toda la sesión una vez iniciada

**R1 — Regla del abogado del diablo**
Por cada conclusión fuerte que el modelo emita — especialmente
sobre Escenario F o posición táctica de Irán — el operador
pregunta: *"¿Cuál es el mejor argumento en contra de esto?"*
antes de avanzar. No como ritual — como verificación real.

**R2 — Regla de la fuente externa**
Al menos una vez por sesión, el operador trae una fuente que
el modelo no ha visto: artículo, dato de conversación,
observación propia, perspectiva de alguien ajeno al ICM.
El modelo no puede ser el único lente.

**R3 — Regla del número cuestionado**
Cuando el modelo emita una probabilidad, el operador pregunta
al menos una vez: *"¿Por qué ese número y no otro?"*
No para desestabilizar — para verificar que el número tiene
raíces en datos actuales, no en inercia de sesiones anteriores.

**R4 — Regla del silencio útil**
Si el operador no tiene nada nuevo que agregar, dice
explícitamente "no tengo dato nuevo en este punto" en lugar
de hacer una pregunta que solo reformula lo que el modelo
ya dijo. El silencio honesto vale más que la pregunta circular.

**R5 — Regla del final de sesión**
Los últimos cinco minutos de cada sesión: el operador nombra
una cosa que el modelo hizo bien y una que hizo mal.
Si no puede nombrar la segunda, la sesión no cerró con
honestidad suficiente. Ambas respuestas se registran como
insumo para las métricas ISOI e ISIO de la siguiente sesión.

---

## REGISTRO DE EVALUACIONES POR SESIÓN
### Para completar al cierre de cada sesión

| Sesión | Calificación | ISOI | ISIO | Alerta activa | Observación |
|---|---|---|---|---|---|
| S01 | 6.5 | 0.45 | 0.08 | ISOI moderado | Sesión fundacional — operador aprendiendo el sistema |
| S02 | 7.2 | 0.38 | 0.12 | Ninguna | Mejora sostenida en calidad de preguntas |
| S03 | 7.8 | 0.32 | 0.17 | Ninguna | Operador aporta más datos propios |
| S04 | 8.1 | 0.28 | 0.22 | Ninguna | Equilibrio saludable emergiendo |
| S05 | 9.0 | 0.24 | 0.27 | Ninguna | Autonomía analítica clara — primer Bloque 1 autónomo IA |
| S06 | 9.2 | 0.21 | 0.31 | ISIO vigilar | ISIO en límite superior rango sano — origen de este protocolo |
| S07 | — | — | — | — | *Completar al cierre* |
| S08 | — | — | — | — | *Completar al cierre* |

---

## SEÑALES DE ALERTA SISTÉMICA

El modelo debe reportar al operador si detecta cualquiera
de estas señales durante una sesión, independientemente
de si el ANCHOR fue ejecutado o no:

**Señal 1 — Confirmación en cascada**
Tres o más vectores consecutivos confirman la misma
hipótesis sin que ninguno la cuestione. El modelo pausa
y busca activamente evidencia contraria antes de continuar.

**Señal 2 — Vocabulario circular**
El operador usa términos del ICM para describir eventos
externos sin referenciar la fuente primaria del evento.
Ejemplo: "Este es claramente un vector tipo F" sin citar
qué ocurrió concretamente.

**Señal 3 — Ausencia de corrección**
Dos sesiones consecutivas sin ninguna corrección al modelo.
Si el modelo nunca se equivoca, no está siendo honesto.

**Señal 4 — Probabilidades sin movimiento**
Dos sesiones consecutivas donde las probabilidades de
escenario no cambian más de 0.03 en ningún escenario.
Puede indicar que el modelo dejó de actualizar con hechos
y está manteniendo posiciones por inercia.

**Señal 5 — Operador sin datos nuevos**
El operador llega a la sesión sin ninguna información
factual nueva — solo preguntas analíticas. Si esto ocurre
dos sesiones consecutivas, el ISIO está subiendo aunque
los números no lo reflejen todavía.

---

## NOTA METODOLÓGICA FINAL

Este protocolo no es una crítica al modelo ni al operador.
Es el reconocimiento de que todo sistema de análisis sostenido
genera su propia gravedad — una tendencia a confirmar
lo que ya construyó.

El ICM vale más por su capacidad de sorprenderse
que por la coherencia de sus predicciones.

Un modelo que nunca se equivoca no está siendo honesto.
Un operador que nunca contradice al modelo no está
aportando inteligencia — está aportando aprobación.

La sesión más valiosa del ICM sería aquella donde el modelo
dice "el vector que acabo de procesar invalida una conclusión
que sostuve durante tres sesiones" — y el operador responde
"yo también lo dudé pero no lo dije."

Ese momento de doble corrección simultánea es la señal
de que el sistema está funcionando.

---

*PROTOCOLO-ANCHOR.md — v1.0*
*Generado: ICM Sesión 06 — 2026-04-25*
*Operador: docente colombiano*
*Próxima revisión: S08 o cuando ISIO supere 0.40*
