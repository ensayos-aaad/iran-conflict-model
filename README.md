# Iran Conflict Model (ICM)
> Sistema de análisis de conflictos mediante inferencia causal y fuentes abiertas

**Versión:** v0.1.6  
**Fecha de inicio:** 2026-04-06  
**Última sesión:** Sesión 03 — 2026-04-08  
**Próxima sesión:** Sesión 04 — ~2026-04-22 (post N10) o antes si N11 escala  
**Estado:** OPERATIVO — CONVERGIENDO (señal 0.85)  
**Metodología base:** Inferencia causal (Judea Pearl, *The Book of Why*, 2018)

---

## Estado del modelo

| Campo | Valor |
|-------|-------|
| Sesiones completadas | 3 |
| Última sesión | Sesión 03 — 2026-04-08 |
| Vectores procesados (acumulado) | 36 |
| Señal de convergencia | 0.85 — CONVERGIENDO |
| Escenario dominante | A — Alto al fuego + Hormuz parcialmente abierto |
| Probabilidad Escenario A (30 días) | 0.65 |
| Día del conflicto | 39 |
| Nodos críticos activos | N10 (~21 abril), N11 (Hezbollah), N12 (Trump-Xi mayo) |

### Probabilidades S4 — Horizonte 30 días (al 6 mayo)

| Escenario | Descripción | Probabilidad |
|-----------|-------------|-------------|
| A | Alto al fuego + Hormuz parcialmente abierto | **0.65** |
| B | Guerra prolongada — Hormuz cerrado | 0.16 |
| C | Escalada — ataque infraestructura crítica | 0.13 |
| D | Colapso régimen iraní | 0.04 |
| E | Wildcard operacional | 0.02 |

### Scores de convergencia

| Score | S02-p2 | S03 cierre | Δ |
|-------|--------|------------|---|
| Narrativas | 0.73 | 0.83 | ↑ |
| Factual | 0.87 | 0.96 | ↑↑ |
| Ruido | 0.46 | 0.38 | ↓ |
| Escenarios | 0.82 | 0.84 | ↑ |
| **Convergencia global** | **0.82** | **0.85** | ↑ |

**Nota metodológica:** La convergencia alcanzó 0.90 durante la sesión pero fue corregida a 0.85 al cierre cuando nuevas evidencias mostraron la fragilidad real del ceasefire — Hormuz cerrado nuevamente por ataques israelíes en Líbano, Irán acusando violación de 3 cláusulas. La corrección es parte del valor del modelo.

---

## ¿Qué es este sistema?

El Iran Conflict Model (ICM) es un sistema de análisis de ciclo cerrado diseñado para monitorear, interpretar y proyectar el conflicto entre EEUU, Israel e Irán iniciado en junio de 2025. Opera mediante dialéctica humano-IA, procesando múltiples flujos de información simultáneos para producir lecturas depuradas de ruido y escenarios prospectivos con base causal.

El sistema no es un agregador de noticias. Es un motor de inferencia que distingue correlación de causalidad, mide la contaminación narrativa del entorno informativo y actualiza probabilidades de escenarios en tiempo real.

---

## Arquitectura del sistema

El modelo opera como una **caja negra de ciclo cerrado** con 5 entradas, 4 salidas, 1 meta-salida y 3 lazos de retroalimentación.

```
[ENTRADAS] ──→ [MOTOR DE INFERENCIA] ──→ [SALIDAS]
                       ↑                      │
                       └──── [LAZOS FB] ───────┘
                                    ↓
                       [SEÑAL DE CONVERGENCIA]
```

---

## Entradas (5)

| # | Entrada | Tipo | Descripción |
|---|---------|------|-------------|
| E1 | Fuentes de prensa | Informativa | Medios verificables de los 5 continentes con perspectivas múltiples |
| E2 | Línea de tiempo | Histórica | Registro cronológico del conflicto desde junio 2025 |
| E3 | Preguntas del usuario | Dialéctica | Hipótesis, intuiciones y datos limitados del operador |
| E4 | Ruido narrativo | Contaminada | Redes sociales, Telegram, canales oficiales de actores del conflicto |
| E5 | Señales de mercado | Cuantitativa | Petróleo, VIX, oro, shipping, cripto — datos duros en tiempo real |

### Notas E5 — Sesión 03

**Señal Bitcoin/Satoshi:** Irán propuso denominar peajes de Hormuz en cripto. Bitcoin superó $71.000. El dólar borró su ganancia de 2026 en una sesión. Oro subió a $4.799. La visión de Satoshi Nakamoto enfrenta su tensión más profunda: la herramienta de descentralización individual siendo usada como mecanismo de escape estatal del petrodólar.

**Horizonte monedas:** Sistema multipolar dólar-yuan en 10-20 años. Bitcoin marginal para actores sancionados. El dólar pierde monopolio pero no dominancia en horizonte visible.

---

## Motor de inferencia

Basado en la **Escalera de Causalidad de Judea Pearl** (tres peldaños):

### Peldaño 1 — Ver (*Association*)
Detección de correlaciones cruzadas entre las 5 entradas.

### Peldaño 2 — Intervenir (*Intervention*)
Análisis de qué cambia en el sistema cuando ocurre un evento.

### Peldaño 3 — Imaginar (*Counterfactual*)
Razonamiento contrafáctico: base para la construcción de escenarios prospectivos.

