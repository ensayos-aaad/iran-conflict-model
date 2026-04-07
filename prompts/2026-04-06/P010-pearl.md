# P010 — Marco teórico: Judea Pearl

**Fecha:** 2026-04-06
**Sesión:** 01
**Tipo:** Referencia
**Peldaño Pearl:** N/A — define el marco mismo
**Impacto en modelo:** Alto

---

## Prompt

> "Hay un libro de un autor que se llama el libro del porque? cual es la intencion de este libro? quien es el autor?"

---

## Respuesta del sistema

**Autor:** Judea Pearl, coescrito con Dana Mackenzie (2018). Premio Turing 2011.

**Tesis central:** La estadística tradicional y el machine learning confunden correlación con causalidad. Para entender el mundo hay que preguntar *¿por qué?*, no solo *¿qué?*

**Escalera de Causalidad — tres peldaños:**

| Peldaño | Nombre | Pregunta | Nivel |
|---------|--------|----------|-------|
| 1 | Ver / Association | ¿Qué está correlacionado con qué? | Machine learning convencional |
| 2 | Intervenir / Intervention | ¿Qué pasaría si hago X? | Experimentos, políticas |
| 3 | Imaginar / Counterfactual | ¿Qué hubiera pasado si...? | Razonamiento humano profundo |

**Conexión con el modelo:** El motor de inferencia debe operar en los tres peldaños simultáneamente para que los escenarios prospectivos sean causalmente válidos.

---

## Inferencia generada

Pearl resuelve el problema fundamental del sistema: sin distinción entre correlación y causalidad, el índice de desinformación mediría coincidencias, no manipulaciones. Con su marco, el sistema puede distinguir entre *estas dos narrativas coinciden* (correlación) y *este actor está causando que la otra narrativa exista* (causalidad). Esa diferencia es la que convierte el análisis en inteligencia.

---

## Impacto en el modelo

Estableció la **base filosófica y metodológica del motor de inferencia**. Los tres peldaños de Pearl se convirtieron en los tres modos operativos del sistema. Referencia añadida al README.md.
