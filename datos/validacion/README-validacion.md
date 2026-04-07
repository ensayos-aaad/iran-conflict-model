# Validación del modelo — Iran Conflict Model (ICM)

## ¿Para qué sirve esta carpeta?

Aquí se registra si lo que el modelo predijo realmente ocurrió. Es la forma de saber si el modelo funciona bien o no.

---

## El único archivo que necesitas

### registro-validacion.csv

Cada vez que el modelo produce un escenario en S4, se agrega una fila aquí. Cuando vence el horizonte temporal, rellenas el campo `resultado`.

---

## Campos del archivo

| Campo | Qué significa | Ejemplo |
|-------|---------------|---------|
| fecha_prediccion | Fecha en que el modelo hizo la predicción | 2026-04-07 |
| sesion | Número de sesión | 2 |
| escenario | Nombre del escenario predicho | Escalada total |
| probabilidad | Probabilidad asignada — entre 0.0 y 1.0 | 0.25 |
| horizonte_dias | En cuántos días se evalúa — 7 o 30 | 7 |
| fecha_evaluacion | Fecha en que debes evaluar | 2026-04-14 |
| resultado | Qué ocurrió realmente | NO OCURRIO |
| notas | Observaciones opcionales | Ceasefire anunciado |

---

## Valores posibles para el campo resultado

| Valor | Cuándo usarlo |
|-------|---------------|
| OCURRIO | El escenario se materializó completamente |
| PARCIAL | Algunos elementos del escenario ocurrieron |
| NO OCURRIO | El escenario no se materializó |
| NO EVALUABLE | Un evento mayor hace que la predicción ya no sea contrastable |

---

## Cómo calcular la fecha de evaluación

```
horizonte_dias = 7  → fecha_evaluacion = fecha_prediccion + 7 días
horizonte_dias = 30 → fecha_evaluacion = fecha_prediccion + 30 días
```

---

## Cómo saber si el modelo es bueno — Brier Score

El Brier Score mide qué tan bien calibradas están las probabilidades. Va de 0.0 a 1.0:

```
0.0  → perfecto
0.25 → igual que adivinar siempre 0.5 — línea de base
1.0  → completamente equivocado
```

Para que el modelo sea útil debe tener un Brier Score menor a 0.25.

Un analista de datos puede calcularlo automáticamente con este archivo una vez tengas al menos 10 predicciones evaluadas.

---

## Ejemplo de cómo se ve el archivo con datos reales

```csv
fecha_prediccion,sesion,escenario,probabilidad,horizonte_dias,fecha_evaluacion,resultado,notas
2026-04-07,2,Escalada total,0.25,7,2026-04-14,NO OCURRIO,Sin movimientos militares mayores
2026-04-07,2,Negociación informal,0.40,7,2026-04-14,PARCIAL,Contactos indirectos via Omán
2026-04-07,2,Escalada total,0.25,30,2026-05-07,NO EVALUABLE,Ceasefire anunciado el 2026-04-20
```

---

*Actualizar con cada nueva sesión operativa.*
