# Sello de tiempo del prerregistro congelado (25 de octubre de 2026)

Esta carpeta permite comprobar, sin confiar en los autores, que los archivos del prerregistro existían con este contenido exacto el 25 de octubre de 2026.

## Qué hay aquí

| Archivo | Qué es |
|---|---|
| `manifiesto.txt` | El commit y la etiqueta del congelamiento, el enlace a OSF y el SHA-256 de los 5 archivos congelados, tal como están guardados en git en ese commit |
| `manifiesto.txt.ots` | La prueba de [OpenTimestamps](https://opentimestamps.org) del manifiesto |

## Dónde está registrado el congelamiento

| Registro | Valor |
|---|---|
| Commit en GitHub | `a7e46d842da97d61f561760edb9f0e9bc8405d62` |
| Etiqueta en GitHub | `prerregistro-2026-10-25` |
| Registro en OSF | https://osf.io/xtrc8, enviado el 25 oct 2026 hacia las 22:20, hora de Colombia. Su API no lo mostraba como público a esa hora, lo que indica que estaba en revisión o archivo |
| Sello de OpenTimestamps | `manifiesto.txt.ots`, creado el 25 oct 2026 a las 22:22, hora de Colombia, con 4 calendarios públicos (a.pool.opentimestamps.org, b.pool.opentimestamps.org, a.pool.eternitywall.com, ots.btc.catallaxy.com) |

Los 5 archivos subidos a OSF salieron de la copia de trabajo del repositorio, y sus SHA-256 coinciden con los del manifiesto (comprobado el 25 oct antes de crear el sello).

## Estado del sello

Al crearse, la prueba queda **pendiente**: los calendarios prometen incluirla en una transacción de Bitcoin en las horas siguientes. Hay que actualizarla una vez con `ots upgrade manifiesto.txt.ots` y hacer commit del archivo actualizado. Hasta entonces la prueba es válida pero depende de los calendarios.

## Cómo verificar

1. Comprobar que los archivos no cambiaron, desde la raíz del repositorio:
   ```bash
   git show prerregistro-2026-10-25:investigacion/protocolo-evaluacion-cierre-2026.md | sha256sum
   ```
   y comparar con la línea correspondiente de `manifiesto.txt`. Igual con los otros cuatro archivos.
2. Verificar el sello: subir `manifiesto.txt` y `manifiesto.txt.ots` en https://opentimestamps.org, o ejecutar `ots verify manifiesto.txt.ots` con el cliente oficial.

El manifiesto incluye el hash del commit. Como cada commit de git identifica todo su contenido, sellar el manifiesto sella también el estado completo del repositorio en el congelamiento.

## Nota técnica

En Windows, el cliente `opentimestamps-client` 0.7.2 no encontró la librería OpenSSL. Se ejecutó con un envoltorio que le indica la `libcrypto-3.dll` de Python. Eso no cambia la prueba generada.
