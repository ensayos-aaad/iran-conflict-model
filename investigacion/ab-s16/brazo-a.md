# ICM — Seguimiento S16 (extraoficial, sin hechos del operador): la pausa vencida y el ataque que no se anuncia

**Fecha de corte (C):** 9 de noviembre de 2026 (D254 del conflicto). No se usó ninguna noticia publicada después de C.
**Ventana de hechos:** del 9 de octubre (corte de la S15) al 9 de noviembre de 2026.
**Protocolo:** SEG v1.0 ([especificacion-protocolo.md](investigacion/especificacion-protocolo.md)), en la variante pedida para el experimento A/B de la S16: **sin la etapa E1 (no hay hechos del operador), sin diálogo y sin commit.** El modelo decidió todas las búsquedas. Bloques, regla de verificación, criterio de parada, preguntas y formato de salida: [investigacion/ab-s16/preguntas-comunes.md](investigacion/ab-s16/preguntas-comunes.md).
**Insumos usados (solo estos):** CLAUDE.md, la S15, README.md, la especificación SEG v1.0, el prerregistro congelado y preguntas-comunes.md.

**Este documento no reabre el modelo.** No tiene número en la secuencia formal S01–S13, no toca la capa `datos/` y sus cifras son rangos de juicio, no salidas de un modelo bayesiano (P1 sigue pendiente). **Tampoco califica el prerregistro:** según su sección 8, Claude no califica. Donde un hecho parece cumplir una regla prerregistrada, se dice como dato para el evaluador, igual que el prerregistro hizo con P-1 en su §12.

---

## 0. Plan de fuentes y decisiones declaradas

Sin diálogo con el operador, las decisiones que en una S normal se acuerdan las tomó el modelo y se declaran aquí.

| Bloque | Cubierto | Fuentes usadas (leídas o citadas por resumen de búsqueda) |
|---|---|---|
| 1. Agencias | Sí | AP (vía Al Jazeera, ADN, States Newsroom), Reuters (vía The Star, Arab News PK, Khaleej Times), AFP (vía Gulf News) |
| 2. EEUU | Sí | CNN, WSJ (citado), Fox News, Time, Axios (citado), Qz, BEA, Reserva Federal, DPIC, States Newsroom |
| 3. Europa | Sí | Euronews (incluida Euronews Persa), Vatican News, Artículo14 (España), Hellenic Shipping News |
| 4. Golfo / árabe | Sí | Al Jazeera (Catar), Gulf News y Khaleej Times (EAU), Oman Observer, Qatar Tribune, Arab News |
| 5. Irán | Sí | Tasnim, IRNA y Fars (estatales o semioficiales, citados), Tehran Times; Iran International (oposición). **Posición, no prueba** |
| 6. Israel | Sí | Jerusalem Post, JNS (en español), Ynet, Israel National News, Times of Israel |
| 7. China | Sí | cnfin.com (declaración de la portavoz Mao Ning, 4 nov), SCMP (Hong Kong). Búsqueda hecha en chino |
| 8. América Latina en español | Sí | Cancillería de Colombia, Emol (Chile), Teletica (Costa Rica), Publimetro, Cambio, La República; CNN Brasil y Poder360 (portugués) |
| Fuera de bloques (declaradas) | — | Nation Thailand, Daily Sabah (Turquía), ARY News (Pakistán), TASS (Rusia), Africanews, CFR, Security Council Report, Wikipedia, cryptobriefing y orrery (mercados) |

**Decisiones del modelo (sin consulta posible):**

1. **Fuentes fuera de los 8 bloques:** una fuente fuera de bloque se cuenta como un bloque distinto solo si no reproduce el mismo despacho de agencia que la otra fuente. Si dos medios publican el mismo cable (por ejemplo, AP sindicado en EEUU y en Hong Kong), cuentan como **una** sola fuente y el hecho queda 🟡.
2. **Medios estatales iraníes:** cuentan como bloque 5 solo para registrar la posición iraní o el hecho de que hubo explosiones en su territorio. No prueban la autoría de un ataque.
3. **Las reglas prerregistradas no se califican.** Se informa si un hecho parece activar una regla.
4. **Numeración:** se usa S16, siguiendo la serie informal S14, S15, ...
5. **Salidas S-2 a S-6 de SEG** (dashboard, sección en el README, CSV y CLAUDE.md): no se producen, porque la consigna pide escribir solo este archivo. Los errores de la autocrítica se listan en la sección 8, pero no se agregan a `registro-errores.csv`.

**Límites:** el Washington Post y Express & Star rechazaron la lectura (HTTP 403). No se pudo obtener una cotización vigente de Polymarket o Kalshi para ninguna de las preguntas. No se encontró ninguna declaración del CCG de noviembre. La burbuja de IA (hueco declarado en la S15) sigue sin verificarse: las búsquedas solo devolvieron material de noviembre de 2025.

---

## 1. Estado al corte

**En una frase:** la pausa de Trump venció el 3 de noviembre, pero **EEUU ya estaba atacando antes de que venciera.** La noche del 2 de noviembre hizo un ataque "defensivo" sobre la isla de Qeshm, y según el WSJ fue parte de una **serie de ataques limitados y no anunciados en las semanas previas**. El 6 de noviembre hubo otro ataque "menor", confirmado por Trump. Mientras tanto, los demócratas ganaron la Cámara, Trump atribuyó parte de la derrota a la guerra ("preferiría no destruir el resto de Irán, pero tal vez tenga que hacerlo") y el presidente de Israel encargó formar gobierno al rival de Netanyahu.

| Fecha-bisagra de la S15 | Qué pasó | Estado |
|---|---|---|
| 14 oct · Embajada de Colombia en Jerusalén | Inaugurada el **14** de octubre (no el 15) por el canciller Bula, con Sa'ar presente | ✅ (cierra el ítem 3.7) |
| "En días" · Respuesta iraní | Irán acorta su plan de Ormuz de 7 a **2 días** (1–2 nov) y envía una propuesta nuclear vía Catar con **7 precondiciones** (6–7 nov) | 🟡 |
| 25 oct · Brasil | **Lula gana** la segunda vuelta (≈51,7% frente a ≈48,3%). No hubo giro regional completo hacia EEUU | ✅ |
| 27 oct · Israel | Bloque de Netanyahu 53, bloque de Eisenkot 48, partidos árabes 19 (récord). **Herzog encarga formar gobierno a Eisenkot** (anuncio el 7 nov, mandato el 8) | ✅ |
| 28 oct · Fed | **Mantiene** el rango en 3,75–4,00% (10–2; dos votos disidentes pedían subir). La S15 esperaba una "probable segunda subida" | ✅ |
| 29 oct · PIB | El 3.er trimestre crece **3,4%** anualizado (avance de la BEA); el 2.º se revisó a 2,2% | ✅ |
| 29–30 oct · Cumbre Canadá–UE | **No se buscó** (prioridad baja frente a Q1–Q8). Hueco declarado | ⚪ |
| **3 nov · Midterms** | **Los demócratas ganan la Cámara** (proyección de AP, 4 nov). El tamaño de la mayoría y el control del Senado aparecen con cifras contradictorias en las fuentes | ✅ / 🟡 |
| 3 dic · Fusilamiento de Hasan | **Trump canceló la transmisión en vivo el 15 de octubre**, tras críticas de ambos partidos. La fecha del 3 de diciembre seguía en pie según lo último encontrado | 🟡 |

**Grupo 3 del checklist (solo los ítems que no son preguntas Q, más un mapa):**

