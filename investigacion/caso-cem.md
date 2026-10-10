# Caso de comparación: Colombia Electoral Model (CEM)

**Fecha:** 10 de octubre de 2026 · **Fuente:** [ensayos-aaad/modelo-electoral-colombia](https://github.com/ensayos-aaad/modelo-electoral-colombia), principalmente su README y su [POST-ELECTORAL.md](https://github.com/ensayos-aaad/modelo-electoral-colombia/blob/main/POST-ELECTORAL.md). Las 15 sesiones no se revisaron todavía en detalle.

## Ficha

| Campo | Valor |
|---|---|
| Objeto | Segunda vuelta presidencial de Colombia, 21 de junio de 2026 (Cepeda frente a De la Espriella) |
| Período | 31 de mayo – 20 de junio de 2026 (21 días) |
| Protocolo | "ICM Lite", derivado del ICM |
| Modelo | Claude Sonnet 4.6, en claude.ai |
| Versiones | 32 (v1 → v31 FINAL) · 15 sesiones Kaizen |
| Sesgo declarado | Preferencia por Cepeda, con un descuento adversarial fijo del 30% |
| Condiciones declaradas | País propio del operador, desgaste acumulado, tiempo fragmentado |

## Pronóstico y resultado

| | Proyección v31 (20 jun) | Resultado (21 jun) |
|---|---|---|
| Ganador | Cepeda | **De la Espriella** |
| Margen | Cepeda +402.000 votos / +1,8 pp | De la Espriella +0,95 pp (~248.000 votos según la sección 1; el propio documento usa también 250.694 y ~262.000 en otras secciones) |
| Participación | 52–55% | ~63,6% |
| Probabilidades | P(Cepeda) 52% · P(Espriella) 40% · 8% sin asignar | — |

**Veredicto del propio CEM, con el criterio declarado el 20 de junio y aplicado sin modificación:** *"EL MODELO ESTUVO EQUIVOCADO."*

## Comparación con otras señales

| Señal | Pronóstico | Acertó la dirección | Brier (pregunta: ¿gana Cepeda?) |
|---|---|---|---|
| CEM v31 | P(Cepeda) = 0,52 | No | **0,270** (0,52²) |
| Encuesta presencial CNC | De la Espriella +3,9 pp | Sí (margen sobreestimado) | — (no es probabilística) |
| Polymarket | P(Espriella) = 0,89 → P(Cepeda) = 0,11 | Sí | **0,012** (0,11²) |
| Línea base (siempre 50%) | 0,50 | — | 0,250 |

**Nota de cálculo:** el CEM dejó un 8% sin asignar. Si se puntúa P(Espriella) = 0,40 en lugar de 1 − 0,52, el Brier sobre "gana Espriella" es (1 − 0,40)² = 0,36. Las dos lecturas están por encima de la línea base de 0,25.

## Lo que el CEM aporta a la investigación

1. **Es el único caso resuelto de principio a fin**, y salió en contra del método como herramienta de pronóstico: el mercado le ganó claramente. Coincide con Vaccaro y otros (2024): en decisiones, la combinación humano-IA suele rendir peor que el mejor de los dos por separado.
2. **La mitad ética del método funcionó:** el criterio de falsación se aplicó sin trampas, y el error se documentó con el mismo rigor que se habría documentado un acierto.
3. **Las autocalificaciones se inflan antes del resultado:** Kaizen 15 (antes): operador 96/100 y modelo 94/100; Kaizen post-electoral: operador 78/100 y modelo 85/100. Es evidencia directa a favor de la calificación independiente y posterior.
4. **Los patrones ausentes coinciden con fallas** documentadas: la taxonomía tardía, la falta de métrica de salud y de umbral, y el mercado tardío y subponderado. Ver [patrones-candidatos.md](patrones-candidatos.md) y [linea-de-procesos.md](linea-de-procesos.md).
5. **Hipótesis de mecanismo, no demostradas:**
   - **Complacencia del modelo:** un modelo que refleja la postura del operador amplificaría el sesgo declarado. Se puede comprobar reetiquetando en las sesiones quién propuso cada variable favorable a Cepeda.
   - **Cierre del ecosistema de fuentes:** se excluyeron medios con sesgo de derecha documentado, y el error fue subestimar a la derecha. Hay otras explicaciones posibles (la carga emocional, el peso del mercado).
6. **Condición límite:** según su lección 6, el método no debe estrenarse con el país propio del operador. Es relevante para el ICM-Colombia (P3).

## Discrepancias y cautelas

- El README del CEM afirma sobre el ICM algunas cosas que conviene verificar contra este repositorio antes de citarlas: por ejemplo, la taxonomía [F]/[P]/[R]/[PR] "desde S01" y una convergencia de "0.51→0.87".
- Las cifras de margen difieren entre secciones del POST-ELECTORAL (247.686 / 250.694 / ~262.000), según el boletín usado. Para la investigación hay que fijar una sola cifra, con el boletín de la Registraduría que corresponda.

## Pendiente

- Revisar las 15 sesiones del CEM para reetiquetar el origen de cada variable (operador o IA) y medir la complacencia.
- Agregar al registro de errores (`registro-errores.csv`) los errores detectados y corregidos en el CEM, como la auditoría de inflación del día 15.
