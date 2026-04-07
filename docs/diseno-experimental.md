# Diseño experimental — Iran Conflict Model (ICM)

**Versión:** v0.1.3
**Fecha:** 2026-04-06
**Estado:** Fase 1 completa — listo para sesión operativa

---

## 1. Objeto de estudio

Conflicto activo entre EEUU, Israel e Irán iniciado formalmente el 13 de junio de 2025 con la Guerra de los 12 Días y continuado desde el 28 de febrero de 2026 con la Guerra de 2026. Punto de inicio del modelo: asesinato del líder supremo Ali Jamenei el 28 de febrero de 2026.

---

## 2. Pregunta de investigación

¿Es posible construir un sistema de análisis de conflictos operado mediante dialéctica humano-IA que distinga correlación de causalidad, mida la contaminación narrativa del entorno informativo y produzca escenarios prospectivos calibrados?

---

## 3. Hipótesis

Un modelo de inferencia causal basado en la Escalera de Causalidad de Judea Pearl, alimentado por fuentes de información heterogéneas y operado mediante dialéctica humano-IA, produce escenarios prospectivos con un Brier Score inferior a 0.25 — superando la línea de base de un modelo que siempre asigna probabilidad 0.5.

---

## 4. Arquitectura del sistema

Ver README.md para descripción completa. Resumen:

```
5 entradas → motor de inferencia → 4 salidas → meta-salida
                    ↑                               │
                    └──────── 3 lazos FB ───────────┘
```

---

## 5. Protocolo de muestreo

| Parámetro | Valor |
|-----------|-------|
| Frecuencia | Diaria |
| Hora | 8:00 PM hora Colombia |
| Zona horaria | UTC-5 (01:00 UTC día siguiente) |
| Ventana de captura | Últimas 24 horas desde las 8PM |
| Duración estimada | 20-30 minutos por sesión |
| Compromiso mínimo | Diario — ver reglas de integridad |
| Sesión inaugural | Hora excepcional permitida — documentar en notas |

> **Nota sesión 02 — inaugural:** La primera sesión operativa puede ejecutarse a cualquier hora del día. Documentar la hora real en el prompt y en el campo `notas` de convergencia.csv con el texto: *"Sesión inaugural — hora excepcional. Horario estándar 8PM inicia sesión 03."* A partir de la sesión 03 aplica estrictamente el horario de 8:00 PM.

---

## 6. Tipos de sesión

| Tipo | Descripción | Cuándo usarlo |
|------|-------------|---------------|
| ESTANDAR | Sesión rutinaria diaria | Todos los días a las 8PM |
| EMERGENCIA | Sesión no planeada | Cuando ocurre evento crítico |
| OMITIDA | Sesión no ejecutada | Cuando no fue posible correrla |

---

## 7. Criterios de sesión de emergencia

Se dispara una sesión EMERGENCIA cuando ocurre cualquiera de estos eventos:

1. Ataque militar de escala mayor
2. Muerte de figura de alto valor
3. Declaración de ceasefire o escalada formal
4. Movimiento de petróleo mayor al 5% en un día
5. Cierre o amenaza de cierre del Estrecho de Ormuz
6. Ruptura o inicio de negociaciones diplomáticas

---

## 8. Reglas de integridad del experimento

```
Hasta 2 días consecutivos omitidos
→ Experimento válido

3 o más días consecutivos omitidos
→ Interrupción de serie — documentar en notas

Más del 20% de días omitidos en 90 días
→ Validez estadística comprometida
  Documentar en conclusiones
```

### Tratamiento de sesiones omitidas

Registrar en convergencia.csv con:
- sesion_tipo = OMITIDA
- todos los scores = NULL
- notas = motivo (LABORAL / PERSONAL / SIN ACCESO / ENFERMEDAD)

---

## 9. Horizontes temporales

| Horizonte | Nombre | Descripción |
|-----------|--------|-------------|
| 7 días | Táctico | ¿Qué puede pasar esta semana? |
| 30 días | Estratégico | ¿Qué puede configurarse este mes? |

---

## 10. Mecanismo de validación

### Método
Contraste retrospectivo de escenarios — comparar probabilidades predichas por S4 contra lo que realmente ocurrió.

### Métrica principal — Brier Score
```
Rango:        0.0 (perfecto) a 1.0 (inútil)
Línea base:   0.25 — modelo que siempre dice 0.5
Meta:         Brier Score < 0.25
Primer punto: 7 días después de sesión 02
```

