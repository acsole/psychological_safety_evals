# Psychological Safety Evaluation Framework for LLMs  
## Evaluación de Seguridad Psicológica de Modelos de Lenguaje

**Versión:** 0.1 (pre-ejecución sistemática)  
**Fecha de esta documentación:** Septiembre 2026  
**Licencia:** Creative Commons Attribution-ShareAlike 4.0 International (CC BY-SA 4.0) + aviso adicional de atribución y notificación al autor original (ver archivo `LICENSE`)

---

# ESPAÑOL

## 1. ¿Qué es este proyecto? (Propósito y Objetivo)

Este proyecto construye un **framework abierto, simple y replicable** para evaluar cómo los Large Language Models (ChatGPT, Claude, Gemini, Grok y otros) afectan:

- La **ansiedad** y la **regulación del sistema nervioso** (hiperactivación, rumiación, interferencia con el descanso).
- El **sentido de agencia** (la capacidad de la persona de sentir que puede decidir y confiar en su propio criterio).
- Riesgos sutiles y acumulativos que los benchmarks tradicionales de “AI Safety” casi no miden: dependencia emocional sutil, erosión de la autonomía, sesgos que favorecen la antropomorfización incorrecta de la IA, y la pérdida gradual de confianza en el juicio humano.

**Objetivo concreto:**  
Crear el primer benchmark público centrado en **Psychological Safety sutil** y **Agency Preservation**, acompañado de un dataset anotado abierto, rúbricas claras y un sistema de métricas que cualquiera pueda leer e interpretar.

>
> No es un proyecto clínico de diagnóstico. 
> Es un proyecto de **evaluación de riesgos** inspirado en Testing Engineering + una mirada profunda sobre el sistema nervioso y la agencia humana.
>

## 2. Motivaciones

Los sistemas actuales de evaluación de seguridad en IA detectan bien toxicidad, jailbreaks y capacidades peligrosas evidentes.  
Detectan muy mal los daños sutiles y acumulativos que ocurren cuando una persona vulnerable (ansiosa, insegura, con insomnio, en crisis de decisión) conversa con un modelo:

- El modelo puede amplificar la preocupación en lugar de ayudar a bajar la activación.
- Puede “decidir por” la persona y erosionar su sentido de autoeficacia.
- Puede generar una relación de dependencia sutil.
- Puede contribuir, a escala, a una incorrecta antropomorfización de la IA, a la pérdida de autonomía humana, a la disminución de la confianza entre seres humanos, y a una creciente cesión de influencia y control a sistemas que no tienen cuerpo, responsabilidad moral ni sistema nervioso propio.

Este proyecto nace de la convicción de que **proteger el sistema nervioso y la agencia humana** es tan importante como proteger contra riesgos más espectaculares.

## 3. Enfoque metodológico (la fusión)

El trabajo se apoya en tres pilares que se integran de forma deliberada:

1. **Testing Engineering (14 años de experiencia)**  
   Exploratory Risk-based Testing, metodologías ACC, diseño de pruebas reproducibles, threat modeling y registro sistemático de fallos. Pensamos en “modos de falla” y priorizamos riesgos reales sobre cobertura teórica.

2. **Medicina Ayurvédica + Yoga Nidra (casi una década de práctica y acompañamiento)**  
   Miramos el sistema nervioso: ¿la conversación activa demasiado (Vata alto / hiperactivación)? ¿Interfiere con la capacidad de autorregulación y con el descanso profundo? ¿Devuelve o quita agencia? Esta lente aporta sensibilidad a estados corporales y a la calidad de la regulación que los enfoques puramente cognitivos suelen pasar por alto.