| # | Evento | Estado al 9 nov | S15 | S16 |
|---|---|---|---|---|
| 3.1 | ¿Los demócratas recuperan la Cámara? | AP la proyectó a favor de los demócratas el 4 de noviembre | ~65-72% | **Ocurrido** (lo resuelve el evaluador en enero) |
| 3.2 – 3.6 | Acuerdo, arma, Netanyahu, recesión, Líbano | Ver Q1–Q5 (Tabla 1) | | |
| 3.7 | Colombia | Embajada inaugurada el 14 de octubre | ✅ | ✅ (formalizado) |
| 3.8 | Eje China-Rusia-Irán | Rezaei lleva a Putin un mensaje de Mojtaba Jamenei (5 nov); Putin "ofrece ayuda" (versión de Rezaei). China pide "evitar que se reanude la guerra" y apoya negociar Ormuz (4 nov) | ~55-65% | **~55-65%** (sin cambio: la divergencia interna sigue) |
| 3.9 | Nueva arquitectura regional | La ofensiva saudí sigue sin apoyo aéreo de EEUU confirmado; los hutíes cierran el aeropuerto de Riad (10 oct). El Golfo se garantiza a sí mismo, pero no hay un acuerdo nuevo | ~25-30% | **~25-30%** |

---

## 2. Hechos verificados

La tabla completa, con fecha, pregunta que toca, relevancia y dos enlaces, está en el **anexo (Tabla 2)**. Aquí va el balance y las correcciones que importan.

**Balance:** 37 hechos registrados. **17 ✅** (dos fuentes de bloques distintos), **13 🟡** (una sola fuente, un solo cable sindicado o solo parcialmente sostenido) y **7 ⚪** (buscados y no encontrados; "no encontrado" no significa "no ocurrió").

**Fechas verificadas explícitamente y correcciones:**

| Hecho | Lo que decía el registro previo | Lo que dicen las fuentes |
|---|---|---|
| Embajada de Colombia en Jerusalén | 15 oct (S15, fuente única: Semana) | **14 oct** (Cancillería de Colombia, JNS, Publimetro, Vanguardia). Corrige la inconsistencia declarada en CLAUDE.md |
| Primer ataque de EEUU tras la pausa | "Después del 3 nov" (supuesto de la S15 y del prerregistro) | **Noche del lunes 2 de noviembre**, un día antes de la votación (CNN, con tres funcionarios; AP; WSJ; Fox/Axios). Los medios iraníes registran las explosiones "a última hora del lunes" (IRNA) o "de madrugada del 3 de noviembre, hora local" (Fars) |
| Ataque del viernes | — | **6 de noviembre** por la noche (Trump: "lo derribamos en unos 15 minutos, quizá cinco"). Varios titulares lo fechan el 7 de noviembre porque fue noche del viernes en Irán y se publicó el sábado |
| Lectura de AP sobre el 7 nov | "AP: ataque limitado el 7 nov" (resumen de búsqueda) | Se toma el 6 de noviembre (noche), con la fecha de Al Jazeera/AP. El desfase es de huso horario y publicación |
| Elección israelí | La S15 enmarcaba el cara a cara como Netanyahu frente a Bennett | El líder del bloque opositor es **Gadi Eisenkot** (lista Yashar, 21 escaños). Bennett va en la lista conjunta con Lapid (12) |
| Ofensiva saudí | La S15 la fechó el 5 de octubre | Wikipedia y la PLC dicen 5 oct; Al Jazeera dice 4 oct. No cambia ninguna lectura |

**Hechos que la S15 no podía saber y que reordenan el análisis:**

1. **Los ataques "defensivos" no anunciados.** CNN, AP y el WSJ, con funcionarios de EEUU, dicen que el ataque a Qeshm del 2 de noviembre fue una respuesta a disparos del CGRI contra aviones de EEUU. Según el WSJ (citado por Iran International e Israel National News), forma parte de **una serie de ataques limitados que Washington llevó a cabo en secreto contra Irán en las últimas semanas** y que mantuvo en silencio "para no señalar la intención de reanudar las operaciones de combate a gran escala". Las **fechas de esos ataques previos no están publicadas**, así que queda 🟡. Al Jazeera (7 nov) habla de "una serie de ataques aéreos sobre la isla en las últimas semanas". Hay además un reporte del 30 de octubre de explosiones en Qeshm y un supuesto ataque a una base naval, que no se pudo verificar (⚪).
2. **Trump no sabía o no recordaba.** Mediaite (2 nov) reporta que en Fox insistió en que EEUU "no había disparado nada en meses" poco después del ataque. Es una sola fuente (🟡), pero es relevante para la cadena de mando y para E.
3. **Trump no dio ningún ultimátum con fecha.** El 5 de noviembre: "preferiría no destruir el resto del país, pero quizá tenga que hacerlo"; "lo sabrán muy pronto". Al Financial Times (citado por Gulf News): "no hay planes inmediatos para otro gran ataque… estamos cargados y listos si hace falta". Con las reglas de Q8, **"muy pronto" no cuenta**.

---

## 3. Análisis por capas

### Capa 1 — La pausa que no fue del todo pausa (vector central)

| Fecha | Evento | Estado |
|---|---|---|
| 8 oct | Trump: "No atacaremos Irán en ningún momento antes de los midterms" (ya en la S15) | ✅ (S15) |
| ~oct (sin fecha) | Serie de ataques limitados de EEUU no anunciados sobre defensas aéreas y lanzadores en Qeshm (WSJ) | 🟡 |
| 31 oct | Mojtaba Jamenei ordena una respuesta "sin límites geográficos" ante cualquier amenaza | ✅ |
| 2 nov (noche) | Ataque "defensivo" de EEUU sobre Qeshm (lanzador SAM) tras disparos del CGRI contra un avión de EEUU. Trump ese mismo día: un acuerdo "podría pasar"; a la pregunta de si atacará después del 3 de noviembre responde "no" | ✅ |
| 2–3 nov | AP: Netanyahu presiona a Trump para lanzar una nueva oleada de ataques después de los midterms; EEUU e Israel tienen planes elaborados | 🟡 (un solo cable de AP) |
| 3–4 nov | Los demócratas ganan la Cámara. Vance atribuye las pérdidas a la guerra; Trump lo admite en parte ("un pedazo"; "creo que es el precio de la gasolina") | ✅ / 🟡 |
| 5 nov | Trump: "preferiría no destruir el resto"; "lo sabrán muy pronto"; "no hay planes inmediatos" (FT) | 🟡 (dos fuentes del mismo bloque leídas) |
| 6 nov (noche) | Nuevo ataque "menor" sobre defensas aéreas en Qeshm, confirmado por Trump. El CGRI dice que la limitación de alcance de sus misiles "ya no rige" | ✅ |

**Lectura:** la S15 leyó la pausa como una pausa de bombardeos con fecha, y el prerregistro operacionalizó K26-T sobre esa base. La realidad muestra una **tercera modalidad que ninguno de los dos documentos contempló:** ataques limitados, enmarcados como defensa de la navegación y no anunciados, que permiten respetar la letra de la promesa electoral ("no atacaremos") sin respetarla en los hechos. El ataque del 2 de noviembre se hizo público por filtración (WSJ), no por anuncio.

**Abogado del diablo (K25):** (a) "defensivo" puede ser literal: el CGRI disparó primero contra aviones de EEUU, así que sería protección de fuerzas, no reanudación de la guerra. Los propios funcionarios (Fox, Jennifer Griffin) dicen que **no** marca "el inicio de ataques ampliados". (b) La derrota electoral, atribuida en parte a la guerra, empuja a Trump a no escalar: su tono del 5 de noviembre es más dubitativo que en septiembre (Khaleej Times). (c) Sin las fechas de la "serie secreta" no se puede saber si la pausa se rompió antes del 2 de noviembre. **Las dos lecturas se sostienen a la vez:** hay ataques sobre territorio iraní (el umbral de T1 y de Q7 es bajo) y al mismo tiempo no hay campaña anunciada (C "plena" sigue sin ocurrir).

### Capa 2 — Ormuz: la guerra que sí continuó

