# Patrones de diseño candidatos

**Fecha:** 10 de octubre de 2026 · **Estado:** borrador

## Qué significa "candidato"

En la tradición de patrones (Christopher Alexander en arquitectura †; Gamma y otros, "Gang of Four", en software †), algo es un patrón cuando **se repite en contextos distintos**. Estos patrones se extrajeron **a posteriori** del ICM, y varios surgieron por necesidad, no por diseño. **Criterio de confirmación:** un patrón pasa de "candidato" a "observado en 2 casos" si aparece documentado también en el CEM, y a "confirmado" si aparece en un tercer caso derivado de forma deliberada (por ejemplo, el ICM-Colombia, P3) o en manos de otro operador.

También hay que distinguir el **patrón diseñado** del **patrón practicado**: por ejemplo, el registro solo de agregar se aplicó en git y en el registro cerrado, pero la capa CSV nunca se usó.

## Los 12 patrones

| # | Patrón | Problema | Solución en el ICM | Análogo en software | Evidencia en el ICM | ¿En el CEM? |
|---|---|---|---|---|---|---|
| 1 | **Compuerta de verificación** | Entran hechos falsos o mal fechados | Verificar y clasificar cada hecho antes de usarlo | Validación de entradas; capa anticorrupción | S15 §1 (18 hechos ✅/🟡/⚪); taxonomía [F]/[P]/[R] | **Tardía**: se formalizó retroactivamente, y su ausencia causó una inflación de +296K votos |
| 2 | **Diversidad de fuentes** | Fuentes con el mismo sesgo fallan juntas | 9 bloques y "2 o más fuentes de bloques distintos" | Programación N-versión | S15 §0 | **Lo contrario**: ecosistema con exclusiones (Semana, El Colombiano, AtlasIntel, La Silla Vacía) |
| 3 | **Procedencia separada** | No se sabe quién aportó qué | Hechos del operador frente a la ampliación del modelo | Linaje de datos | S15 §1 frente a §10 | Parcial (reparto declarado en el COCREACION.md) |
| 4 | **Registro solo de agregar** | Reescribir el pasado borra los errores | S01–S13 inmutables; correcciones como entradas nuevas | Event sourcing | git; CLAUDE.md; reglas de `datos/` | Sí: 32 versiones con su motivo |
| 5 | **Criterio antes del resultado** | Acomodar la conclusión al resultado | Falsación con fecha; prerregistro | TDD; diseño por contrato | S15 §5 (criterio para el 3 nov) | **Sí, y funcionó**: "EL MODELO ESTUVO EQUIVOCADO", sin modificación retroactiva |
| 6 | **Umbral de cambio** | Movimientos grandes por un solo dato | K21: mover un escenario más de 0,10 exige justificación | Circuit breaker; cláusula de guarda | PROTOCOLO-ANCHOR K21; S15 §4 | **No**: el CEM lo nombra como falla ("sin mecanismo interno de detección de inflación") |
| 7 | **"No sé" como respuesta válida** | Inventar certeza | R4; rangos; huecos declarados | Tipo `Option`/`Maybe` | PROTOCOLO-ANCHOR R4; S15 notas | Sí: "¿Tienes forma de probarlo?" |
| 8 | **Abogado del diablo obligatorio** | Sesgo de confirmación | K25: "¿qué leería distinto alguien sin este sesgo?" | Red team | S15 capa 2 y §10.6 | Sí: hipótesis adversa más descuento del 30%, que fue insuficiente |
| 9 | **Corrección mutua** | Cada parte solo ve sus propios errores | El operador corrige a la IA y la IA al operador | Programación en pareja | S15: 4 hechos del operador corregidos; Colombia aportado por el operador | Asimétrica: la autoridad final era del operador, y el sesgo era del operador |
| 10 | **Núcleo cerrado, extensión abierta** | Crecer sin corromper lo cerrado | v0.2.0 congelado; seguimientos aparte | Principio abierto/cerrado | CLAUDE.md; README §SEGUIMIENTO | Sí: v31 FINAL congelada; POST-ELECTORAL aparte |
| 11 | **Mejora continua del proceso** | Los mismos errores se repiten | K1–K25: falla, cambio de regla, verificación | Retrospectivas; PDCA | README Kaizen | Sí: 15 Kaizen más el post-electoral |
| 12 | **Arranque con contexto** | Empezar sin el estado anterior | Bloques iniciales de ANCHOR; CLAUDE.md | Carga de contexto (*bootstrap*) | PROTOCOLO-ANCHOR; CLAUDE.md | Parcial: el CEM declara "sesiones abiertas sin protocolo de apertura estandarizado" |

**Estado tras el CEM:** los patrones 4, 5, 7, 8, 10 y 11 se observan en los dos casos. Los patrones 1, 2, 6 y 12 estuvieron ausentes o tardíos en el CEM, y **su ausencia coincide con fallas que el propio CEM documenta.** Es un contraste débil: los casos difieren en muchas otras cosas (dominio, duración, cercanía emocional del operador).

## El patrón general: bucle dialéctico con compuertas de verificación

```
Operador (abducción: hechos, inyecciones, criterio)
        │
        ▼
[1 Compuerta de verificación] ◄── [2 Diversidad de fuentes]
        │
        ▼
IA (deducción: estructura, fuentes, contradicción)
        │
        ▼
[8 Abogado del diablo] ──► [6 Umbral de cambio] ──► [7 "No sé"]
        │
        ▼
[9 Corrección mutua] ──► [4 Registro solo de agregar] ◄── [3 Procedencia]
        │
        ▼
[5 Criterio antes del resultado] ──► Realidad (inducción, con retraso)
        │
        ▼
[11 Mejora continua] ──► nueva regla o restricción
```

Su lógica es **generar y probar**: el operador y la IA generan, las compuertas filtran y la realidad prueba, con retraso. Como la prueba llega tarde, **los criterios tienen que escribirse antes.**

## Pendiente

- Reetiquetar los ~209 vectores del ICM por origen (operador o IA), para medir el patrón 9 con datos.
- Comprobar cada patrón en las sesiones del CEM (no solo en su README y su POST-ELECTORAL).
- Documentar los patrones con el formato completo (contexto, fuerzas, consecuencias y usos conocidos) cuando se confirmen.
