# El ICM como línea de procesos

**Fecha:** 10 de octubre de 2026 · **Estado:** borrador

## Encuadre

En ingeniería de software, una **línea de productos** es una familia de sistemas con un **núcleo común** y **puntos de variación**, desarrollada en dos procesos: **ingeniería de dominio** (construir el núcleo) e **ingeniería de aplicación** (derivar cada producto). Ver Pohl, Böckle y van der Linden (2005) y el método FODA de Kang y otros (1990).

Como lo que se reutiliza aquí es un **método**, no un programa, el encaje más exacto es:
- **Líneas de procesos** (Rombach): familias de procesos con un proceso de referencia y variantes;
- **Ingeniería de métodos situacional** (Brinkkemper; Henderson-Sellers, Ralyté y otros): armar un método a la medida de una situación con fragmentos de un repositorio.

Referencias completas en [estado-del-arte.md](estado-del-arte.md) §8.

## Los miembros de la familia

| Variante | Tipo | Estado |
|---|---|---|
| ICM v0.2.0 (S01–S13) | Producto completo | Cerrado |
| CEM ("ICM Lite") | Variante liviana, de horizonte corto | Cerrado y resuelto (equivocado) |
| Seguimientos extraoficiales (S14, S15…) | Variante de seguimiento posterior al cierre | Activa |
| ICM-Colombia (P3) | Variante futura | Por derivar |
| Versión pedagógica (P7) | Variante futura | Por derivar |

## Núcleo común

Sesgo declarado · "no sé" como respuesta válida · falsación antes del resultado · registro de versiones · mejora continua (Kaizen).

## Modelo de características (borrador)

```
Protocolo de análisis humano-IA
├── [obligatorio] Sesgo declarado
├── [obligatorio] Criterio de falsación previo al resultado
├── [obligatorio] Registro solo de agregar
├── [obligatorio] Mejora continua (Kaizen)
├── [obligatorio] "No sé" como respuesta válida
├── Dominio ........................ [alternativo] Geopolítica | Elecciones | ...
├── Horizonte ...................... [alternativo] Largo (98 días) | Corto (21 días) | Seguimiento
├── Taxonomía de entradas [F]/[P]/[R]/[PR] .. [alternativo] Desde el inicio | Retroactiva
├── Fuentes ........................ [alternativo] Diversidad por bloques | Ecosistema con exclusiones
├── Corrección del sesgo ........... [alternativo] Descuento fijo | Descuento adaptativo
├── Ancla externa de mercado ....... [opcional]
├── Métrica de salud (convergencia / entropía) [opcional]
├── Umbral de cambio (K21) ......... [opcional]
├── Calificación independiente ..... [opcional]
└── Base causal formal (escalera de Pearl) [opcional]
```

## Configuración de cada variante

| Característica | ICM v0.2.0 | CEM | S15 |
|---|---|---|---|
| Dominio | Geopolítica | Elecciones (país propio del operador) | Geopolítica |
| Horizonte | 98 días | 21 días | Seguimiento |
| Taxonomía de entradas | Desde el inicio | **Retroactiva** | Sí (✅/🟡/⚪) |
| Fuentes | Mixtas | **Ecosistema con exclusiones** | Diversidad por 9 bloques |
| Corrección del sesgo | Declaración más K25 | **Descuento fijo del 30%** | K25 |
| Ancla de mercado | Desde S01 | **Tardía (v28) y subponderada** | Declarada; sin cuotas verificables |
| Métrica de salud | Convergencia (estimada) | **Ausente** | Convergencia (estimada; contradicha por la entropía) |
| Umbral de cambio | K21 (desde S12) | **Ausente** | K21 |
| Calificación independiente | **No** | **No** | **No** (pendiente) |
| Base causal formal | Pearl | **Ausente** | Implícita |

## Lecciones del CEM convertidas en restricciones

Las restricciones entre características son las reglas que impiden derivar una variante defectuosa. Estas salen de fallas documentadas en el [POST-ELECTORAL.md del CEM](https://github.com/ensayos-aaad/modelo-electoral-colombia/blob/main/POST-ELECTORAL.md):

| # | Restricción | Origen |
|---|---|---|
| R-1 | **Si** hay un sesgo declarado fuerte, **entonces** son obligatorios el descuento adaptativo y el ancla de mercado | CEM lección 1: con el mercado por encima del 85% en contra, el descuento debe ser ≥50%, no 30% |
| R-2 | **Si** hay una señal de mercado con alta convicción, **entonces** el mercado actúa como ancla, no como calibrador secundario | CEM lección 2 y "muda más importante" |
| R-3 | **Si** el dominio es el país propio del operador, **entonces** la calificación independiente es obligatoria (y conviene que no sea el primer caso del método) | CEM lección 6 |
| R-4 | **Si** el horizonte es corto, **entonces** la taxonomía de entradas es obligatoria desde la primera sesión | CEM lección 5; inflación de +296K |
| R-5 | **Si** se usa "ecosistema con exclusiones", **entonces** hay que justificar cada exclusión y contrastar periódicamente con la fuente excluida | Hipótesis: el CEM excluyó medios de derecha y subestimó a la derecha. **Causalidad no demostrada** |
| R-6 | **Siempre:** una métrica de salud calculada, no solo estimada | El CEM careció de ella; en el ICM la convergencia estimada contradice la entropía (ver marco-conceptual §6) |
| R-7 | **Siempre:** calificación posterior por alguien distinto del operador | Autocalificación del CEM: 96/100 antes del resultado y 78/100 después |

## Interacción de características

En líneas de productos, quitar una característica puede romper otra que dependía de ella. El CEM es un caso documentado: al quitar la taxonomía y la métrica de salud, el descuento adversarial quedó sin forma de detectar que era insuficiente.

## Uso para la réplica

Replicar el método deja de ser "volver a hacer lo mismo" y pasa a ser **derivar una variante de la línea**: elegir los puntos de variación, aplicar las restricciones R-1 a R-7 y documentar la configuración. La siguiente derivación deliberada (ICM-Colombia, P3) serviría para confirmar o refutar las restricciones.

## Decisión del operador sobre fuentes excluidas (10 oct 2026)

**Se mantiene lo definido previamente; no se cambia nada.** El operador consideró levantar la exclusión de La Silla Vacía y decidió no hacerlo, para no desestabilizar lo ya definido.

- **Exclusiones del CEM** (Semana, El Colombiano, AtlasIntel, La Silla Vacía): siguen vigentes como decisiones del operador.
- **ICM y seguimientos:** nunca tuvieron una lista de exclusiones; se mantienen como están. La S15 **no usó** La Silla Vacía (solo apareció en el plan de fuentes acordado en la conversación), así que esta decisión no altera nada de lo publicado.
- **R-5** queda como **restricción propuesta** para variantes futuras (justificar por escrito y contrastar periódicamente cada exclusión), sin aplicarse hacia atrás.

**Inconsistencia declarada, sin corregir:** la S15 usó **Semana**, una fuente excluida en el CEM, como única fuente de la fecha de inauguración de la embajada colombiana en Jerusalén (15 de octubre, anunciada por Sa'ar el 8 de octubre). El restablecimiento de relaciones (11 de agosto) tiene otras fuentes independientes (Infobae, ABC Color, El Financiero, TRT). No se edita la S15; la inconsistencia se registra aquí y se tendrá en cuenta al resolver el ítem 3.7.