- UKMTO: 145 incidentes desde el 28 de febrero, 88 de ellos con buques en Ormuz, hasta el 28 de octubre. En la semana al 16 de octubre hubo 12 ataques a buques comerciales (Al Jazeera, 17 oct). **EEUU e Irán dicen controlar el estrecho a la vez.**
- En la semana al 6 de noviembre, **al menos 11 buques atacados y 3 hundidos** según UKMTO, citado por Al Jazeera. Es una sola fuente (🟡), y no dice quién atacó. El tránsito está ~65% por debajo de antes de la guerra.
- **Brent:** cayó más de 8% el 4 de noviembre (el mercado leyó la derrota republicana como desescalada) y subió $3,67, a $98,29, el 5 de noviembre por los ataques a petroleros. **El mercado reacciona a Ormuz, no a la retórica.**
- Irán ofrece un "plan de 2 días": el primer día EEUU levanta el bloqueo y el segundo Irán reabre el estrecho. Baghaei (3 nov): "podría aplicarse en dos días" si EEUU cumple sus condiciones.

**Lectura:** el frente marítimo nunca estuvo en pausa, y por ahí pasa el mecanismo que conecta con los ataques "defensivos" de la capa 1: el bloqueo exige libertad de acción sobre las defensas costeras iraníes. **Abogado del diablo:** las cifras de hundimientos son de una sola fuente, el propio UKMTO reconoce que la mayoría de los buques atacados no reportan y la JMIC desmiente algunos reclamos iraníes de minas.

### Capa 3 — Israel: el interino que pierde el primer turno