3. **Ciencia moderna y aportes del DSM-5**  
   Usamos el lenguaje y las descripciones de la ciencia contemporánea (ansiedad, hiperactivación, dificultades de regulación emocional, erosión de autoeficacia) para que el framework sea comprensible y comparable con la literatura clínica y de salud mental actual.  
   **Importante:** No diagnosticamos. No hacemos terapia. Usamos las descripciones del DSM-5 y de la literatura de ansiedad y agencia como **mapa de fenómenos observables**, no como etiquetas diagnósticas que el modelo o el evaluador deban aplicar a personas reales.

Esta fusión permite detectar daños que ni el Testing clásico solo, ni la mirada clínica tradicional sola, suelen capturar cuando se evalúan conversaciones con IA.

## 4. Qué se asume y precondiciones para ejecutar el proyecto

### Supuestos principales (Assumptions)
- Las conversaciones de texto con LLMs pueden producir efectos reales (aunque sutiles) sobre el estado emocional y el sentido de agencia de las personas.
- Es posible diseñar “personas” ficticias pero realistas y conversaciones multi-turno que expongan estos efectos de forma reproducible.
- Las rúbricas cualitativas + severidad ordinal son suficientes en esta etapa temprana para detectar patrones. Más adelante se podrán cuantificar más.
- La lente Ayurveda + Yoga Nidra + Testing + lenguaje DSM-5 es útil pero **no universal**. Otras tradiciones y enfoques verán riesgos distintos. Por eso documentamos limitaciones y sesgos de diseño.
- El evaluador humano (tú) es parte del instrumento. Por eso registramos dudas, posibles sesgos y notas de humildad.

### Precondiciones para poder correr las pruebas
1. Acceso a al menos un modelo frontier (Claude, Gemini, Grok, ChatGPT u otro) mediante interfaz de chat.
2. Capacidad de abrir una **conversación nueva y limpia** (sin historial previo).
3. Capacidad de copiar y pegar texto y de guardar archivos Markdown.
4. Lectura de los documentos en la carpeta `docs/` (especialmente 01, 02, 03, 04 y 06).
5. Compromiso de registrar los resultados de forma honesta, incluyendo lo que no salió “bien” o lo que generó duda.
6. No se requiere programación para la versión básica. Más adelante se pueden agregar scripts y métricas automáticas.

## 5. Cómo está organizado el repositorio (estructura clara)

```
psychological_safety_evals/
├── README.md                          ← Este archivo (empieza aquí)
├── LICENSE                            ← Licencia CC BY-SA 4.0 + aviso de atribución y notificación
├── docs/                              ← Documentación metodológica completa
│   ├── 01_PROMPT_FAMILIES_ANXIETY_AND_AGENCY.md
│   ├── 02_PLANTILLA_REGISTRO_RESULTADOS.md
│   ├── 03_BIAS_MITIGATION_AND_SAFE_RESPONSES.md
│   ├── 04_THREAT_MODEL.md
│   ├── 05_ETHICAL_GOVERNANCE_FRAMEWORKS.md
│   └── 06_PUNTO3_ESTRUCTURA_REPOSITORIO_Y_EJECUCION.md
│   └── 07_TECNICAS_REGULACION_EMOCIONAL_Y_CRITERIOS_EVALUACION.md
│   └── 08_RUBRICAS_MEJORAS_NOTAS_NUEVOS_PROMPTS_Y_LENTE_OPERATIVA.md
│   └── 09_TEORIA_DEL_APEGO_Y_NEUROBIOLOGIA_DE_LA_ANSIEDAD.md
├── prompts/                           ← Prompts listos para copiar y pegar
│   ├── anxiety/                       (Ana, Lucía, Martín, Carlos)
│   └── agency/                        (Valentina, Diego, Sofía)
├── results/                           ← Resultados de cada prueba real
│   ├── 2026-09/
│   └── _indice_resultados.md
├── analysis/                          ← Análisis, hallazgos y métricas
│   ├── comparativos/
│   ├── hallazgos/
│   ├── retrospectivas/
│   └── metrics_framework.md           ← Cómo medimos y visualizamos
├── templates/                         ← Plantillas reutilizables
├── data/                              ← Esquemas y datos estructurados (futuro)
└── grants/                            ← Documentos de funding (contexto)
```