### Valores de resultado
```
OCURRIO      → escenario completamente materializado
PARCIAL      → algunos elementos ocurrieron
NO OCURRIO   → escenario no materializado
NO EVALUABLE → evento mayor invalida la predicción
```

### Fuentes árbitro
| Categoría | Fuente |
|-----------|--------|
| Hechos militares | ACLED — acleddata.com |
| Hechos militares | Uppsala Conflict Data — ucdp.uu.se |
| Hechos generales | Reuters, AP — registro histórico |
| Mercados | Bloomberg, EIA — datos históricos con timestamps |
| Desinformación | NewsGuard, PolitiFact, FactCheck.org |

---

## 11. Base metodológica

**Pearl, J. & Mackenzie, D. (2018).** *The Book of Why: The New Science of Cause and Effect.* Basic Books.

### Escalera de Causalidad — tres peldaños operativos

| Peldaño | Nombre | Pregunta | Aplicación en el modelo |
|---------|--------|----------|------------------------|
| 1 | Ver | ¿Qué está correlacionado? | Detección de patrones entre entradas |
| 2 | Intervenir | ¿Qué cambia si ocurre X? | Análisis de impacto de eventos |
| 3 | Imaginar | ¿Qué hubiera pasado si...? | Construcción de escenarios |

---

## 12. División de responsabilidades

| Operador humano | Sistema IA |
|----------------|------------|
| Preguntas correctas | Matemática de Pearl |
| Juicio sobre relevancia | Razonamiento bayesiano |
| Dirección de la simulación | Detección de patrones |
| Hipótesis e intuiciones | Traducción a lenguaje claro |
| Captura de datos en CSV | Generación de datos crudos |
| Commits al repositorio | Análisis de fuentes |

---

## 13. Replicabilidad

### Requisitos para replicar el experimento
1. Cuenta en github.com (gratuita)
2. Cuenta en claude.ai (gratuita o de pago)
3. Git instalado en el PC
4. 20-30 minutos diarios

### Documentos necesarios para replicar
- Este documento (diseno-experimental.md)
- docs/prompt-plantilla.md
- docs/guia-captura-datos.md
- docs/guia-github.md
- README.md

### Instrucción para replicar
1. Haz fork del repositorio en github.com
2. Clona el fork en tu PC
3. Lee este documento completo
4. Sigue el prompt-plantilla.md para cada sesión
5. Sigue la guia-captura-datos.md para registrar los datos
6. Haz push diario con git

---

## 14. Estructura del repositorio

```
iran-conflict-model/
├── README.md                          ← descripción general
├── CHANGELOG.md                       ← historial de versiones
├── docs/
│   ├── diseno-experimental.md         ← este documento
│   ├── prompt-plantilla.md            ← protocolo diario
│   ├── guia-captura-datos.md          ← cómo llenar los CSVs
│   └── guia-github.md                 ← cómo subir a GitHub
├── simulaciones/
│   └── YYYY-MM-DD-sesion-NN.md        ← registro por sesión
├── prompts/
│   ├── README-prompts.md              ← metodología
│   └── YYYY-MM-DD/
│       └── P001-PNNN.md               ← evidencia experimental
└── datos/
    ├── README-datos.md                ← diccionario de datos
    ├── entradas/
    │   ├── E1-prensa/
    │   ├── E2-timeline/
    │   ├── E4-ruido-narrativo/
    │   └── E5-mercados/
    └── salidas/
        ├── S1-narrativas/
        ├── S2-estado-factual/
        ├── S3-desinformacion/
        ├── S4-escenarios/
        ├── convergencia.csv
        └── validacion/
```

---

## 15. Roadmap

| Versión | Estado | Descripción |
|---------|--------|-------------|
| v0.1.0 | ✅ | Arquitectura inicial |
| v0.1.1 | ✅ | Evidencia experimental sesión 01 |
| v0.1.2 | ✅ | Infraestructura de datos |
| v0.1.3 | ✅ | Diseño experimental completo |
| v0.2.0 | ⬜ | Primera sesión operativa |
| v0.3.x | ⬜ | GitHub Actions — validación automática |
| v1.0.0 | ⬜ | Sistema operativo completo |

---

*Diseño experimental v0.1.3 — Iran Conflict Model*
*Fase 1 completada el 2026-04-06*
