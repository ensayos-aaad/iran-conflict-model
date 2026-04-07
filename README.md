# Iran Conflict Model (ICM)
> Sistema de análisis de conflictos mediante inferencia causal y fuentes abiertas

**Versión:** v0.1.4  
**Fecha de inicio:** 2026-04-06  
**Última sesión:** Sesión 02 — 2026-04-06  
**Próxima sesión:** Sesión 03 — 2026-04-08 — 8:00 PM Colombia (UTC-5)  
**Estado:** OPERATIVO — CONVERGIENDO (señal 0.73)  
**Metodología base:** Inferencia causal (Judea Pearl, *The Book of Why*, 2018)

---

## Estado del modelo

| Campo | Valor |
|-------|-------|
| Sesiones completadas | 2 |
| Última sesión | Sesión 02 — 2026-04-06 |
| Vectores procesados (acumulado) | 17 |
| Señal de convergencia | 0.73 — CONVERGIENDO |
| Escenario dominante | A — Alto al fuego 45 días |
| Probabilidad Escenario A (30 días) | 0.66 |
| Día del conflicto | 38 |
| Nodo crítico activo | N1 — Ultimátum 7 abril 8PM ET |

### Probabilidades S4 — Horizonte 30 días (al 6 mayo)

| Escenario | Descripción | Probabilidad |
|-----------|-------------|-------------|
| A | Alto al fuego + Hormuz parcialmente abierto | **0.66** |
| B | Guerra prolongada — Hormuz cerrado | 0.13 |
| C | Escalada — ataque infraestructura crítica | 0.13 |
| D | Colapso régimen iraní | 0.05 |
| E | Wildcard operacional | 0.03 |

### Scores de convergencia

| Score | S02 | S03-pre | Δ |
|-------|-----|---------|---|
| Narrativas | 0.55 | 0.62 | ↑ |
| Factual | 0.78 | 0.82 | ↑ |
| Ruido | 0.44 | 0.38 | ↓ |
| Escenarios | 0.74 | 0.72 | ↓ |
| **Convergencia global** | **0.75** | **0.73** | ↓ leve |

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
| E5 | Señales de mercado | Cuantitativa | Petróleo, VIX, oro, shipping — datos duros en tiempo real |

---

## Motor de inferencia

Basado en la **Escalera de Causalidad de Judea Pearl** (tres peldaños):

### Peldaño 1 — Ver (*Association*)
Detección de correlaciones cruzadas entre las 5 entradas. Identifica qué variables se mueven juntas y en qué secuencia temporal.

### Peldaño 2 — Intervenir (*Intervention*)
Análisis de qué cambia en el sistema cuando ocurre un evento. Modela efectos de intervenciones reales sobre el conflicto.

### Peldaño 3 — Imaginar (*Counterfactual*)
Razonamiento contrafáctico: ¿qué hubiera ocurrido si X no hubiera pasado? Base para la construcción de escenarios prospectivos.

### Componentes internos

- **Análisis de correlación cruzada** — relaciones no obvias entre entradas
- **Detección de patrones temporales** — comparación contra conflictos históricos
- **Análisis de disonancia narrativa** — distancia entre relatos de actores
- **Razonamiento bayesiano** — actualización continua de probabilidades

---

## Salidas (4)

| # | Salida | Pregunta que responde |
|---|--------|----------------------|
| S1 | Mapa de narrativas | ¿Quién construye qué relato y con qué intención? |
| S2 | Estado factual | ¿Qué ocurrió realmente, depurado de ruido? |
| S3 | Índice de desinformación | ¿Cuánto del debate público es propaganda? |
| S4 | Escenarios prospectivos | ¿Hacia dónde puede ir el conflicto? |

> Las salidas S1, S2 y S3 alimentan S4. Los escenarios prospectivos son tan robustos como la calidad de las tres salidas anteriores.

---

## Meta-salida

### Señal de convergencia
Indicador de segundo orden que mide cuándo el sistema se estabiliza. Se activa cuando las 4 salidas empiezan a apuntar en la misma dirección — narrativas estables, hechos verificados, ruido bajo, escenarios reducidos.

No mide el conflicto — mide el comportamiento del propio sistema.

---

## Lazos de retroalimentación (3)

El sistema opera en **ciclo cerrado**. Las salidas corrigen las entradas en cada iteración.

### L1 — Corrección de fuentes
**Desde:** Estado factual (S2)  
**Hacia:** Fuentes de prensa (E1) y Ruido narrativo (E4)  
**Función:** Ajusta el peso de cada fuente según su historial de precisión. Una fuente que reportó algo demostrado falso reduce su peso en consultas posteriores.

### L2 — Calibración de ruido
**Desde:** Índice de desinformación (S3)  
**Hacia:** Ruido narrativo (E4) y Señales de mercado (E5)  
**Función:** Cuando el ruido narrativo está en niveles extremos, filtra más agresivamente las señales de mercado — porque en momentos de alto ruido, los mercados también se contaminan con pánico, no solo con fundamentals.

### L3 — Aprendizaje del sistema
**Desde:** Señal de convergencia (meta-salida)  
**Hacia:** Motor de inferencia  
**Función:** Recalibra las probabilidades bayesianas de todos los escenarios cuando detecta estabilización o desestabilización. El sistema no mantiene sus apuestas iniciales — las actualiza con cada ciclo.

