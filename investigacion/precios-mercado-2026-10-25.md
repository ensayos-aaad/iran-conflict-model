# Precios de mercado al congelamiento (25 de octubre de 2026)

> **Para qué sirve:** es la referencia de mercado de la sección 6.5 del prerregistro. Se congela con él y no se edita.
> **Capturado por:** Claude, desde la API pública de Kalshi (`api.elections.kalshi.com/trade-api/v2`), el **26 oct 2026 a las 02:52 UTC**, que son las **21:52 del 25 de octubre en Colombia** (UTC−5).
> **Precio usado:** el punto medio entre la oferta de compra y la de venta del contrato "Sí".

## Regla de equivalencia (sección 6.5 del prerregistro)

Un contrato es equivalente si pregunta por el mismo evento, con una fecha límite que no difiere en más de 7 días y sin condiciones adicionales que cambien lo que se pregunta. Si no hay contrato equivalente, se registra "sin referencia de mercado". Los contratos parecidos pero no equivalentes se anotan solo como información y **no se usan** para la comparación.

## Precios

| Ítem | Pregunta del prerregistro (resumen) | Contrato | Compra / venta / último | Precio | ¿Equivalente? | Por qué |
|---|---|---|---|---|---|---|
| 3.1 | ¿Los demócratas obtienen mayoría en la Cámara en la elección del 3 nov? | Kalshi `CONTROLH-2026-D`: "Which party will win the U.S. House?", Democratic Party | 0,903 / 0,904 / 0,904 | **0,9035** | **Sí** | Mismo evento (control de la Cámara en la elección de 2026) |
| 3.2 | ¿Acuerdo nuclear EEUU-Irán con texto público, verificación de la OIEA y alivio de sanciones? | Kalshi `KXUSAIRANAGREEMENT-27`: "US-Iran nuclear deal? Before Jan 1, 2027" | 0,091 / 0,092 / 0,092 | 0,0915 | **No** | Kalshi resuelve Sí con que EEUU "acepte o firme" un acuerdo nuevo; el prerregistro exige además texto público, OIEA y alivio de sanciones. Es una cota superior, no una referencia |
| 3.3 | ¿Irán posee un arma nuclear operativa? | — | — | — | **Sin referencia de mercado** | No hay contrato en Kalshi. El de Polymarket ("Iran nuclear test before 2027") pregunta por una prueba nuclear, no por la posesión, y no se pudo leer (ver Límites) |
| 3.4 | ¿Netanyahu es primer ministro el 31 dic, como titular o interino? | Kalshi `KXISRAELPM-26OCT27-BNET`: "Prime Minister of Israel after the 2026 election?", Netanyahu | 0,26 / 0,27 / 0,26 | 0,265 | **No** | Kalshi pregunta si Netanyahu forma el próximo gobierno antes del 27 oct 2027; no cuenta la permanencia como interino al 31 dic. Ver la nota sobre Polymarket |
| 3.5 | ¿Recesión en EEUU con los datos publicados al 31 dic (BEA o NBER)? | Kalshi `KXRECSSNBER-26`: "Recession this year?" | 0,04 / 0,06 / 0,05 | 0,05 | **No** | Kalshi cuenta dos trimestres negativos en 2025 **o** 2026 según la BEA, sin la vía del NBER, y resuelve con datos de enero de 2027; el prerregistro usa los datos publicados al 31 dic |
| 3.6 | ¿Colapso del Estado libanés o anexión? | — | — | — | **Sin referencia de mercado** | No se encontró contrato en Kalshi |
| 3.7 | ¿Colombia cambia su política exterior? | — | — | — | No aplica | Ya resuelto: Sí |
| P-1 | Sanciones, sabotaje atribuido o ataque hutí (10 oct – 3 nov) | — | — | — | **Sin referencia de mercado** | No se encontró contrato |
| P-2 | ¿EEUU confirma apoyo aéreo directo a la ofensiva saudí en Yemen antes del 31 dic? | — | — | — | **Sin referencia de mercado** | No se encontró contrato |
| P-3 | ¿Ataque de Irán o sus aliados con bajas estadounidenses (20 oct – 3 nov)? | — | — | — | **Sin referencia de mercado** | No se encontró contrato |

**Resultado:** solo el ítem **3.1** tiene una referencia de mercado equivalente. La comparación con el mercado del criterio H-3 se hace únicamente sobre las preguntas comparables, como dice el prerregistro.

## Nota sobre Polymarket y el ítem 3.4

Polymarket tiene un contrato "Netanyahu out before 2027?" que podría ser equivalente a 3.4, si sus reglas cuentan la permanencia como interino. Según un agregador (rg.org), el 24 de octubre cotizaba **42 % para "Sí, sale"**, es decir, **58 % para que siga**. Ese valor **no se capturó directamente** y no se pudieron leer sus reglas, así que **no se usa como referencia**. Queda solo como contexto.

## Límites

- **Polymarket no se pudo leer** desde el entorno de Claude: el dominio no resolvía (`ENOTFOUND`), tanto en la web como en su API. Por eso todos los precios capturados son de Kalshi.
- Kalshi no tiene contratos para la mayoría de las preguntas del prerregistro. Los contratos que no se encontraron se registran como "sin referencia de mercado", sin buscar sustitutos.
- Los contratos de Kalshi se encontraron recorriendo los 12.000 eventos abiertos que devuelve su API y filtrando por palabras clave (House, recession, Netanyahu, Israel, Iran, Yemen, Houthi, Lebanon, Hezbollah, nuclear). Puede haber contratos con otros nombres que este filtro no detectó.