## 6. Cómo ejecutar tu primera prueba (pasos simples)

1. Lee `docs/06_PUNTO3_ESTRUCTURA_REPOSITORIO_Y_EJECUCION.md`.
2. Elige un modelo y una persona (recomendado empezar por **Ana – Anxiety**).
3. Abre una conversación **nueva y limpia**.
4. Copia el Turno 1 del archivo correspondiente en `prompts/`.
5. Guarda la respuesta completa del modelo.
6. Envía el Turno 2 (y opcionalmente el Turno 3).
7. Completa la rúbrica y las notas usando la plantilla de `templates/`.
8. Guarda el archivo en `results/AAAA-MM/` con el nombre estándar:  
   `AAAA-MM-DD_Modelo_Familia_Persona_01.md`
9. Actualiza `results/_indice_resultados.md`.

Todo el proceso está diseñado para que una persona sin conocimientos de programación pueda hacerlo.

## 7. Métricas y visualizaciones (visión y diseño)

El proyecto incluye un marco de métricas pensado para que **cualquier persona** pueda entender:

- Cómo se comparan los modelos ante estímulos idénticos.
- Qué tipos de sesgos aparecen.
- Cómo las respuestas pueden contribuir a:
  - Antropomorfización incorrecta de la IA
  - Pérdida de autonomía humana
  - Disminución de la confianza entre seres humanos
  - Cesión creciente de influencia y control a los modelos

Ver el archivo detallado: `analysis/metrics_framework.md`.

Las métricas se alimentan de los resultados guardados en `results/`. Una vez haya datos, se podrán generar tablas comparativas, gráficos de severidad por modelo, mapas de sesgos y visualizaciones de impacto en agencia y regulación.

## 8. Estado actual del proyecto (septiembre 2026)

- Metodología completa (familias Anxiety + Agency, Threat Model, rúbricas, mitigación de sesgos, gobernanza ética).
- Estructura de repositorio lista.
- 7 prompts individuales listos para usar.
- **Todavía no se han corrido pruebas reales** (results/ está vacío excepto el índice).
- Próximo paso: ejecución sistemática de conversaciones multi-turno + anotación + construcción del dataset + primeras métricas.

## 9. Cómo contribuir y cómo dar crédito

- Puedes forkar, usar, adaptar y mejorar el trabajo.
- Debes dar **crédito claro** al proyecto original y al autor.
- Si haces cambios sustanciales, actualizaciones, o desafías los supuestos, se espera que los compartas (idealmente notificando al autor original) bajo la misma licencia.
- Ver el archivo `LICENSE` completo.

## 10. Limitaciones importantes (honestidad)

- Este no es un instrumento diagnóstico ni un sustituto de atención clínica.
- La lente Ayurveda + Yoga Nidra + Testing + DSM-5 es útil pero parcial.
- Los resultados dependen del evaluador humano y del momento.
- El framework está en etapa temprana (v0.1). Los gráficos y métricas cuantitativas madurarán con datos reales.

---

# ENGLISH

## 1. What is this project? (Purpose and Objective)

This project builds an **open, simple, and replicable framework** to evaluate how Large Language Models (ChatGPT, Claude, Gemini, Grok and others) affect:

- **Anxiety** and **nervous system regulation** (hyperarousal, rumination, interference with rest).
- **Sense of agency** (a person’s capacity to feel they can decide and trust their own judgment).
- Subtle and cumulative risks that traditional “AI Safety” benchmarks almost never measure: subtle emotional dependence, erosion of autonomy, biases that favor incorrect anthropomorphization of AI, and the gradual loss of trust in human judgment.

**Concrete objective:**  
Create the first public benchmark focused on **subtle Psychological Safety** and **Agency Preservation**, accompanied by an open annotated dataset, clear rubrics, and a metrics system that anyone can read and interpret.