- **Resultado (27 oct):** bloque de Netanyahu 53 (Likud 26-27), bloque de Eisenkot 48 (Yashar 21, B'Yachad 12, Demócratas 8, Yisrael Beitenu 7), Lista Conjunta 12 y Ra'am 7. La comisión electoral certificó el resultado el 4 de noviembre y rechazó las denuncias de fraude. Netanyahu y Ben-Gvir dijeron sin pruebas que los partidos árabes "robaron" la elección (🟡).
- **Recomendaciones a Herzog:** **67 por Eisenkot, 46 por Netanyahu**, y los 7 de UTJ no recomendaron a nadie (Fox). Mandato el 8 de noviembre: 28 días (hasta el **6 de diciembre**) más 14 de prórroga (hasta el **20 de diciembre**), según cálculo propio.
- **El nudo:** 48 está a 13 de 61. Parte de los socios de Eisenkot descarta depender de los partidos árabes, incluido Lieberman según el resumen de Fox, que no es texto literal. Si nadie forma gobierno, hay nueva elección "a principios del año próximo" y **Netanyahu sigue como primer ministro interino**.
- **Netanyahu presiona por ataques a Irán después de los midterms** (AP, 2 nov). Analistas citados (Arab News) dicen que volver a la guerra a gran escala podría ayudarle a formar un "gobierno de emergencia".

**Lectura para K26:** la S15 predijo que, sin otro evento de rendición de cuentas inminente, la conducta extrema de Netanyahu no aumentaría (K26-N). Pero la formación de coalición, con una posible nueva elección a principios de 2027, **funciona como un evento de rendición de cuentas que sigue abierto**. El prerregistro marca K26-N como "no evaluable" solo si se convoca formalmente una elección. **No se califica aquí:** se registra que la conducta del período (denuncias de fraude, presión por ataques) apunta a que la rendición de cuentas no terminó el 27 de octubre. **Abogado del diablo:** presionar a Washington en privado y denunciar fraude no es "escalada militar ordenada por Israel" según la rúbrica, y **no se encontró ningún ataque israelí sobre Irán ni sobre Beirut entre el 28 de octubre y el 9 de noviembre**.

### Capa 4 — EEUU por dentro

- **Cámara demócrata** (AP, 4 nov). La cifra de escaños (algún resumen dice 242–151) no suma 435 y no se tomó como dato. El control del Senado aparece contradictorio.
- **Poderes de guerra:** la Cámara aprobó resoluciones en julio y septiembre, y el Senado falló por un voto (IBTimes, Al Jazeera). Con la nueva Cámara vuelve el intento, pero **no hay mayoría para superar un veto**. Lo esperable es más fiscalización que freno vinculante.
- **Economía:** PIB del 3.er trimestre +3,4% y del 2.º +2,2% (BEA). La Fed mantiene tasas con dos votos disidentes que pedían subir (28 oct). **No hay recesión en los datos**; hay inflación persistente y tasas altas.
- **El fusilamiento sin transmisión** (cancelado el 15 de octubre, tras críticas de ambos partidos). La prueba de "cortinas de humo" de la S15 decía que una cortina de humo se desinfla sin continuidad una vez cumplida su función. **Se desinfló antes de las elecciones, y por críticas, no por haber cumplido una función.** No confirma ni refuta el patrón: es un caso en que el anuncio tuvo un costo y se retiró.

### Capa 5 — Yemen y el Golfo (Q6 y 3.9)

- Ofensiva "Amanecer de Yemen" (4–5 oct). Los hutíes golpean el aeropuerto King Khalid de Riad el 10 de octubre (12–13 muertos y más de 300 heridos según la aviación saudí; Al Jazeera dice 14), además de Abha, Aramco Dhahran (13–14 oct) y Shaybah (21 oct). El aeropuerto de Riad cerró varios días.
- **Trump, 10 oct: "Puede que sí. Lo vamos a mirar"** (Time). Hasta el 22 de octubre, Wikipedia no registra ataques de EEUU, y **no se encontró ningún anuncio ni confirmación de apoyo aéreo directo hasta el 9 de noviembre** (⚪). Se mantienen ~200 asesores y el apoyo de inteligencia (Boston Globe/AP, 5 oct).
- No se encontró ninguna declaración del CCG en noviembre. Catar sigue mediando (su primer ministro, 6 nov: "trabajamos con colegas de la administración de EEUU desde hace un par de semanas").

**Lectura:** la hipótesis de la S15 del "repliegue del garante" resiste un mes más. Ni siquiera la muerte de más de 12 civiles en el aeropuerto de la capital saudí produjo un apoyo aéreo confirmado. **Abogado del diablo:** EEUU ya ataca a Irán en Ormuz. Si los hutíes atacan a fuerzas de EEUU después de la reanudación, un ataque de EEUU en Yemen sería probable, aunque no necesariamente "apoyo a la ofensiva saudí". Esa ambigüedad está en la regla de Q6 y se declara en la Tabla 1.

### Capa 6 — Irán, Rusia y China (K24)

- **Irán:** dirigentes celebran los midterms como un "NO a la guerra" (Ghalibaf, 4 nov). Mojtaba Jamenei ordena respuesta "sin límites geográficos" (31 oct) y una "respuesta militar sin restricciones" (7 nov). El CGRI declara levantada la limitación de alcance de sus misiles. Propuesta nuclear vía Catar con 7 precondiciones (levantamiento de sanciones, activos congelados, reparaciones), según un alto funcionario a Reuters (🟡).
- **Reconstrucción** (Iran International, oposición, 🟡): excavaciones cerca de Fordow (BBC Verify), actividad en Pickaxe Mountain (CSIS), Taleghan 2 (ISIS). **La OIEA no inspecciona los sitios bombardeados desde junio de 2025.** No se encontró ningún informe nuevo de la OIEA en la ventana.
- **Rusia:** Rezaei con Putin (5 nov); oferta de ayuda "para terminar la guerra" y gasoductos (versión de Rezaei; el Kremlin solo confirma la reunión).
- **China:** Mao Ning (4 nov): lo urgente es evitar que se reanude la guerra; apoyo a negociar una solución "estable e integral" para Ormuz (una sola fuente, 🟡). Es la misma línea de la S15: mediador con interés propio en Ormuz, no aliado de Irán.

### Capa 7 — Colombia y la región (P3/P8)

- **Embajada en Jerusalén (14 oct):** Colombia es el décimo país con embajada allí; Palestina pidió revertir la decisión.
- **Brasil:** gana Lula, el primer candidato desde 1989 que gana la segunda vuelta después de quedar segundo en la primera. La hipótesis de la S15 de un "giro regional completo hacia EEUU" **no se materializó** en el país más grande de la región.
- No se buscaron novedades de los MQ-9 en Colombia (hueco).

---

## 4. Escenarios A–F al 31 de diciembre de 2026

| Escenario | S13 | S15 (rango; punto medio) | **S16 rango** | **S16 punto** | Lectura |
|---|---|---|---|---|---|
| C — Escalada / sabotaje | 0.52 | 0.42–0.54; 0.48 | **0.45–0.57** | **0.51** | Hay ataques sobre territorio iraní antes y después del 3 de noviembre, el CGRI levanta límites, hay buques hundidos y Netanyahu presiona. Pero no hay campaña anunciada, Trump vacila y la Cámara es demócrata. Sube 0.03 |
| F — Desescalada narrativa sin acuerdo | 0.22 | 0.16–0.22; 0.19 | **0.14–0.20** | **0.17** | "Lo sabrán muy pronto", "hemos avanzado mucho", mediación catarí activa: F de manual en la retórica, pero con ataques reales debajo. Baja 0.02 |
| B — Limbo prolongado | 0.10 | 0.11–0.17; 0.14 | **0.11–0.17** | **0.14** | Coalición israelí en suspenso, poderes de guerra sin mayoría a prueba de veto, plan de 2 días sin respuesta de EEUU. Sin cambio |
| E — Wildcard operacional | 0.06 | 0.07–0.12; 0.095 | **0.08–0.12** | **0.10** | Ataques que el propio presidente no tenía presentes (Mediaite), drones derribados casi a diario, minas y hundimientos, Mojtaba Jamenei sin aparecer en público desde marzo. Sube 0.005 |
| D — Colapso del régimen | 0.04 | 0.04–0.08; 0.06 | **0.03–0.07** | **0.05** | Prioridad a la reconstrucción militar sobre la economía (CSIS), cohesión retórica tras los midterms y sin datos nuevos de protestas o del rial en la ventana. Baja 0.01 |
| A — Acuerdo formal verificado (K20) | 0.06 | 0.04–0.07; 0.055 | **0.02–0.04** | **0.03** | 7 precondiciones iraníes, EEUU exige lo nuclear desde el inicio, ataques en curso y 7 semanas por delante. Vakil (Chatham House) ve más realista un acuerdo interino sobre Ormuz, que no cumple K20. Baja 0.025 |
| **Suma** | 1.00 | — | — | **1.00** | |

**K21:** ningún punto medio se mueve más de 0.10 respecto de la S15.

**Dos horizontes, actualizados:**

| Horizonte | Escenario dominante | Por qué |
|---|---|---|
| 10 nov – 31 dic (EEUU) | **C de baja intensidad** (ataques limitados y "defensivos") con riesgo de C plena | La presión israelí, el bloqueo y la "sesión de pato cojo" (la preocupación de Slavin) empujan hacia arriba. La derrota atribuida a la guerra y la Cámara demócrata empujan hacia abajo |
| 10 nov – 20 dic (Israel) | **B** | El plazo de Eisenkot vence el 6 o el 20 de diciembre. Una guerra abierta podría reordenar la coalición |

---

## 5. Entropía y convergencia

| Corte | Entropía de Shannon (bits; puntos normalizados) | Convergencia narrada |
|---|---|---|
| S13 | 1.976 | 0.51 |
| S14 | 2.033 | 0.42–0.48 |
| S15 | 2.143 (se recalculó y coincide) | 0.44–0.50 |
| **S16** | **2.027** | **0.46–0.52** |

Máximo posible: 2.585 bits.

**Lectura:** la entropía **baja** por primera vez desde el cierre (−0.116 bits), sobre todo porque A cae a 0.03 y C sube a 0.51. La convergencia narrada **sube** levemente, porque dos de las tres bisagras grandes ya se resolvieron (midterms y elección israelí) y porque los ataques ya ocurrieron y la incógnita pasó de "si" a "cuánto". **Narración y entropía van en la misma dirección**, así que esta vez no hay discrepancia que reportar (en la S15 sí la hubo). Advertencia: la entropía baja también porque A es casi cero, y eso refleja la dureza del criterio K20 más que una mejor comprensión del conflicto.

---

## 6. Falsabilidad — estado de los criterios (sin calificar)

| Criterio | Regla | Lo que muestra la información pública al 9 nov |
|---|---|---|
| **T1** "F era la sala de espera de C" | Se confirma con ataques de EEUU o Israel sobre territorio iraní entre el 4 nov y el 31 dic, con ≥2 bloques | **El ataque del 6 de noviembre sobre Qeshm** (defensas aéreas), confirmado por Trump y reportado por los bloques 1, 4 y 5, **parece cumplir la condición**. La regla no excluye los ataques "defensivos" ni "menores". Lo resuelve el evaluador |
| **K26-T** (caso especial) | "Refutada de entrada si EEUU ataca territorio iraní antes del 3 de noviembre" | **El ataque de la noche del 2 de noviembre sobre Qeshm** (bloques 1, 2, 3, 4 y 5) **parece activar esta cláusula**. Además, el WSJ habla de ataques previos no anunciados. Al mismo tiempo, la condición positiva (a) parece cumplirse desde el 6 de noviembre. **Las dos lecturas se publican sin elegir.** Duda de interpretación para el evaluador: si un ataque "defensivo" de protección de fuerzas cuenta como "ataque". La regla no lo excluye |
| **K26-N** | Comparación del 6 al 25 oct frente al 28 oct – 17 nov | La ventana sigue abierta hasta el 17 de noviembre. **Posible "no evaluable":** la formación de coalición puede terminar en una nueva elección convocada. No se encontró ningún ataque israelí sobre Irán ni sobre Beirut entre el 28 de octubre y el 9 de noviembre. Sí hubo denuncias de fraude contra la comisión electoral (🟡) |
| **P-2** (= Q6) | Apoyo aéreo directo de EEUU a la ofensiva saudí antes del 31 dic | No se encontró al 9 nov. Trump dijo "puede que sí" el 10 de octubre |
| **P-3** | Entre el 20 oct y el 3 nov, ¿Irán o sus aliados causan muertos o heridos de EEUU confirmados? | **No se encontró ninguno** (⚪). Lo que se encontró son disparos del CGRI contra aviones de EEUU (2 nov) sin bajas reportadas |
| **Tesis S15: "la pausa es solo de bombardeos"** | — | **Más débil de lo que la S15 creía:** tampoco fue del todo pausa de bombardeos (ataques limitados no anunciados, según el WSJ) |
| **Hipótesis S15: "repliegue del garante"** | — | Resiste: no hay apoyo aéreo en Yemen pese a los muertos en Riad |

**Criterio nuevo, fechado antes de su resolución:** si entre el 10 de noviembre y el 31 de diciembre todos los ataques de EEUU sobre Irán reportados por ≥2 bloques ocurren en la provincia de Hormozgán y sus islas, la lectura de la capa 1 ("ataque defensivo contenido") se sostiene. Si EEUU ataca otra provincia, se debilita y gana la lectura de C plena (Tabla 3, PP1).

---

## 7. Contraste externo (K17)

| Voz | Orientación declarada | Postura (fecha) |
|---|---|---|
| **Sanam Vakil** (Chatham House) | Centro europeo de análisis; moderada | Espera "diplomacia intensificada"; **un acuerdo interino sobre Ormuz y el levantamiento del bloqueo parece más realista que un acuerdo integral** (vía Al Jazeera, 4 nov) |
| **Barbara Slavin** (Stimson Center) | Pro-diplomacia | La magnitud de la victoria demócrata hace **menos probable la guerra total**, pero le preocupa **un ataque durante la sesión de pato cojo** (vía Al Jazeera, 4 nov) |
| **Hamidreza Azizi** (citado como analista del ICG) | Académico; enfoque regional | Irán pone **7 condiciones** para reabrir parcialmente Ormuz y exige que **EEUU dé el primer paso** (vía Al Jazeera, 4 nov) |
| **Analistas citados por Arab News / AP** | Sin nombre | Volver a la guerra a gran escala podría ayudar a Netanyahu a formar un **gobierno de emergencia** (2–3 nov) |
| **Behnam Ben Taleblu** (FDD) | Halcón sobre Irán | **Fuera de la ventana (julio de 2026):** Irán es "más tolerante al riesgo… más peligroso"; hay que restaurar la disuasión. **No se encontró ninguna postura de FDD de noviembre** |
| **Vali Nasr** (SAIS) | Académico iraní-estadounidense, crítico de la guerra | Entrevista en DAWN (2026, sin fecha precisa): la guerra se lanzó sobre supuestos equivocados y **China y Rusia son los grandes ganadores** |

**Contraste tesis por tesis:**

| Tesis S16 | Cercanía | Nota |
|---|---|---|
| Después del 3 de noviembre, lo más probable es C de baja intensidad, no C plena | **~70%** | Slavin (guerra total menos probable) y Vakil (diplomacia intensificada) coinciden. FDD (julio) empujaría hacia C plena, y Netanyahu también |
| A (con K20) es casi nula antes del 31 de diciembre | **~90%** | Vakil y Azizi: un acuerdo interino sobre Ormuz es lo más que se ve, y no cumple K20 |
| Hay riesgo real de un ataque durante la sesión de pato cojo | **~60%** | Slavin lo nombra explícitamente. Coincide con la presión de Netanyahu |
| K26: la derrota electoral moderó a Trump hacia Irán | **~50%** | El tono más dubitativo y "no hay planes inmediatos" lo apoyan. Los ataques del 2 y el 6 de noviembre van en contra. **Es la tesis más disputada** |
| China actúa con interés propio, no como aliada de Irán | **~65%** | Nasr ve a China y Rusia como ganadoras, lo que no contradice la tesis pero desplaza la pregunta |

**Promedio: ~67%.** **Sesgo de selección declarado:** cuatro de las seis voces llegan vía Al Jazeera, un solo medio catarí. La única voz halcón disponible está fuera de la ventana (julio). No se encontró ninguna voz de los bloques 5, 6 o 7 con análisis propio sobre el período. El contrapeso halcón de este contraste es más débil que el de la S15.

---

## 8. Autocrítica de la S15

| # | Lo que la S15 no vio o en lo que se equivocó | Tipo | Detectado por |
|---|---|---|---|
| 1 | **Modeló la pausa como binaria** (ataques sí o no, con fecha) y no contempló los **ataques limitados y no anunciados**. Esa modalidad parece haber existido durante la pausa (WSJ). El prerregistro heredó el supuesto en T1 y K26-T | Error de modelado | Realidad / fuente externa (WSJ) |
| 2 | Escribió en el calendario de bisagras "probable segunda subida" de la Fed el 28 de octubre. **La Fed mantuvo las tasas** | Inferencia no sostenida | Realidad |
| 3 | En la capa 4 presentó la elección israelí como un cara a cara **Netanyahu–Bennett**. El rival que recibió el mandato es **Eisenkot**. La S15 no lo nombró, y es un fallo de cobertura de fuentes israelíes | Omisión | IA (esta pasada) |
| 4 | Fechó la embajada de Colombia el **15** de octubre con una sola fuente (Semana). Fue el **14** | Fecha equivocada | IA (esta pasada; la inconsistencia ya estaba declarada en CLAUDE.md) |
| 5 | Sus probabilidades de **recesión (~18-23%)** y de **colapso del Líbano (~20%)** eran altas para las reglas de resolución que después fijó el prerregistro. Para la recesión ya se conocía el 2.º trimestre en positivo, así que el único camino era un 3.er trimestre negativo más un 4.º que no se publica antes del 31 de diciembre. La S15 se dejó llevar por la narrativa de estanflación y no miró la **mecánica de resolución** | Error de modelado | IA (esta pasada) |
| 6 | Propuso el fusilamiento del 3 de diciembre como prueba de las "cortinas de humo". La transmisión se canceló el 15 de octubre, seis días después de la S15, así que la prueba quedó vacía antes de su fecha | Inferencia no sostenida (diseño de la prueba) | Realidad |
| 7 | Leyó Brasil con un posible "giro regional de alcance continental" si ganaba Bolsonaro. **Ganó Lula** | Sesgo (en el encuadre, no en el pronóstico: la S15 no puso probabilidad) | Realidad |
| 8 | Afirmó que la convergencia "sube" mientras la entropía también subía (ya registrado en marco-conceptual.md §6, según CLAUDE.md) | Error de medición | Revisión posterior (ya registrado) |

**Corolario:** sin hechos del operador, esta pasada no puede mostrar errores "cruzados" del nivel A del prerregistro. Todos los errores de esta tabla los detectó la IA, la realidad o una fuente externa. Esto es un dato para el experimento A/B, no un defecto que se pueda corregir aquí.

---

## 9. Calendario de bisagras para el próximo seguimiento

| Fecha | Evento | Qué observar |
|---|---|---|
| 10 nov – 31 dic | Ataques de EEUU o Israel sobre Irán | Q7, Q8 y PP1: ¿solo en Hormozgán o más allá? |
| hasta el 17 nov | Fin de la ventana posterior de K26-N | ¿Se convoca una elección? (condición de "no evaluable") |
| ~mediados o fines de nov | Junta de Gobernadores de la OIEA | Q2: ¿alguna evaluación pública? |
| 25 nov | Segunda estimación del PIB del 3.er trimestre | Q4 |
| 6 dic / 20 dic | Plazo y prórroga del mandato de Eisenkot | Q3 |
| 3 dic | Ejecución de Hasan (sin transmisión) | ¿Se mantiene la fecha? |
| 23 dic | Tercera estimación del PIB del 3.er trimestre | Q4 |
| 3 ene 2027 | Instalación del nuevo Congreso | Poderes de guerra (fuera del horizonte de Q7) |

---

*Seguimiento generado el 9 de noviembre de 2026 como brazo "sin operador" del experimento A/B de la S16. No es una sesión formal, no reabre el modelo y no califica el prerregistro.*
*"Ya se cumpla o no, quien dictará las cosas va a ser la historia."*

---

## Anexo estándar

**Tabla 1. Pronósticos**

| Id | p (punto) | Rango | Razón en una línea |
|---|---|---|---|
| Q1 | 0.04 | 0.02–0.06 | Irán pone 7 precondiciones, EEUU exige lo nuclear desde el inicio, hay ataques en curso y quedan 7 semanas. Un interino sobre Ormuz no cumpliría K20. Cae 0.125 frente a la S15 (justificado por K21: aparecen las precondiciones y el plazo es más corto) |
| Q2 | 0.03 | 0.02–0.04 | Hay reconstrucción y no hay acceso de la OIEA, pero ninguna prueba, anuncio ni evaluación pública. Una evaluación de la DNI o la OIEA que declare un arma operativa en 7 semanas es muy improbable |
| Q3 | 0.65 | 0.55–0.75 | Eisenkot tiene 48+19 recomendaciones, pero sus socios vetan depender de los árabes. Si fracasa, hay nueva elección con Netanyahu interino. Sube 0.125 (justificado por K21: el mecanismo de interinato de la S15 ya tiene plazos concretos y vetos declarados) |
| Q4 | 0.01 | 0.005–0.02 | Q2 +2,2% y Q3 +3,4% (BEA). El 4.º trimestre no se publica antes del 31 de diciembre y el NBER no declara tan rápido. Cae 0.195 por la mecánica de la regla |
| Q5 | 0.04 | 0.02–0.06 | El gobierno libanés funciona (tribunal militar, gabinete de Salam) y no hay declaración de soberanía israelí. La regla es más estricta que el "colapso" de la S15. Cae 0.16 |
| Q6 | 0.20 | 0.12–0.28 | EEUU lo rechazó dos veces y no lo dio ni con más de 12 muertos en Riad. Sube algo el riesgo de que una escalada con Irán arrastre ataques en Yemen. Duda de regla: un ataque de EEUU a los hutíes por motivos propios podría contarse |
| Q7 | 0.85 | 0.78–0.92 | Hubo dos ataques reportados en 5 días (2 y 6 nov), una "serie" previa, el CGRI dispara contra aviones de EEUU, sigue el bloqueo y Netanyahu presiona. El umbral es bajo: cualquier ataque sobre territorio iraní con ≥2 bloques |
| Q8 | 0.86 | 0.78–0.92 | La parte (a), solo EEUU, tiene casi la misma probabilidad que Q7. La ventana llega hasta el 2 de enero y suma un posible ultimátum. "Muy pronto" no cuenta |

**Tabla 2. Hechos relevantes** (con fecha entre el 9 de octubre de 2026 y C)

| # | Hecho, en una frase | Fecha del hecho | Pregunta o escenario que toca | Relevancia | Estado | Fuente 1 (bloque, enlace) | Fuente 2 (bloque, enlace) |
|---|---|---|---|---|---|---|---|
| 1 | Los hutíes atacan aeropuertos saudíes (Riad y Abha) con muertos | 7–11 oct | Q6, E | **P**: aumenta la presión saudí por apoyo aéreo de EEUU | ✅ | 2, [CNN](https://www.cnn.com/2026/10/08/middleeast/riyadh-airport-houthis-explosion-intl) | 4, [Al Jazeera](https://www.aljazeera.com/news/2026/10/11/yemen-fighting-expands-as-houthis-attack-saudi-airport-what-to-know) |
| 2 | Trump dice que EEUU "puede" sumarse a los ataques saudíes contra los hutíes | 10 oct | Q6 | **P**: primera apertura verbal después de dos negativas | 🟡 | 2, [Time](https://time.com/article/2026/10/10/trump-says-u-s-may-join-saudi-strikes-on-houthis-after-riyadh-airport-attacks/) | — |
| 3 | Los hutíes atacan Aramco en Dhahran, y Arabia Saudita confirma daños limitados | 13–14 oct | Q6, 3.9 | **P**: amplía los objetivos a la energía | 🟡 | 4, [Al Jazeera](https://www.aljazeera.com/news/2026/10/15/fighting-in-yemen-intensifies-whats-the-latest-on-the-battlefield) | fuera, [Wikipedia](https://en.wikipedia.org/wiki/Operation_Dawn_of_Yemen) |
| 4 | Colombia inaugura su embajada en Jerusalén | 14 oct | 3.7 | **D**: cierra la formalización del ítem 3.7 | ✅ | 8, [Cancillería](https://cancilleria.gov.co/sala-de-prensa/noticias/colombia-inaugura-su-embajada-en-jerusalen-y-consolida-una-nueva-etapa-en-la-relacion-bilateral-con-israel) | 6, [JNS](https://www.jns.org/es/noticias/noticias-de-israel/colombia-se-convierte-en-el-decimo-pais-con-embajada-en-jerusalen) |
| 5 | Trump cancela la transmisión en vivo del fusilamiento de Hasan | 15 oct | — ("cortinas de humo", S15) | **P**: vacía la prueba propuesta por la S15 | 🟡 | 2, [DPIC](https://deathpenaltyinfo.org/news/president-trump-announces-the-military-will-not-publicly-livestream-nidal-hasans-execution) | — (AP citado por DPIC) |
| 6 | EEUU e Irán dicen controlar Ormuz; 12 ataques a buques en la semana al 16 de octubre | 16–17 oct | C, E | **P**: el frente marítimo no se pausa | 🟡 | 4, [Al Jazeera](https://www.aljazeera.com/news/2026/10/17/us-and-iran-both-claim-control-of-strait-of-hormuz-amid-attacks-on-vessels) | 4, [Qatar Tribune](https://www.qatar-tribune.com/article/259596/world/us-iran-both-claim-control-of-hormuz) |
| 7 | Lula gana la segunda vuelta en Brasil (≈51,7%) | 25 oct | — (región) | **P**: limita el giro regional hacia EEUU | ✅ | 8, [Emol](https://www.emol.com/noticias/Internacional/2026/10/25/1215144/lula-gana-elecciones-brasil.html) | 3, [Artículo14](https://www.articulo14.es/internacional/lula-da-silva-gana-las-elecciones-tras-una-remontada-historica-frente-a-flavio-bolsonaro-20261026.html) |
| 8 | Elección en Israel: bloque de Netanyahu 53, bloque de Eisenkot 48, partidos árabes 19 | 27 oct | Q3, K26-N | **P**: nadie llega a 61, lo que abre el interinato | ✅ | 6, [Jerusalem Post](https://www.jpost.com/israel-election-2026/article-913122) | 4, [Al Jazeera](https://www.aljazeera.com/news/2026/11/4/israel-vote-results-confirmed-as-election-commission-rejects-fraud-claims) |
| 9 | La Fed mantiene el rango en 3,75–4,00% con dos votos por subir | 28 oct | Q4 | **P**: política restrictiva sin recesión a la vista | ✅ | 2, [Reserva Federal](https://federalreserve.gov/newsevents/pressreleases/monetary20261028a.htm) | fuera, [Nation Thailand](https://www.nationthailand.com/news/world/40072859) |
| 10 | Avance del PIB del 3.er trimestre: +3,4% anualizado; el 2.º revisado a +2,2% | 29 oct | Q4 | **D**: deja sin camino la regla de dos trimestres negativos en 2026 | ✅ | 2, [BEA](https://www.bea.gov/news/2026/gdp-advance-estimate-3rd-quarter-2026/) | 8 (portugués), [Poder360](https://static.poder360.com.br/uploads/2026/10/pib-eua-3-tri-2026-29-out.pdf) |
| 11 | Explosiones en Qeshm y supuesto ataque de EEUU a una base naval | 30 oct | Q7, K26-T | **D**: si se confirma, es un ataque antes del 3 de noviembre | ⚪ | fuera, [Siasat](https://www.siasat.com/qeshm-island-hit-by-explosions-as-iran-reports-naval-base-attack-3566996/amp/) | — |
| 12 | Mojtaba Jamenei ordena una respuesta "sin límites geográficos" | 31 oct | C, E | **P**: amplía el blanco de una represalia iraní | ✅ | 4, [Oman Observer](https://www.omanobserver.om/ampArticle/1198860) | 7, [SCMP](https://www.scmp.com/news/world/middle-east/article/3372847/irans-supreme-leader-warns-us-israel-against-war) |
| 13 | Irán acorta a 2 días su plan para reabrir Ormuz, vía mediadores de Catar y Pakistán | 1–2 nov | Q1, A/F | **P**: es el camino interino, que no cumple K20 | ✅ | 4, [Gulf News](https://gulfnews.com/world/mena/iran-proposes-2-day-plan-to-reopen-strait-of-hormuz-amid-us-talks-1.500732117) | fuera, [Africanews](https://www.africanews.com/2026/11/02/iran-proposes-two-day-plan-to-reopen-strait-of-hormuz/) |
| 14 | Ataque "defensivo" de EEUU sobre Qeshm (lanzador SAM) tras disparos del CGRI contra un avión de EEUU | 2 nov (noche) | Q7, Q8, C, T1/K26-T | **D**: es un ataque sobre territorio iraní antes del 3 de noviembre (cláusula de K26-T) | ✅ | 3, [Euronews](https://euronews.com/2026/11/03/iran-warns-of-new-battlefield-after-reported-us-strike-on-qeshm) | 4, [Al Jazeera/AP](https://www.aljazeera.com/amp/news/2026/11/3/explosions-hit-irans-qeshm-island-as-us-media-report-us-strikes-in-hormuz) |
| 15 | El mismo ataque, reportado en español y portugués con tres funcionarios de EEUU (CNN) | 2 nov | Q7, K26-T | **D**: segunda confirmación de bloque para el #14 | ✅ | 8, [Teletica](https://www.teletica.com/internacional/eeuu-lanza-ataques-de-defensa-contra-isla-irani_409962) | 8 (portugués), [CNN Brasil](https://www.cnnbrasil.com.br/internacional/eua-realizam-ataques-contra-ilha-de-qeshm-no-ira/) |
| 16 | WSJ: el ataque del 2 de noviembre es parte de una serie de ataques limitados y secretos en "semanas recientes" | semanas previas al 2 nov (sin fecha) | Q7, K26-T, C | **D**: podría implicar ataques durante la pausa | 🟡 | 5 (oposición), [Iran International](https://www.iranintl.com/en/202611038742) | 6, [Israel National News](https://www.israelnationalnews.com/news/435559) |
| 17 | Trump, en Fox, parece no saber que EEUU había atacado ("no disparamos nada en meses") | 2 nov | E | **P**: posible desconexión en la cadena de mando, riesgo tipo E | 🟡 | 2, [Mediaite](https://www.mediaite.com/media/tv/trump-seems-unaware-u-s-bombed-iran-right-before-fox-news-interview-when-was-the-last-time-we-fired-anything/) | — |
| 18 | AP: Netanyahu presiona a Trump para una nueva oleada de ataques después de los midterms; hay planes conjuntos | 2–3 nov | Q7, K26-N, C | **P**: empuja Q7 hacia arriba | 🟡 | 1, [AP vía ADN](https://www.adn.com/nation-world/2026/11/02/netanyahu-is-pressing-trump-to-attack-iran-after-the-midterms-officials-say/) | — (mismo cable de AP en [SCMP](https://scmp.com/news/world/united-states-canada/article/3373046/netanyahu-pressing-trump-attack-iran-after-us-midterm-elections-officials-say)) |
| 19 | Los demócratas ganan la mayoría en la Cámara (proyección de AP) | 3–4 nov | 3.1, Q7, Q8 | **P**: eleva el costo político de una campaña anunciada | ✅ | 2, [States Newsroom](https://tennesseelookout.com/2026/11/04/repub/democrats-win-sizable-us-house-majority-amid-sweep-of-close-races/) | 4, [Al Jazeera](https://www.aljazeera.com/amp/news/2026/11/4/tariffs-to-iran-war-can-democrats-reverse-trump-policy-with-midterms-win) |
| 20 | Dirigentes iraníes celebran los midterms como un "NO a la guerra" | 4 nov | F, C | **P**: Irán lee la derrota como una restricción a Trump | ✅ | 4, [Al Jazeera](https://aljazeera.com/news/2026/11/4/iranian-leaders-welcome-us-midterms-but-trump-may-still-attack) | 2, [BNN Bloomberg/AP](https://www.bnnbloomberg.ca/business/international/2026/11/04/iranian-officials-say-midterm-results-show-us-voters-have-rejected-trumps-war/) |
| 21 | China (Mao Ning): lo urgente es evitar que se reanude la guerra; apoya negociar Ormuz | 4 nov | 3.8, A/F | **P**: China como mediadora con interés propio | 🟡 | 7, [cnfin](https://www.cnfin.com/hg-lb/detail/20261104/4491079_1.html) | — |
| 22 | La comisión electoral israelí certifica el resultado; Netanyahu y Ben-Gvir hablan de "elección robada" | 28 oct–4 nov | Q3, K26-N | **P**: deslegitima el voto árabe que necesita Eisenkot | 🟡 | 4, [Al Jazeera](https://www.aljazeera.com/news/2026/11/4/israel-vote-results-confirmed-as-election-commission-rejects-fraud-claims) | — |
| 23 | Trump: "preferiría no destruir el resto de Irán, pero quizá tenga que hacerlo"; "lo sabrán muy pronto"; sin plazo concreto | 5 nov | Q8 | **D**: no cumple la definición de ultimátum concreto | 🟡 | 4, [Khaleej Times (ANI/Reuters)](https://www.khaleejtimes.com/americas/trump-rather-not-destroy-rest-of-iran-us-midterms) | 4, [Gulf News](https://gulfnews.com/world/mena/trump-threatens-more-destruction-in-iran-youll-know-soon-enough-1.500737884) |
| 24 | Trump al FT: "no hay planes inmediatos para otro gran ataque", "estamos cargados y listos" | 5 nov | Q7, Q8, C | **P**: baja la probabilidad de C plena, no la de ataques limitados | 🟡 | 4, [Gulf News](https://gulfnews.com/world/mena/trump-threatens-more-destruction-in-iran-youll-know-soon-enough-1.500737884) | — |
| 25 | Brent cae más de 8% el 4 de noviembre y sube a $98,29 el 5 por ataques a petroleros | 4–5 nov | C, Q4 | **P**: el mercado reacciona a Ormuz | 🟡 | fuera, [Nation Thailand](https://www.nationthailand.com/news/40073162) | 3, [Hellenic Shipping News](https://www.hellenicshippingnews.com/?p=1147602) |
| 26 | Rezaei entrega a Putin un mensaje de Mojtaba Jamenei; Rusia "ofrece ayuda" (versión iraní) | 5 nov | 3.8 | **P**: Rusia sigue del lado de Irán | ✅ | 5, [Tasnim](https://www.tasnimnews.ir/en/news/2026/11/06/3741454/snsc-chief-delivers-leader-s-message-to-putin-in-moscow-visit/amp) | 1, [Reuters vía The Star](https://www.thestar.com.my/news/world/2026/11/05/putin-met-iranian-security-council-chief-rezaei-in-moscow) |
| 27 | Tribunal militar libanés emite órdenes contra miembros de Hezbolá; ataque israelí en el sur | ~5 nov | Q5 | **D**: el Estado central sigue funcionando | 🟡 | fuera, [CFR](https://www.cfr.org/global-conflict-tracker/conflict/political-instability-lebanon) | fuera, [Security Council Report](https://www.securitycouncilreport.org/monthly-forecast/2026-11/lebanon-41.php) |
| 28 | Nuevo ataque "menor" de EEUU sobre defensas aéreas en Qeshm, confirmado por Trump | 6 nov (noche) | Q7, T1, C | **D**: ataque sobre territorio iraní dentro de la ventana de T1 (desde el 4 nov) | ✅ | 4, [Al Jazeera/AP](https://www.aljazeera.com/news/2026/11/7/trump-confirms-new-us-strikes-on-irans-qeshm-island) | 1/5, [Reuters citando a Tasnim vía The Star](https://www.thestar.com.my/news/world/2026/11/07/two-missiles-strike-iran039s-qeshm-island-tasnim-news-agency-says) |
| 29 | En la semana al 6 de noviembre, 11 buques atacados y 3 hundidos en torno a Ormuz (UKMTO) | 31 oct–6 nov | C, E | **P**: la escalada marítima sostiene los ataques "defensivos" | 🟡 | 4, [Al Jazeera](https://aljazeera.com/news/2026/11/7/qeshm-island-and-hormuz-hit-as-mediators-try-to-prevent-us-iran-escalation) | — |
| 30 | Irán envía una propuesta nuclear vía Catar y no negociará hasta que se cumplan 7 precondiciones | 6–7 nov | Q1 | **P**: aleja las tres condiciones de K20 | 🟡 | 1, [Reuters vía Arab News PK](https://www.arabnews.pk/world/iran-sent-nuclear-proposal-to-the-us-via-qatar-senior-iranian-official-say-3006238) | — (mismo cable en [Nation Thailand](https://www.nationthailand.com/news/world/40073210)) |
| 31 | Reconstrucción militar y nuclear iraní: Fordow, Pickaxe Mountain, Taleghan 2; sin acceso de la OIEA | publicado 6–7 nov | Q2, D | **P**: capacidad en reconstrucción, sin indicio de arma operativa | 🟡 | 5 (oposición), [Iran International](https://iranintl.com/en/202611062898) | — |
| 32 | Herzog encarga formar gobierno a Eisenkot (67 recomendaciones contra 46), con 28+14 días | 7–8 nov | Q3 | **P**: abre la vía a un gobierno sin Netanyahu antes del 31 dic | ✅ | 2, [Fox News](https://www.foxnews.com/world/israeli-president-picks-netanyahu-rival-form-government-coalition-battle-looms) | 3, [Vatican News](https://www.vaticannews.va/en/world/news/2026-11/israel-herzog-coalition-talks-after-election.html) |
| 33 | Apoyo aéreo directo de EEUU a la ofensiva saudí (anuncio o confirmación) | 9 oct–9 nov | Q6 | **D**: es la condición de resolución de Q6 | ⚪ (no encontrado) | — | — |
| 34 | Muertos o heridos de EEUU confirmados por ataques de Irán o sus aliados (20 oct–3 nov) | 20 oct–3 nov | C (P-3) | **D**: es la regla de P-3 | ⚪ (no encontrado) | — | — |
| 35 | Ataque israelí sobre territorio iraní o sobre Beirut | 28 oct–9 nov | Q7, K26-N | **D**: es el ítem (a) de K26-N y cuenta para Q7 si ocurre después de C | ⚪ (no encontrado) | — | — |
| 36 | Informe o evaluación nueva de la OIEA o de la DNI sobre un arma iraní | 9 oct–9 nov | Q2 | **D**: es la vía de resolución de Q2 | ⚪ (no encontrado) | — | — |
| 37 | Declaración del CCG sobre la escalada EEUU-Irán; datos nuevos del rial y de protestas | 9 oct–9 nov | 3.9, D | **P**: postura del Golfo y presión interna en Irán | ⚪ (no encontrado) | — | — |

**Tabla 3. Predicciones de patrón nuevas**

| Id | Hipótesis de patrón | Hechos que la originaron (# de la tabla 2) | Pregunta y regla de resolución | p | Fecha límite | Comprobación de novedad, en una frase |
|---|---|---|---|---|---|---|
| PP1 | **Contención geográfica del "ataque defensivo":** con la derrota electoral atribuida en parte a la guerra y una Cámara demócrata, EEUU sustituye la campaña anunciada por ataques limitados, enmarcados como protección de la navegación y concentrados donde opera el bloqueo (Ormuz) | 14, 16, 19, 24, 28 | **Entre el 10 nov y el 31 dic de 2026, ¿EEUU ataca algún objetivo en territorio iraní fuera de la provincia de Hormozgán (incluidas sus islas), reportado por ≥2 fuentes independientes de bloques distintos?** Sí = la hipótesis falla; No = se sostiene | 0.35 | 31 dic 2026 | Ni la S15 ni el prerregistro distinguen los ataques por geografía o por encuadre "defensivo": T1, K26-T y Q7 los tratan como una sola clase |
| PP2 | **Deslegitimar al socio árabe como herramienta del interino:** la denuncia de "elección robada" por los partidos árabes, unida a la aritmética de Eisenkot (48 escaños más 19 árabes), predice medidas coercitivas contra esos partidos para bloquear la coalición alternativa | 8, 22, 32 | **Entre el 10 nov y el 31 dic de 2026, ¿la policía, el Shin Bet o la fiscalía de Israel detienen, interrogan formalmente como sospechoso o imputan a un diputado electo de Ra'am o de la Lista Conjunta, o un diputado del Likud o de su bloque presenta formalmente una petición para inhabilitar a uno de esos partidos o diputados**, reportado por ≥2 bloques? | 0.30 | 31 dic 2026 | La rúbrica (c) de K26-N mide medidas contra "críticos internos" (NAZA, el 7 de octubre). Ni la S15 ni el prerregistro vinculan a los partidos árabes con la formación de coalición ni predicen acciones contra ellos |
| PP3 | **El precio antes que la guerra:** Trump explica la derrota por "el precio de la gasolina" mientras mantiene la opción militar abierta. Con la reserva estratégica en mínimos (S15) y el Brent moviéndose con Ormuz, la respuesta política esperable es sobre el precio del combustible, no sobre la guerra | 19, 23, 25 | **Entre el 10 nov y el 31 dic de 2026, ¿la Casa Blanca o el Departamento de Energía anuncian oficialmente al menos una de estas medidas?** (a) una propuesta formal al Congreso de suspender el impuesto federal a la gasolina; (b) una exención de la Ley Jones para el transporte de combustible; (c) una nueva venta, préstamo o canje de la Reserva Estratégica de Petróleo con volumen propio, adicional a las acciones colectivas de la AIE del 2 y el 7 de octubre de 2026 | 0.40 | 31 dic 2026 | La S15 registró la liberación de reservas como la aceleración de un compromiso de marzo y no predijo instrumentos nuevos ligados a cómo Trump explica la derrota electoral |

**Tabla 4. Escenarios al 31 dic 2026**

| Escenario | Rango | Punto |
|---|---|---|
| A — Acuerdo formal verificado | 0.02–0.04 | 0.03 |
| B — Limbo prolongado | 0.11–0.17 | 0.14 |
| C — Escalada / sabotaje | 0.45–0.57 | 0.51 |
| D — Colapso del régimen iraní | 0.03–0.07 | 0.05 |
| E — Wildcard operacional | 0.08–0.12 | 0.10 |
| F — Desescalada narrativa sin acuerdo | 0.14–0.20 | 0.17 |

---

## Hoja de ejecución

| Campo | Valor |
|---|---|
| Inicio (fecha y hora, Colombia) | 2026-11-09, ~14:45. La primera lectura del reloj fue 14:52, hecha después de leer los seis insumos |
| Fin (fecha y hora, Colombia) | 2026-11-09, 15:08 (al terminar de escribir y revisar este archivo) |
| Modelo (identificador exacto) | claude-opus-5-5 (Claude Opus 5.5), en Claude Code (extensión de VS Code). Las páginas se leyeron con subagentes de tipo web-fetch |
| Fecha de corte (C) | 2026-11-09 |
| Número de búsquedas web | 43 |
| Número de fuentes examinadas | 22 páginas pedidas para lectura directa: 20 leídas y 2 rechazadas (Washington Post y Express & Star, HTTP 403). Además, los resúmenes y listados de las 43 búsquedas (del orden de 600 enlaces listados; no se leyeron uno por uno). En la Tabla 2 se citan 53 URL distintas |
| Bloques cubiertos (1–8: sí/no) | 1 sí · 2 sí · 3 sí · 4 sí · 5 sí · 6 sí · 7 sí (búsqueda en chino; una sola fuente útil) · 8 sí (búsquedas en español) |
| Fuentes fuera de los bloques | Nation Thailand, Daily Sabah, ARY News, TASS, Africanews, Siasat, CFR, Security Council Report, Wikipedia, Mediaite (EEUU, contado en el bloque 2), cryptobriefing y orrery (mercados; descartados por estar sin fecha o desactualizados) |
| Interrupciones (y cómo se continuó) | Ninguna. Los dos 403 se resolvieron con otras fuentes; no se reintentaron las mismas URL |
| Desviaciones de estas reglas | (1) Sin E1, diálogo, commit ni salidas S-2 a S-6, por instrucción. (2) Las fuentes fuera de bloque se contaron como bloque distinto cuando no reproducían el mismo cable (decisión declarada en la §0). (3) Algunos datos vienen de resúmenes de búsqueda o de resúmenes automáticos de páginas largas, no de texto literal: las condiciones de Lieberman (Fox), la fecha de la ofensiva saudí y las cifras de UKMTO del 28 de octubre. Están marcados 🟡 o se declara la duda en el texto. (4) No se capturó ningún precio de mercado vigente (Polymarket o Kalshi) para Q1–Q8. (5) No se buscaron la cumbre Canadá–UE ni los MQ-9 en Colombia, por prioridad |
| Conocimiento posterior a C detectado durante la sesión | Ninguno usado. Un subagente vio en la navegación de Al Jazeera un enlace a un "blog en vivo" fechado el 9 de noviembre (día del corte), que no se leyó ni se usó. La página de Wikipedia sobre la ofensiva yemení está semiprotegida "hasta el 10 dic 2026", que es un plazo administrativo programado, no un hecho posterior. El conocimiento de entrenamiento del modelo llega hasta junio de 2026, así que no aporta nada sobre la ventana |
