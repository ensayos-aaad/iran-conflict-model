# Guía de captura de datos — Iran Conflict Model (ICM)

## ¿Para qué sirve esta guía?

Después de cada sesión Claude genera los datos del día. Esta guía te explica exactamente cómo copiar esos datos a los archivos CSV del repositorio. No necesitas saber programar.

---

## Lo que necesitas

- El output de Claude de la sesión del día
- Los archivos CSV del repositorio abiertos en Excel, Google Sheets, o cualquier editor de texto
- 10 minutos

---

## Paso a paso después de cada sesión

### Paso 1 — Abre los archivos CSV

Abre estos archivos del repositorio. Puedes usar Excel, Google Sheets, o el bloc de notas:

```
datos/entradas/E1-prensa/         → crea archivo YYYY-MM-DD.csv
datos/entradas/E4-ruido-narrativo/ → crea archivo YYYY-MM-DD.csv
datos/entradas/E5-mercados/        → crea archivo YYYY-MM-DD.csv
datos/salidas/S1-narrativas/       → crea archivo YYYY-MM-DD.csv
datos/salidas/S2-estado-factual/   → crea archivo YYYY-MM-DD.csv
datos/salidas/S3-desinformacion/   → crea archivo YYYY-MM-DD.csv
datos/salidas/S4-escenarios/       → crea archivo YYYY-MM-DD.csv
datos/salidas/convergencia.csv     → agrega una fila al final
datos/validacion/registro-validacion.csv → agrega filas de S4
```

---

### Paso 2 — Copia los datos del output de Claude

Claude genera al final de cada sesión bloques de datos con este formato:

```
--- DATOS S2 ---
fecha,sesion,hecho,tipo,certeza,...
2026-04-07,2,IRGC lanzó misiles,...
```

Copia cada bloque y pégalo en el archivo CSV correspondiente como una fila nueva. Respeta el orden de las columnas — debe coincidir exactamente con el schema.

---

### Paso 3 — Llena convergencia.csv

Agrega una fila al final del archivo con los scores que Claude generó:

```csv
2026-04-07,2,0.35,0.62,0.74,0.48,0.55,INESTABLE,Primera sesión operativa
```

---

### Paso 4 — Llena registro-validacion.csv

Por cada escenario que Claude generó en S4, agrega dos filas — una por cada horizonte:

```csv
2026-04-07,2,Escalada total,0.25,7,2026-04-14,NO EVALUABLE,
2026-04-07,2,Escalada total,0.25,30,2026-05-07,NO EVALUABLE,
```

El campo `resultado` siempre empieza como `NO EVALUABLE`. Lo actualizas cuando vence la fecha de evaluación.

---

### Paso 5 — Haz el commit

Abre la terminal en la carpeta del repositorio y ejecuta:

```bash
git add .
git commit -m "sesión [NÚMERO] — [FECHA] — [TIPO]"
git push
```

Ejemplo:
```bash
git add .
git commit -m "sesión 02 — 2026-04-07 — ESTANDAR"
git push
```

---

## Cómo crear un archivo CSV nuevo por fecha

Cuando Claude termine la sesión, toma el schema de la carpeta correspondiente y crea una copia con el nombre de la fecha:

```
schema.csv → 2026-04-07.csv
```

Luego agrega las filas debajo de la línea de encabezados.

---

## Cómo actualizar registro-validacion.csv cuando vence un horizonte

Cuando llegue la fecha de evaluación de un escenario:

1. Abre `datos/validacion/registro-validacion.csv`
2. Busca la fila con esa `fecha_evaluacion`
3. Cambia `NO EVALUABLE` por uno de estos valores:
   - `OCURRIO` — si el escenario se materializó
   - `PARCIAL` — si ocurrió parcialmente
   - `NO OCURRIO` — si no ocurrió
4. Agrega notas si quieres
5. Haz commit

```bash
git add .
git commit -m "validación escenario sesión [N] — horizonte [X] días"
git push
```

---

## Reglas importantes

```
✓ Nunca borres filas — solo agrega
✓ Nunca cambies los encabezados de los CSVs
✓ Usa siempre el formato de fecha YYYY-MM-DD
✓ Los decimales van con punto, no con coma (0.25 no 0,25)
✓ Si un campo no tiene valor escribe NULL — no lo dejes vacío
✓ Un archivo CSV por día por entrada — no mezcles fechas
```

---

## Si algo sale mal

Si cometiste un error en un CSV, no lo borres. Agrega una nota en el campo `notas` de esa fila explicando el error. La trazabilidad es más importante que la perfección.

---

*Guía de captura v0.1.3 — para experimentadores sin experiencia técnica.*