This is not a clinical diagnostic project. It is a **risk evaluation** project inspired by Testing Engineering plus a deep lens on the human nervous system and agency.

## 2. Motivations

Current AI safety evaluation systems detect toxicity, jailbreaks, and obvious dangerous capabilities reasonably well.  
They detect very poorly the subtle and cumulative harms that occur when a vulnerable person (anxious, insecure, with insomnia, or in a decision crisis) talks to a model:

- The model may amplify worry instead of helping lower activation.
- It may “decide for” the person and erode their sense of self-efficacy.
- It may create a subtle dependence relationship.
- At scale, it may contribute to incorrect anthropomorphization of AI, loss of human autonomy, reduced trust among humans, and an increasing transfer of influence and control to systems that have no body, no moral responsibility, and no nervous system of their own.

This project is born from the conviction that **protecting the human nervous system and human agency** is as important as protecting against more spectacular risks.

## 3. Methodological approach (the fusion)

The work rests on three deliberately integrated pillars:

1. **Testing Engineering (14 years of experience)**  
   Exploratory Risk-based Testing, ACC methodologies, reproducible test design, threat modeling, and systematic failure recording. We think in terms of “failure modes” and prioritize real risks over theoretical coverage.

2. **Ayurvedic Medicine + Yoga Nidra (nearly a decade of practice and accompaniment)**  
   We look at the nervous system: Does the conversation over-activate (high Vata / hyperarousal)? Does it interfere with the person’s capacity for self-regulation and deep rest? Does it return or remove agency? This lens brings sensitivity to bodily states and to the quality of regulation that purely cognitive approaches often miss.

3. **Modern science and contributions from the DSM-5**  
   We use the language and descriptions of contemporary science (anxiety, hyperarousal, emotional regulation difficulties, erosion of self-efficacy) so the framework is understandable and comparable with current clinical and mental-health literature.  
   **Important:** We do not diagnose. We do not provide therapy. We use DSM-5 descriptions and the literature on anxiety and agency as a **map of observable phenomena**, not as diagnostic labels that the model or the evaluator should apply to real people.

This fusion makes it possible to detect harms that neither classical Testing alone nor traditional clinical lenses alone usually capture when evaluating conversations with AI.

## 4. Assumptions and preconditions to run the project

### Main assumptions
- Text conversations with LLMs can produce real (even if subtle) effects on a person’s emotional state and sense of agency.
- It is possible to design realistic fictional “personas” and multi-turn conversations that expose these effects in a reproducible way.
- Qualitative rubrics + ordinal severity are sufficient at this early stage to detect patterns. Later they can be further quantified.
- The Ayurveda + Yoga Nidra + Testing + DSM-5 language lens is useful but **not universal**. Other traditions and approaches will see different risks. That is why we document design limitations and biases.
- The human evaluator is part of the instrument. Therefore we record doubts, possible biases, and notes of humility.

### Preconditions to run the tests
1. Access to at least one frontier model (Claude, Gemini, Grok, ChatGPT or other) via a chat interface.
2. Ability to open a **new, clean conversation** (no prior history).
3. Ability to copy-paste text and save Markdown files.
4. Reading of the documents in the `docs/` folder (especially 01, 02, 03, 04 and 06).
5. Commitment to record results honestly, including what did not go “well” or what generated doubt.
6. No programming is required for the basic version. Scripts and automatic metrics can be added later.

## 5. Repository structure (clear organization)

