# Especificación del protocolo de seguimiento — SEG v1.0

**Fecha:** 10 de octubre de 2026 · **Estado:** versión 1.0, tal como se practicó en la S15 (9 oct 2026)
**Relación con ANCHOR:** ANCHOR v2.0 ([PROTOCOLO-ANCHOR.md](../PROTOCOLO-ANCHOR.md)) es el protocolo de sesión del modelo cerrado (S01–S13). **SEG** es una variante derivada para los seguimientos posteriores al cierre. Ver [linea-de-procesos.md](linea-de-procesos.md).

Este documento especifica el procedimiento como un artefacto: qué entra, qué sale, en qué orden, con qué reglas y cuándo se detiene. El objetivo es que otro operador pueda ejecutarlo y que su ejecución se pueda auditar.

---

## 1. Roles

| Rol | Responsabilidades | Lo que no hace |
|---|---|---|
| **Operador** | Aporta hechos de su lectura de prensa e inyecciones dialécticas (abducción); decide el alcance, las fuentes excluidas y cuándo empezar; aprueba los commits y los push | No se califica a sí mismo como único evaluador |
| **IA** | Evalúa la relevancia; verifica con varias fuentes; busca lo que falta; redacta; calcula; contradice | No escribe archivos antes de la orden del operador; no hace commit ni push sin aprobación; no califica la evaluación final |
| **Evaluador independiente** | Califica las resoluciones con las reglas prerregistradas | No ve la lectura previa de la IA |

## 2. Insumos

| Insumo | Formato |
|---|---|
| I-1. Hechos del operador | Lista libre, en una o varias tandas. Pueden venir vagos, mal fechados o con el sujeto equivocado |
| I-2. Estado anterior | El último seguimiento, el checklist del README y la tabla de falsabilidad |
| I-3. Plan de fuentes | Tabla por bloques, acordada antes de buscar |
| I-4. Prerregistro vigente | [protocolo-evaluacion-cierre-2026.md](protocolo-evaluacion-cierre-2026.md) |

## 3. Etapas

| # | Etapa | Entrada → salida | Regla de paso |
|---|---|---|---|
| E0 | **Arranque con contexto** | CLAUDE.md, último seguimiento → resumen de lo pendiente | Leer el registro antes de presentar una idea como nueva |
| E1 | **Recepción de hechos** | I-1 → evaluación de relevancia de cada hecho (con qué ítem o escenario se conecta) y preguntas de aclaración | **No se escriben archivos.** Se pasa a E2 solo cuando el operador dice que la lista está completa |
| E2 | **Plan de fuentes** | → tabla por bloques: agencias, EEUU, Europa, Golfo/árabe, Irán (estatal y oposición), Israel, China, América Latina en español, mercados, expertos | Respetar las exclusiones declaradas por el operador; sin exclusiones nuevas que no se justifiquen (R-5, propuesta) |
| E3 | **Verificación** | Cada hecho → ✅ verificado / 🟡 parcial o desactualizado / ⚪ no verificado o descartado, con su corrección | Verificado = ≥2 fuentes independientes de bloques distintos. Una sola fuente = "plausible, no verificado". Medios estatales u opositores = posición, no prueba. **Verificar las fechas explícitamente** |
| E4 | **Ampliación** | Hilos del seguimiento anterior que no se retomaron, más lo nuevo → una sección aparte | Separar la procedencia: los hechos del operador frente a lo que añadió la IA |
| E5 | **Análisis por capas** | Vectores agrupados por frente → lectura de cada capa | Abogado del diablo (K25) en cada hipótesis fuerte |
| E6 | **Actualización** | Checklist (Grupo 3) y rangos de escenarios → tablas | K21: mover un punto medio más de 0,10 exige justificación explícita. **Calcular la entropía** de la distribución y reportarla junto a la convergencia narrada |
| E7 | **Falsabilidad** | Tabla de criterios → estado de cada uno | Todo criterio nuevo se escribe con fecha y regla, antes de su resolución |
| E8 | **Contraste externo (K17)** | Voces de orientación declarada, que incluyan al menos una contraria al sesgo de la selección → tabla de cercanía | Declarar el sesgo de selección |
| E9 | **Autocrítica** | El seguimiento anterior → lo que no vio o en lo que se equivocó | Cada error encontrado se agrega a `registro-errores.csv` |
| E10 | **Entregables** | Archivo del seguimiento, dashboard, sección en el README, CLAUDE.md y CSV | Ver la sección 4 |
| E11 | **Cierre** | Commit y push | **Solo con la aprobación del operador**, por separado |

## 4. Salidas

| Salida | Ubicación |
|---|---|
| S-1. Seguimiento | `simulaciones/YYYY-MM-DD-sesion-NN-seguimiento-extraoficial.md` |
| S-2. Dashboard | `simulaciones/img/YYYY-MM-DD-sesion-NN-dashboard.png` |
| S-3. Sección en el README | `## SEGUIMIENTO POST-CIERRE — SNN (...)`, al final del archivo |
| S-4. Registro de errores | `investigacion/registro-errores.csv` (solo se agregan filas) |
| S-5. Pronósticos | `datos/validacion/registro-validacion.csv` (solo se agregan filas; un número por pregunta) |
| S-6. Contexto para la siguiente sesión | `CLAUDE.md`, sección de lo que queda abierto |

## 5. Reglas permanentes

1. No tocar el registro cerrado v0.2.0.
2. "No sé" y "no encontré" son salidas válidas; "no encontré" nunca significa "no ocurrió".
3. Los rangos se publican junto con el punto que se va a puntuar (regla del punto medio).
4. Los conflictos de interés se declaran (por ejemplo, Anthropic es firmante del acuerdo de IA evaluado en la S15).
5. Los datos personales del operador no van al repositorio público.
6. Las referencias citadas de memoria llevan †.

## 6. Criterios de parada

- **De E1:** el operador declara la lista completa.
- **De E3:** cada hecho tiene un estado; los que quedan como ⚪ se declaran, no se fuerzan.
- **De la búsqueda en E4:** cuando las búsquedas ya no devuelven hechos nuevos relevantes para el checklist o los escenarios, o cuando el operador lo indica. Las búsquedas que devuelven contenido de baja calidad se descartan y se declaran.
- **Del seguimiento:** se completaron las salidas S-1 a S-6, y el operador aprobó el cierre.

## 7. Puntos de variación (ver linea-de-procesos.md)

Dominio · horizonte · taxonomía de entradas · política de fuentes · corrección del sesgo · ancla de mercado · métrica de salud · umbral de cambio · calificación independiente. **SEG v1.0** usa: geopolítica · seguimiento · ✅/🟡/⚪ · diversidad por bloques con las exclusiones del operador · K25 · mercado declarado · entropía y convergencia · K21 · calificación independiente solo al cierre.

## 8. Versiones

| Versión | Fecha | Cambio |
|---|---|---|
| SEG v1.0 | 2026-10-10 | Especificación inicial a partir de la S15. Se agregan respecto de la S15: el cálculo de entropía (E6), el registro de errores (E9) y la salida S-5 |

Los cambios futuros se registran en esta tabla con su motivo (Kaizen). Cada seguimiento declara qué versión de SEG usó.
