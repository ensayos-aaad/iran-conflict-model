# Estado del arte — análisis humano-IA, pronóstico y método

**Fecha:** 10 de octubre de 2026
**Alcance y límites:** no es una revisión sistemática (no siguió un protocolo tipo PRISMA). Las búsquedas fueron casi todas en inglés, así que probablemente falta literatura en español y latinoamericana. **Convención:** las referencias con enlace se verificaron en línea el 9–10 de octubre de 2026; las marcadas con **†** se citan de memoria y **deben verificarse** (ficha completa, año y revista) antes de usarlas en un texto académico.

---

## Mapa de líneas

| # | Línea | Pregunta que responde | Relación con el ICM/CEM |
|---|---|---|---|
| 1 | Pronóstico con modelos de lenguaje | ¿Puede la IA sola pronosticar? | Es la referencia contra la que compite el método |
| 2 | IA como asistente del pronosticador | ¿Mejora el humano con la IA? | Hipótesis de "amplificar el sentido común" |
| 3 | Complementariedad humano-IA | ¿Juntos rinden más que el mejor de los dos? | Pregunta central del diálogo |
| 4 | Sesgos de la interacción | ¿Cómo falla la colaboración? | Modos de falla vistos en el CEM y la S15 |
| 5 | Análisis de inteligencia y técnicas estructuradas | ¿Funcionan las reglas para no engañarse? | ANCHOR pertenece a esta familia |
| 6 | Marcos metodológicos | ¿Cómo se legitima académicamente? | Encuadre de la tesis |
| 7 | Niveles de automatización y estilos de colaboración | ¿Cuánto decide la máquina? | Ubicar cada fase del proyecto |
| 8 | Líneas de productos y de procesos | ¿Cómo se reutiliza y adapta un método? | ICM → CEM → seguimientos como familia |

---

## 1. Pronóstico con modelos de lenguaje