---

## Fuentes por entrada

### E1 — Fuentes de prensa

| Región | Medio | URL |
|--------|-------|-----|
| América del Norte | Reuters | reuters.com |
| América del Norte | Associated Press | apnews.com |
| América del Norte | Politico | politico.com |
| Europa | BBC News | bbc.com/news |
| Europa | The Guardian | theguardian.com |
| Europa | Deutsche Welle | dw.com |
| Europa | France 24 | france24.com |
| Europa | El País | elpais.com |
| Medio Oriente | Al Jazeera | aljazeera.com |
| Medio Oriente | Haaretz | haaretz.com |
| Medio Oriente | Times of Israel | timesofisrael.com |
| Asia | South China Morning Post | scmp.com |
| Medio Oriente | Tehran Times | tehrantimes.com ⚠️ sesgo oficial iraní |
| África | Daily Maverick | dailymaverick.co.za |
| Oceanía | ABC Australia | abc.net.au/news |
| América Latina | Infobae | infobae.com |

### E4 — Ruido narrativo

| Actor | Canal | Notas |
|-------|-------|-------|
| Trump | Truth Social @realDonaldTrump | Narrativa oficial EEUU |
| Casa Blanca | X @WhiteHouse | Posición oficial |
| IDF | X @IDF | Fuente militar israelí |
| Netanyahu | X @netanyahu | Posición oficial Israel |
| Israel MFA | X @IsraelMFA | Cancillería israelí |
| Jamenei | X @khamenei_ir | Canal oficial iraní |
| IRGC | Telegram canal oficial | Cuerpo de Guardia Revolucionaria |
| Press TV | presstv.ir | Medio estatal iraní en inglés |
| IRNA | irna.ir | Agencia oficial iraní |
| MFA Rusia | X @mfa_russia | Posición oficial Rusia |
| MFA China | X @MFA_China | Posición oficial China |
| Al Qassam | X / Telegram | Brigadas Hamas ⚠️ actor no estatal |
| Hezbollah Media | Telegram canal oficial | ⚠️ actor no estatal |

### E5 — Señales de mercado

| Indicador | Fuente | URL |
|-----------|--------|-----|
| Petróleo WTI / Brent | Oilprice.com | oilprice.com |
| Mercados generales | Bloomberg Markets | bloomberg.com/markets |
| Mercados generales | Reuters Markets | reuters.com/markets |
| Macro / commodities | TradingEconomics | tradingeconomics.com |
| Energía EEUU | EIA | eia.gov |
| OPEC | OPEC Newsroom | opec.org |
| Volatilidad / miedo | CBOE VIX | cboe.com/vix |
| Oro | Gold Price | goldprice.org |
| Shipping | Baltic Exchange | balticexchange.com |

---

## Punto de inicio histórico

### Guerra de los 12 Días — 13 al 24 junio 2025
Israel lanzó la Operación Rising Lion contra instalaciones nucleares, bases militares y liderazgo militar iraní. EEUU se unió el 22 de junio atacando Natanz, Fordow e Isfahan. Ceasefire el 24 de junio. Bajas: ~610 iraníes, 29 israelíes.

### Guerra de 2026 — inicio 28 febrero 2026
EEUU e Israel lanzaron operación conjunta (Epic Fury / Roaring Lion) contra Irán durante negociaciones nucleares en curso. El líder supremo Ali Jamenei fue asesinado en Teherán. Confirmado por medios iraníes el 1 de marzo de 2026. Su hijo Mojtaba Jamenei fue designado sucesor el 8 de marzo de 2026 por la Asamblea de Expertos.

**Estado a fecha de inicio del modelo: conflicto activo — 6 de abril de 2026.**

---

## Limitaciones del sistema

- El motor de inferencia opera mediante dialéctica humano-IA — no es un sistema automatizado
- Las correlaciones identificadas son probabilísticas, no deterministas
- El acceso a fuentes con paywall es parcial
- El ruido narrativo de actores no estatales es de difícil verificación
- La matemática bayesiana es ejecutada por el motor IA — no está implementada en código formal

---

## Historial de sesiones

| Sesión | Fecha | Vectores | Convergencia | Escenario A | Estado |
|--------|-------|----------|--------------|-------------|--------|
| 01 | 2026-04-06 | 3 | 0.47 — INESTABLE | 0.50 | ✅ Completa |
| 02 | 2026-04-06 | 17 | 0.75 — CONVERGIENDO | 0.64 | ✅ Completa |
| 03 | 2026-04-08 | — | — | — | 🔜 Programada |

---

## Roadmap

- [x] v0.1.0 — Arquitectura conceptual documentada
- [x] v0.1.4 — Sesiones 01 y 02 completadas — sistema CONVERGIENDO
- [ ] v0.2.0 — Pipeline de scraping automatizado
- [ ] v0.3.0 — Motor bayesiano implementado en código
- [ ] v1.0.0 — Sistema operativo completo

---

## Referencia metodológica principal

Pearl, J. & Mackenzie, D. (2018). *The Book of Why: The New Science of Cause and Effect*. Basic Books.

---

*Proyecto iniciado el 6 de abril de 2026. Operado mediante dialéctica humano-IA.*
