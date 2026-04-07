# Prompt plantilla diario — Iran Conflict Model (ICM)

## Instrucciones para el experimentador

1. Copia el bloque de texto entre las líneas de guiones
2. Reemplaza los campos entre corchetes [ ] con los valores del día
3. Pégalo en Claude al inicio de una sesión nueva
4. Adjunta estos archivos al prompt:
   - README.md
   - CHANGELOG.md
   - simulaciones/2026-04-06-sesion-01.md
   - prompts/2026-04-06/P010-pearl.md
   - prompts/2026-04-06/P011-delegacion-matematica.md

---

## PROMPT ESTÁNDAR — copiar desde aquí

> **Nota sesión inaugural (sesión 02):** Si no puedes correrla a las 8PM,
> cámbia la línea de hora por la hora real y agrega la línea de nota
> excepcional. A partir de la sesión 03 usa siempre 8:00 PM.

```
Nueva simulación — Iran Conflict Model (ICM)
Sesión: [NÚMERO DE SESIÓN — ejemplo: 2]
Fecha: [FECHA — ejemplo: 2026-04-07]
Hora: [HORA REAL si es sesión 02, o 8:00 PM a partir de sesión 03] Colombia (UTC-5)
Tipo de sesión: ESTANDAR
Nota excepcional: [SOLO para sesión 02 — "Sesión inaugural — hora excepcional.
                   Horario estándar 8PM inicia sesión 03." — borrar en sesiones siguientes]
Ventana de captura: últimas 24 horas

Adjunto la documentación del modelo v0.1.3.
El repositorio está en [VERSIÓN — ejemplo: v0.1.3].

El modelo opera con 5 entradas, 4 salidas, 
1 meta-salida y 3 lazos de retroalimentación.
La base metodológica es la Escalera de Causalidad 
de Judea Pearl. La matemática está delegada al sistema.

Por favor ejecuta el modelo completo en este orden:

1. S2 — Estado factual
   Consulta fuentes verificables de las últimas 24 horas.
   ¿Qué ocurrió realmente en el conflicto hoy?

2. S1 — Mapa de narrativas
   Con base en S2, ¿qué está diciendo cada bloque 
   geopolítico y en qué diverge de los hechos?

3. S3 — Índice de desinformación
   ¿Cuánto ruido hay en el sistema hoy?
   Identifica los claims más alejados de los hechos 
   verificados y asígnales un score entre 0.0 y 1.0.

4. S4 — Escenarios prospectivos
   Con base en S1, S2 y S3, produce los escenarios 
   más probables con sus probabilidades para 
   horizontes de 7 y 30 días.

5. Señal de convergencia
   ¿El sistema se está estabilizando o desestabilizando?
   Asigna scores entre 0.0 y 1.0 para:
   - score_narrativas
   - score_factual
   - score_ruido
   - score_escenarios
   - convergencia_global
   Estado: CAOTICO / INESTABLE / TRANSITANDO / 
           CONVERGIENDO / ESTABLE

Al final genera los datos crudos en formato CSV 
para cada salida, listos para copiar al repositorio.
```

---

## PROMPT DE EMERGENCIA — usar cuando ocurre evento crítico

```
Nueva simulación — Iran Conflict Model (ICM)
Sesión: [NÚMERO DE SESIÓN]
Fecha: [FECHA]
Hora: [HORA ACTUAL] Colombia (UTC-5)
Tipo de sesión: EMERGENCIA
Evento disparador: [DESCRIBE EL EVENTO]
Ventana de captura: últimas [X] horas

Adjunto la documentación del modelo v0.1.3.

Acaba de ocurrir un evento crítico que requiere
análisis inmediato fuera del horario estándar.

Por favor ejecuta el modelo completo enfocándote
en el evento disparador y su impacto sobre:

1. S2 — ¿Qué ocurrió exactamente? ¿Qué es verificable?
2. S1 — ¿Cómo están reaccionando las narrativas?
3. S3 — ¿Cuánto ruido está generando el evento?
4. S4 — ¿Cómo cambian los escenarios con este evento?
5. Señal de convergencia — ¿el evento estabiliza 
   o desestabiliza el sistema?

Al final genera los datos crudos en formato CSV
listos para copiar al repositorio.
```

---

## PROMPT DE SESIÓN OMITIDA — usar cuando no puedes correr el modelo

```
Registro de sesión omitida — Iran Conflict Model (ICM)
Sesión: [NÚMERO DE SESIÓN]
Fecha: [FECHA DE LA SESIÓN OMITIDA]
Tipo de sesión: OMITIDA
Motivo: [LABORAL / PERSONAL / SIN ACCESO / ENFERMEDAD]

Por favor genera únicamente la fila de 
convergencia.csv para esta sesión con 
todos los scores en NULL y el motivo registrado.
```

---

## Cómo numerar las sesiones

```
Sesión 01 → 2026-04-06 — diseño de arquitectura (ya ejecutada)
Sesión 02 → primera sesión operativa
Sesión 03 → segunda sesión operativa
... y así sucesivamente
```

La numeración es continua y nunca se reinicia. Las sesiones OMITIDAS también llevan número.

---

## Checklist antes de cada sesión

```
[ ] Tengo 20-30 minutos disponibles
[ ] Adjunté los 5 archivos de contexto
[ ] Reemplacé todos los campos entre corchetes [ ]
[ ] Es una sesión nueva — no continúo la del día anterior
[ ] Tengo el repositorio local actualizado (git pull)
```

---

*Prompt plantilla v0.1.3 — actualizar si cambia la arquitectura del modelo.*
