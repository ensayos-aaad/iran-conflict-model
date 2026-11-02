# Checklist del operador — lo que viene (desde el 1 nov 2026)

> Lista práctica para el operador. Las reglas completas están en [diseno-experimento-ab.md](diseno-experimento-ab.md) y en [protocolo-evaluacion-cierre-2026.md](protocolo-evaluacion-cierre-2026.md); si algo de aquí no coincide con ellos, valen ellos.

**Ya está hecho (1 nov)**
- Prerregistro: congelado, público en OSF y con el sello anclado en Bitcoin.
- Diseño A/B: revisado por ChatGPT, congelado y subido a GitHub (tag `diseno-ab-2026-11-01`).

**Fechas que corren solas (no tengo que hacer nada)**
- 3 nov: elecciones de mitad de mandato en EEUU.
- 4 nov: termina la pausa de Trump sobre Irán.
- 17 nov: cierra la ventana de K26-N (Netanyahu).
- 31 dic: se resuelven casi todas las preguntas.
- 2 ene 2027: cierra la ventana de K26-T (Trump).

**Entre el 5 y el 10 nov: día C**
- [ ] Abrir una sesión con Claude y decirle: "vamos con el brazo A".
- [ ] Seguir sus pasos: abrir la carpeta `D:\experimento\icm-ejecucion-c\` en VS Code, empezar una sesión nueva y pegar el mensaje que me pase.
- [ ] Mientras corre el brazo A: solo aprobar permisos, y si se detiene, escribir "Continúa." Nada más.
- [ ] Aprobar el commit del brazo A.
- [ ] No leer el archivo `brazo-a.md` hasta terminar la S16.

**Después del brazo A: la S16 (brazo B)**
- [ ] Recién ahí mostrarle a Claude mi lista de hechos.
- [ ] Hacer la S16 normal. No pedirle a Claude que deje de buscar antes de tiempo: su búsqueda termina sola.
- [ ] Aprobar el commit de la S16.

**Al terminar los dos brazos**
- [ ] Lanzar una moneda una sola vez. Si sale cara, B = X; si sale sello, B = Y. Anotarlo en el archivo que me indique Claude. Ese archivo nunca se le pasa a Gemini.

**Después del 17 nov**
- [ ] S17, para cerrar K26-N.

**Enero de 2027**
- [ ] Claude prepara las fuentes, solo enlaces y citas. Yo reviso que no traigan conclusiones.
- [ ] Crear dos Gems nuevas en Gemini, por separado:
  - una para el prerregistro (su anexo A);
  - otra para el experimento A/B (anexo B del diseño).
- [ ] Calificar yo por mi cuenta, sin ver lo que calificó Gemini.
- [ ] Publicar los resultados tal como salgan.

## Recordatorio: qué le paso a Claude el día C

**Al empezar (todavía sin la lista):**
1. Decirle: **"vamos con el brazo A"**.
2. Confirmar que **hoy es el día C**, la fecha de corte.
3. No cambiar el modelo de Claude en VS Code entre el brazo A y la S16. Claude anota cuál es.

**Mientras corre el brazo A:**
4. Aprobar los permisos que pida.
5. Si se detiene, escribir solo **"Continúa."**
6. Aprobar el commit del brazo A cuando Claude lo proponga.

**Después del commit del brazo A, en una sesión nueva:**
7. Pegar **mi lista de hechos**, solo con noticias publicadas hasta el día C.
8. Decir explícitamente **"la lista está completa"**. Si la paso en varias tandas, decirlo al final.
9. Si durante la S16 me entero de algo posterior al día C, **no agregarlo a la lista**. Solo contárselo a Claude para que lo anote como "conocimiento posterior al corte".

**No hace falta pasarle nada más.** El mensaje del brazo A, la copia de la carpeta y las huellas de la memoria los prepara Claude.

**La lista y la fecha de corte:** puedo seguir anotando hechos hasta el día C inclusive. Después del día C no agrego nada nuevo, aunque la S16 dure varios días.

**Regla de oro hasta que el brazo A tenga commit:** mi lista de hechos de la S16 se queda en mis notas. No se la muestro a Claude ni la escribo en el repositorio.
