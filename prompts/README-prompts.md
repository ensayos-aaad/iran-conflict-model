# Documentación de prompts — Iran Conflict Model (ICM)

## ¿Por qué se documentan los prompts?

Los prompts son la evidencia experimental del sistema. Documentarlos permite:

1. **Reproducibilidad** — cualquier investigador puede replicar el experimento
2. **Trazabilidad** — cada decisión de diseño tiene un origen rastreable
3. **Aprendizaje** — el sistema mejora al analizar qué preguntas produjeron qué inferencias
4. **Validación** — la calidad del output puede evaluarse contra la calidad del input

La interacción humano-IA es en sí misma un dato experimental. El prompt no es solo una instrucción — es una hipótesis. La respuesta del sistema es el resultado del experimento.

---

## Estructura de nomenclatura

```
P[número]-[descripción-corta].md
```

- Números secuenciales por sesión, reiniciados en cada fecha
- Descripción en minúsculas con guiones
- Archivos agrupados por fecha en subcarpetas

---

## Formato estándar de cada archivo

```markdown
# P[N] — [Título]

**Fecha:** YYYY-MM-DD
**Sesión:** [número]
**Tipo:** [Consulta factual / Diseño / Validación / Dialéctica]
**Peldaño Pearl:** [Ver / Intervenir / Imaginar / N/A]
**Impacto en modelo:** [Alto / Medio / Bajo]

## Prompt
[Texto exacto del usuario]

## Respuesta del sistema
[Resumen o respuesta completa del sistema]

## Inferencia generada
[Qué aprendió o procesó el sistema con esta interacción]

## Impacto en el modelo
[Si modificó la arquitectura, las fuentes, las salidas u otro componente]
```

---

## Tipos de prompt

| Tipo | Descripción |
|------|-------------|
| Consulta factual | El usuario pide información verificable |
| Diseño | El usuario toma una decisión arquitectónica |
| Validación | El usuario confirma o rechaza una propuesta del sistema |
| Dialéctica | El usuario introduce una hipótesis o tensión conceptual |
| Referencia | El usuario introduce una fuente o marco teórico externo |

---

## Relación con CHANGELOG.md

Cada versión en el CHANGELOG referencia los prompts que la originaron. Los prompts son la evidencia que justifica cada entrada del changelog.

---

## Índice de sesiones

| Sesión | Fecha | Prompts | Descripción |
|--------|-------|---------|-------------|
| 01 | 2026-04-06 | P001–P013 | Diseño completo de la arquitectura del modelo |

---

*Este documento se actualiza con cada nueva sesión.*
