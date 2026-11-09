# Clave de etiquetas X/Y — experimento A/B de la S16

> **Este archivo NO se entrega a Gemini.** Queda fuera del paquete cerrado del anexo B ([diseno-experimento-ab.md](../diseno-experimento-ab.md), sección 8).

## Resultado

| Campo | Valor |
|---|---|
| Fecha y hora del lanzamiento | 2026-11-09, 16:58 (hora de Colombia) |
| Quién lanzó | El operador, una sola vez |
| Moneda | $1.000 colombiana |
| Resultado | **Cara** |
| Regla (sección 8 del diseño) | Cara → B = X; sello → B = Y |
| **Asignación** | **Brazo B (protocolo completo, S16) = X · Brazo A (Claude solo) = Y** |

## Declaraciones

- **El lado "cara" no se definió antes del lanzamiento** ni se describió después: el operador informó "cayó cara", sin decir si quedó arriba la tortuga o el número. Cualquiera de las dos lecturas convencionales de "cara" en esa moneda produce una asignación válida, porque la regla solo exige que el azar, y no una elección, fije las etiquetas.
- Como ya declara el diseño, el operador podría haber repetido el lanzamiento sin que nadie lo notara. Lo que está en juego es poco: las etiquetas solo ocultan los nombres ante Gemini, que antes de calificar dice si cree poder inferir cuál es B.
- El lanzamiento se hizo después de cerrar los dos brazos: el brazo A en el commit `1b2c040` y el brazo B en el commit `b934e4e`, los dos del 9 nov 2026. Fue antes de preparar cualquier paquete para Gemini.