- **Halawi, Zhang, Chen y Steinhardt (2024).** *Approaching Human-Level Forecasting with Language Models.* NeurIPS 2024. Un sistema de búsqueda, razonamiento y agregación se acerca al agregado de pronosticadores competitivos humanos, y en un escenario relajado lo supera. [arXiv 2402.18563](https://arxiv.org/pdf/2402.18563)
- **Schoenegger, Tuminauskaite, Park y Tetlock (2024).** *Wisdom of the Silicon Crowd.* Science Advances. Un conjunto de 12 modelos, en 31 preguntas, es estadísticamente indistinguible de una multitud de 925 humanos. Ver la mediana humana mejora a los modelos, pero el promedio simple de humanos y máquinas fue aún más preciso. [PMC](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC11800985/)
- **ForecastBench (Karger y otros, Forecasting Research Institute).** Los superpronosticadores tienen un Brier ajustado de 0,081 frente a 0,101 del mejor modelo. Los modelos ya superan al público medio, y el instituto proyecta paridad hacia noviembre de 2026. [PDF Wharton](https://faculty.wharton.upenn.edu/wp-content/uploads/2026/02/ForecastBench_A_Dynamic_.pdf) · [FRI](https://forecastingresearch.substack.com/p/ai-models-have-likely-reached-parity)
- **Li, Li y Zhou (2026).** *When AI Navigates the Fog of War.* arXiv, marzo 2026. **Estudia el mismo conflicto de 2026** con 11 momentos críticos y 42 preguntas verificables, usando solo la información pública de cada momento. Los modelos razonan mejor en escenarios económicos y logísticos que en los políticos con muchos actores. No hay operador humano en el ciclo. **Es el comparador más directo del ICM.** [arXiv 2603.16642](https://arxiv.org/html/2603.16642v1)
- **Nemkova (2026).** *The Limits of LLM Forecasting: Parametric Knowledge Gaps Across Conflict Zones.* arXiv, mayo 2026. Diferencia de **224 veces** en la cobertura de los medios en inglés entre conflictos de 22 países. Los modelos "no pronostican el conflicto, lo categorizan". Una regresión logística con 11 variables les gana. [arXiv 2607.00018](https://arxiv.org/html/2607.00018)

**Para el ICM:** la IA sola ya es un competidor serio. Nemkova da sustento externo a la ceguera del modelo con las fuentes en español observada en la S14 y la S15 (pendiente P8).

## 2. La IA como asistente del humano

- **Schoenegger y otros (2025).** *AI-Augmented Predictions: LLM Assistants Improve Human Forecasting Accuracy.* ACM Transactions on Interactive Intelligent Systems. Experimento prerregistrado, N = 991: conversar con un asistente mejoró la precisión entre 24% y 28%, incluso con un asistente diseñado para dar consejos sesgados. [arXiv 2402.07862](https://arxiv.org/abs/2402.07862v1)

**Para el ICM:** apoya la hipótesis de amplificación, pero con personas sin experiencia, 6 preguntas y horizonte corto. No dice nada sobre un operador sostenido durante meses.

## 3. Complementariedad humano-IA

- **Vaccaro, Almaatouq y Malone (2024).** *When Combinations of Humans and AI Are Useful: A Systematic Review and Meta-Analysis.* Nature Human Behaviour. 370 resultados de 106 experimentos: **en promedio, la combinación rinde peor que el mejor de los dos por separado**, sobre todo en tareas de decisión. Funciona mejor en tareas creativas o generativas. [PMC](https://pmc.ncbi.nlm.nih.gov/articles/PMC11659167/) · [MIT Sloan](https://mitsloan.mit.edu/node/48565)
- † **Bansal y otros (2021).** *Does the Whole Exceed its Parts? The Effect of AI Explanations on Complementary Team Performance.* CHI 2021.

**Para el ICM:** el CEM coincide con esta literatura: en una decisión binaria, el mercado le ganó a la combinación. Si el diálogo tiene valor, estaría en la generación de hipótesis (abducción), no en el número final.

## 4. Cómo falla la colaboración

- † **Parasuraman y Manzey (2010).** *Complacency and Bias in Human Use of Automation.* Human Factors. Ya citado en el PROTOCOLO-ANCHOR.md.
- † **Buçinca, Malaya y Gajos (2021).** *To Trust or to Think: Cognitive Forcing Functions…* CSCW. Obligar a pensar antes de ver la respuesta de la IA reduce la dependencia excesiva.
- **Complacencia política de los modelos.** *Echoes of Agreement: Argument Driven Sycophancy in LLMs* (EMNLP Findings 2025): los modelos ajustan su postura a la del usuario, más cuanto más fuerte es su argumento. [ACL Anthology](https://preview.aclanthology.org/dashboard/2025.findings-emnlp.1241) · Síntesis: [TechPolicy Press](https://techpolicy.press/what-research-says-about-ai-sycophancy)
- **Dependencia excesiva de la IA generativa:** la fluidez del texto actúa como señal de confiabilidad. [arXiv 2509.08010](https://arxiv.org/pdf/2509.08010)

**Para el ICM/CEM:** la complacencia es una **hipótesis de mecanismo** para el error del CEM: el operador declaró preferir a Cepeda, y un modelo complaciente refleja esa postura. Se puede comprobar reetiquetando quién propuso cada variable.

## 5. Análisis de inteligencia y técnicas estructuradas

- † **Heuer (1999).** *Psychology of Intelligence Analysis.* CIA Center for the Study of Intelligence.
- † **Heuer y Pherson.** *Structured Analytic Techniques for Intelligence Analysis.* CQ Press (varias ediciones).
- **Chang, Berdini, Mandel y Tetlock (~2018).** *Restructuring Structured Analytic Techniques in Intelligence.* Intelligence and National Security. Las técnicas estructuradas no se han probado empíricamente: corregir un sesgo puede producir el opuesto, y no hay métricas para detectarlo. [Gobierno de Canadá](https://publications.gc.ca/site/eng/9.852936/publication.html) · [UT Austin](https://intelligencestudies.utexas.edu/?p=604)
- **CETaS / Instituto Alan Turing (2023).** *The Rapid Rise of Generative AI.* El dilema de la confianza en la IA dentro del ciclo de inteligencia. [PDF](https://cetas.turing.ac.uk/sites/default/files/2023-12/cetas_research_report_-_the_rapid_rise_of_generative_ai_-_2023.pdf)
- † **Tetlock (2005)** *Expert Political Judgment*; † **Tetlock y Gardner (2015)** *Superforecasting*; † **Mellers y otros (2014)**, Psychological Science (el torneo de Good Judgment).

**Para el ICM:** la crítica de Chang y otros cae directamente sobre ANCHOR, que son reglas sin métrica de corrección excesiva. El descuento adversarial fijo del 30% en el CEM es un ejemplo concreto: corrigió un sesgo sin calibración y resultó insuficiente.

## 6. Marcos metodológicos

- † **Hevner, March, Park y Ram (2004).** *Design Science in Information Systems Research.* MIS Quarterly.
- † **Peffers, Tuunanen, Rothenberger y Chatterjee (2007).** *A Design Science Research Methodology…* Journal of Management Information Systems.
- † **Yin.** *Case Study Research: Design and Methods* (varias ediciones). Estudio de caso múltiple.
- † **Whewell (1840)** *The Philosophy of the Inductive Sciences*; † **Wilson (1998)** *Consilience: The Unity of Knowledge*.
- † **Peirce.** La abducción como modo de inferencia (*Collected Papers*).
- † **Koestler (1964).** *The Act of Creation* (bisociación).
- † **Gentner (1983).** *Structure-Mapping: A Theoretical Framework for Analogy.* Cognitive Science.
- † **Pirolli y Card (2005).** *The Sensemaking Process and Leverage Points for Analyst Technology.* International Conference on Intelligence Analysis.
- † **Nosek y otros (2018).** *The Preregistration Revolution.* PNAS.
- **Autoetnografía con IA generativa:** investigadores que documentan su propia colaboración con ChatGPT. Se parece en el formato (diario reflexivo), pero no valida contra la realidad. [WCQR 2026](https://proceedings.science/wcqr-2026/papers/autoethnographic-reflexivity-in-collaboration-with-genai-the-co-construction-of?lang=en)

## 7. Niveles de automatización y estilos de colaboración

- † **Sheridan y Verplank (1978).** Escala de 10 niveles de automatización.
- † **Dell'Acqua y otros (2023).** *Navigating the Jagged Technological Frontier.* Harvard Business School, con BCG. "Centauros" (reparten tareas) frente a "cyborgs" (entrelazan cada paso), y la "frontera irregular" de capacidades de la IA.
- † **NIST AI Risk Management Framework (2023)** e **ISO/IEC 42001 (2023)**: marcos de gestión de riesgo y uso responsable.
- † **von Foerster.** Cibernética de segundo orden: el observador forma parte del sistema que observa.

## 8. Líneas de productos y de procesos

- **Pohl, Böckle y van der Linden (2005).** *Software Product Line Engineering: Foundations, Principles and Techniques.* Springer. [Springer](https://link.springer.com/book/10.1007/3-540-28901-1)
- **Kang, Cohen, Hess, Novak y Peterson (1990).** *Feature-Oriented Domain Analysis (FODA) Feasibility Study.* SEI. [DTIC](https://apps.dtic.mil/sti/pdfs/ADA235785.pdf)
- **Rombach (mediados de los 2000):** el concepto de *software process lines*, familias de procesos. Caso aplicado: la línea de procesos V-Modell XT (Kuhrmann y otros). [arXiv 1702.05724](https://arxiv.org/pdf/1702.05724) · [GI](https://dl.gi.de/items/b7af7f12-21a0-480f-a860-e32aa140a3c3/full)
- **Ingeniería de métodos situacional:** Brinkkemper (definición de la disciplina); Henderson-Sellers, Ralyté y otros, *Situational Method Engineering* (Springer). [Springer Professional](https://www.springerprofessional.de/situational-method-engineering/4189302) · [JUCS](https://www.jucs.org/jucs_16_3/situational_method_engineering_state.html)
- **Líneas de productos e IA reciente:** trabajos que usan modelos de lenguaje para apoyar líneas de productos, es decir, la dirección inversa a la de este proyecto. [ACM](https://doi.org/10.1145/3822455.3838767) · [arXiv 2604.20523](https://arxiv.org/pdf/2604.20523)

---

## Dónde encajan el ICM y el CEM

| Tipo de estudio | ¿Operador humano sostenido? | ¿Caso real en curso? | ¿Prerregistro contra la realidad? | ¿Registro auditable completo? |
|---|---|---|---|---|
| Pruebas automáticas (ForecastBench, Halawi) | No | Sí | Sí | Parcial |
| Experimentos de laboratorio (Schoenegger 2025) | Breve, sin experiencia | No | Sí | No |
| Caso retrospectivo (*Fog of War*) | No | Sí, mismo conflicto | Retrospectivo | Parcial |
| Autoetnografía con IA | Sí | No aplica | No | Variable |
| **ICM + CEM** | **Sí, meses** | **Sí, dos dominios** | **CEM sí; ICM desde oct 2026** | **Sí, git** |

**Hueco observado (no demostrado):** no se encontraron estudios que documenten un operador humano sostenido, con IA, sobre casos reales en curso, con registro auditable y falsación prerregistrada. Tampoco trabajos que traten **los protocolos de análisis humano-IA como una línea de procesos**. La búsqueda fue limitada.

## Lo que la literatura predice para el veredicto

1. **Como pronóstico, lo probable es perder** contra los mercados (CEM, Vaccaro) y quizá contra la IA sola (ForecastBench). No sería un fracaso del estudio, sino una confirmación de la literatura.
2. **Donde podría aportar:** generación y crítica de hipótesis, detección cruzada de errores, honestidad epistémica.
3. **Riesgos a medir:** complacencia del modelo, sesgo de cobertura (Nemkova) y corrección sin métrica (Chang y otros).

## Implicaciones para el diseño

- El brazo de "solo IA" del experimento A/B es imprescindible.
- Medir la complacencia: quién propuso cada tesis y si el modelo cambió de postura después de que opinara el operador.
- Usar *Fog of War* como comparador directo.
- Responder a Chang y otros con métricas de corrección excesiva o insuficiente.