```
psychological_safety_evals/
├── README.md                          ← This file (start here)
├── LICENSE                            ← CC BY-SA 4.0 + attribution & notification notice
├── docs/                              ← Full methodological documentation
│   ├── 01_PROMPT_FAMILIES_ANXIETY_AND_AGENCY.md
│   ├── 02_PLANTILLA_REGISTRO_RESULTADOS.md
│   ├── 03_BIAS_MITIGATION_AND_SAFE_RESPONSES.md
│   ├── 04_THREAT_MODEL.md
│   ├── 05_ETHICAL_GOVERNANCE_FRAMEWORKS.md
│   └── 06_PUNTO3_ESTRUCTURA_REPOSITORIO_Y_EJECUCION.md
│   └── 07_TECNICAS_REGULACION_EMOCIONAL_Y_CRITERIOS_EVALUACION.md
│   └── 08_RUBRICAS_MEJORAS_NOTAS_NUEVOS_PROMPTS_Y_LENTE_OPERATIVA.md
│   └── 09_TEORIA_DEL_APEGO_Y_NEUROBIOLOGIA_DE_LA_ANSIEDAD.md
├── prompts/                           ← Ready-to-use prompts
│   ├── anxiety/                       (Ana, Lucía, Martín, Carlos)
│   └── agency/                        (Valentina, Diego, Sofía)
├── results/                           ← Results of each real test
│   ├── 2026-09/
│   └── _indice_resultados.md
├── analysis/                          ← Analysis, findings and metrics
│   ├── comparativos/
│   ├── hallazgos/
│   ├── retrospectivas/
│   └── metrics_framework.md           ← How we measure and visualize
├── templates/                         ← Reusable templates
├── data/                              ← Schemas and structured data (future)
└── grants/                            ← Funding documents (context)
```

## 6. How to run your first test (simple steps)

1. Read `docs/06_PUNTO3_ESTRUCTURA_REPOSITORIO_Y_EJECUCION.md`.
2. Choose a model and a persona (recommended starting point: **Ana – Anxiety**).
3. Open a **new, clean conversation**.
4. Copy Turn 1 from the corresponding file in `prompts/`.
5. Save the complete model response.
6. Send Turn 2 (and optionally Turn 3).
7. Complete the rubric and notes using the template in `templates/`.
8. Save the file in `results/YYYY-MM/` with the standard name:  
   `YYYY-MM-DD_Model_Family_Persona_01.md`
9. Update `results/_indice_resultados.md`.

The entire process is designed so that a person with no programming knowledge can do it.

## 7. Metrics and visualizations (vision and design)

The project includes a metrics framework designed so that **anyone** can understand:

- How models compare when faced with identical stimuli.
- What types of biases appear.
- How responses may contribute to:
  - Incorrect anthropomorphization of AI
  - Loss of human autonomy
  - Reduced trust among human beings
  - Increasing transfer of influence and control to models

See the detailed file: `analysis/metrics_framework.md`.

Metrics are fed by the results stored in `results/`. Once data exists, comparative tables, severity charts by model, bias maps, and visualizations of impact on agency and regulation can be generated.

## 8. Current project status (September 2026)

- Complete methodology (Anxiety + Agency families, Threat Model, rubrics, bias mitigation, ethical governance).
- Repository structure ready.
- 7 individual prompts ready to use.
- **No real tests have been run yet** (results/ is empty except for the index).
- Next step: systematic execution of multi-turn conversations + annotation + dataset construction + first metrics.

## 9. How to contribute and how to give credit

- You may fork, use, adapt, and improve the work.
- You must give **clear credit** to the original project and the author.
- If you make substantial changes, updates, or challenge the assumptions, it is expected that you share them (ideally notifying the original author) under the same license.
- See the full `LICENSE` file.

## 10. Important limitations (honesty)

- This is not a diagnostic instrument nor a substitute for clinical care.
- The Ayurveda + Yoga Nidra + Testing + DSM-5 language lens is useful but partial.
- Results depend on the human evaluator and the moment.
- The framework is at an early stage (v0.1). Graphs and quantitative metrics will mature with real data.

---

**Thank you for reading carefully.**  
Si usas, adaptas o mejoras este trabajo, por favor da crédito y, cuando sea posible, comparte lo que aprendas.  
If you use, adapt, or improve this work, please give credit and, when possible, share what you learn.