---

## Salidas (4)

| # | Salida | Pregunta que responde |
|---|--------|----------------------|
| S1 | Mapa de narrativas | ¿Quién construye qué relato y con qué intención? |
| S2 | Estado factual | ¿Qué ocurrió realmente, depurado de ruido? |
| S3 | Índice de desinformación | ¿Cuánto del debate público es propaganda? |
| S4 | Escenarios prospectivos | ¿Hacia dónde puede ir el conflicto? |

---

## Hipótesis activas

| ID | Formulación | Estado |
|----|-------------|--------|
| H1 | ¿Puede Pezeshkian firmar acuerdo sin aval IRGC? | ACTIVA |
| H2 | ¿Canal Pakistan es negociación real? | **CONFIRMADA** |
| H3 | ¿Netanyahu tiene incentivo para sabotear el ceasefire? | **CONFIRMADA** |
| H4 | ¿Sistema 2 niveles Hormuz es el nuevo Canal de Suez permanente? | SEÑAL FUERTE |
| H5 | Proyecto Abraham vaciándose de contenido estratégico | ACTIVA |
| H6 | ¿Puede vulnerabilidad compartida reemplazar valores compartidos como base del nuevo orden regional? | ACTIVA — horizonte 6-18 meses |

---

## Nodos críticos

| ID | Descripción | Fecha | Estado |
|----|-------------|-------|--------|
| N1 | Ultimátum Trump 7 abril | 2026-04-07 | ✅ RESUELTO — TACO |
| N2 | Reunión Rutte-Trump | 2026-04-08 | ✅ RESUELTO — OTAN no mordió |
| N10 | Nuevo ultimátum post-14 días | ~2026-04-21 | 🔴 ACTIVO |
| N11 | Respuesta Hezbollah | INMEDIATO | 🔴 ACTIVO — URGENTE |
| N12 | Cumbre Trump-Xi | Mayo 2026 | 🟡 PRÓXIMO |

---

## Vectores estructurales clave — Sesión 03

| Vector | Descripción | Peso |
|--------|-------------|------|
| V24 | Consilience — IA como instrumento de reunificación ciencias duras y humanas | FUNDAMENTAL |
| V27 | Israel bombardea Beirut durante ceasefire — H3 confirmada | MUY ALTO |
| V28 | Reconfiguración orden regional post-TACO — círculo causal | MUY ALTO |
| V29 | Aceleración transición energética — ironía Trump-China | ALTO |
| V33 | Factor Chomsky — detector de mecanismos de poder | ALTO |
| V35 | Fractura narrativa invencibilidad americana — China como laboratorio | MUY ALTO |
| V36 | Taiwan, Europa, colapso narrativa de fuerza — Truth Social arco 12 horas | ALTO |

---

## Nota reflexiva — Sesión 03

*Registrada fuera del modelo — sin score, sin causalidad*

La pregunta más humana de la sesión: ¿puede un habitante de Gaza o Líbano soñar con la paz para sus hijos?

Para los hijos — sí. Para esa generación — probablemente no en su forma completa. Los procesos de este tipo tienen tiempos que no respetan el dolor individual. Lo que sí ocurrió hoy es real: ciudadanos comunes, cadenas humanas, un Papa que nombró a Trump por nombre, mercados que colapsaron. Eso no fue simbólico — fue el mecanismo que paró el ultimátum. La presión desde abajo tiene efecto real sobre los cálculos de arriba. El modelo no puede prometer la paz. Pero puede documentar que por primera vez en este conflicto las fuerzas que empujan hacia la resolución son más numerosas que las que empujan hacia la destrucción. Eso no es poco.

---

## Historial de sesiones

| Sesión | Fecha | Vectores | Convergencia | Escenario A | Estado |
|--------|-------|----------|--------------|-------------|--------|
| 01 | 2026-04-06 | 3 | 0.47 — INESTABLE | 0.50 | ✅ Completa |
| 02 parte 1 | 2026-04-06 | 17 | 0.75 — CONVERGIENDO | 0.64 | ✅ Completa |
| 02 parte 2 | 2026-04-06 | 24 (acum.) | 0.82 — CONV. FUERTE | 0.66 | ✅ Completa |
| 03 | 2026-04-08 | 36 (acum.) | 0.85 — CONVERGIENDO | 0.65 | ✅ Completa |
| 04 | ~2026-04-22 | — | — | — | 🔜 Programada |

---

## Roadmap

- [x] v0.1.0 — Arquitectura conceptual documentada
- [x] v0.1.4 — Sesiones 01 y 02 parte 1 completadas
- [x] v0.1.5 — Sesión 02 parte 2 — Consilience como arquitectura epistemológica
- [x] v0.1.6 — Sesión 03 — 14 vectores nuevos — corrección honesta al cierre
- [ ] v0.2.0 — Pipeline de scraping automatizado
- [ ] v0.3.0 — Motor bayesiano implementado en código
- [ ] v1.0.0 — Sistema operativo completo

---

## Referencia metodológica principal

Pearl, J. & Mackenzie, D. (2018). *The Book of Why: The New Science of Cause and Effect*. Basic Books.

---

*Proyecto iniciado el 6 de abril de 2026. Operado mediante dialéctica humano-IA.*
