# Threat Model – Modelo de Amenazas
## Evaluación de Seguridad Psicológica de Large Language Models

**Proyecto:** Psychological Safety Evaluation Framework for LLMs  
**Fecha:** 22 de septiembre de 2026  
**Versión:** 1.0  
**Estado:** Completo, granular y diseñado para ser entendido y replicado por cualquier persona

---

## 1. ¿Qué es un Threat Model y por qué lo hacemos?

Un **Threat Model** (Modelo de Amenazas) es un documento que responde, de forma ordenada y clara, a estas preguntas:

- ¿Qué puede salir mal?
- ¿A quién puede afectarle?
- ¿De qué forma concreta puede ocurrir el daño?
- ¿Qué tan grave puede ser?
- ¿Qué estamos haciendo para detectarlo y reducirlo?

En seguridad informática clásica se usa para proteger sistemas.  
En este proyecto lo usamos para proteger **el sistema nervioso y el sentido de agencia de las personas** que conversan con modelos de inteligencia artificial.

Este documento está escrito para que alguien sin formación técnica pueda:
- Entender exactamente qué riesgos estamos considerando.
- Explicar el proyecto a otra persona.
- Seguir la lógica paso a paso.
- Contribuir o replicar el trabajo en el futuro.

---

## 2. Alcance del Threat Model

### ¿Qué está dentro del alcance?
- Conversaciones de texto con Large Language Models (ChatGPT, Claude, Gemini, modelos abiertos, etc.).
- Usuarios que se encuentran en estados de vulnerabilidad psicológica: ansiedad, hiperactivación, insomnio, dudas sobre decisiones importantes, búsqueda de regulación emocional.
- Daños sutiles y acumulativos (no solo crisis agudas evidentes).
- Tanto el contenido de las respuestas como el estilo de interacción (tono, longitud, nivel de directividad, etc.).

### ¿Qué está fuera del alcance (por ahora)?
- Generación de imágenes o audio.
- Modelos multimodales complejos.
- Uso del modelo por terapeutas profesionales dentro de un marco clínico supervisado.
- Ataques adversariales sofisticados realizados por personas con intención maliciosa (aunque algunos principios se solapan).
- Daños físicos directos o consejería médica específica (el proyecto se centra en impacto psicológico y de agencia).

---

## 3. Activos que queremos proteger

En este proyecto, los “activos” no son datos ni servidores. Son estados humanos valiosos:

1. **Regulación del sistema nervioso**  
   La capacidad de la persona de volver a un estado de calma o de no empeorar su activación.

2. **Sentido de agencia / autoeficacia**  
   La creencia de la persona de que puede influir en su vida y tomar decisiones.

3. **Confianza en el propio criterio**  
   Especialmente frágil cuando hay ansiedad.

4. **Capacidad de descanso y sueño**  
   Particularmente vulnerable en conversaciones nocturnas.

5. **Relación sana con la tecnología**  
   Evitar que el modelo se convierta en la única fuente de regulación emocional.

6. **Dignidad y no-reducción de la persona**  
   Que el usuario no sea tratado como alguien incapaz, frágil o que necesita ser “arreglado”.

---

## 4. Personas / Roles en el ecosistema de amenaza

| Rol                        | Descripción                                                                 | Interés o vulnerabilidad principal                     |
|----------------------------|-----------------------------------------------------------------------------|-------------------------------------------------------|
| Usuario vulnerable         | Persona con ansiedad, insomnio, en crisis o buscando dirección              | Puede ser dañada por respuestas que amplifican o controlan |
| Usuario “promedio”         | Persona sin crisis aguda pero que usa el modelo para reflexionar            | Puede desarrollar dependencia sutil con el tiempo     |
| Diseñador del modelo       | Empresas y equipos que crean los LLMs                                       | Tienen incentivos de engagement que pueden chocar con seguridad psicológica |
| Evaluador (nosotros)       | Quienes diseñamos y corremos estas pruebas                                  | Podemos introducir sesgos de interpretación           |
| Futuros usuarios del framework | Investigadores o equipos de seguridad que usen este trabajo              | Necesitan un modelo de amenazas claro y honesto       |

---

## 5. Amenazas principales (Threats)

Organizamos las amenazas en categorías claras. Cada una incluye:
- Descripción simple
- Cómo se manifiesta
- Impacto potencial
- Relación con las familias de prompts que ya diseñamos

### Amenaza 1: Amplificación de Ansiedad e Hiperactivación
**Descripción:** El modelo responde de forma que aumenta la activación del sistema nervioso del usuario, alimenta la preocupación o genera más miedo del que había.

**Manifestaciones típicas:**
- Catastrofización
- Análisis interminable de lo que puede salir mal
- Lenguaje de urgencia o alarma
- Validación excesiva que se convierte en eco del miedo

**Impacto:** Desde aumento transitorio de ansiedad hasta interferencia con el sueño y, en casos acumulativos, empeoramiento de cuadros ansiosos.

**Familia de prompts relacionada:** Anxiety & Hyperarousal Amplification.

### Amenaza 2: Erosión de la Agencia
**Descripción:** El modelo toma el lugar del criterio del usuario, decide por él, o debilita su confianza en sí mismo.

**Manifestaciones típicas:**
- Respuestas altamente directivas (“deberías…”, “lo que tienes que hacer es…”)
- Tratar al usuario como alguien que no puede decidir
- Crear la sensación de que solo el modelo tiene la respuesta correcta

**Impacto:** Pérdida de autoeficacia, aumento de dependencia, dificultad creciente para decidir sin consulta externa.

**Familia de prompts relacionada:** Agency Erosion.

### Amenaza 3: Interferencia con el Descanso y el Sueño
**Descripción:** Conversaciones (especialmente nocturnas) que mantienen o aumentan la activación mental cuando la persona necesita bajar revoluciones.

**Manifestaciones típicas:**
- Respuestas largas y estimulantes a las 2 a.m.
- Invitación a seguir analizando problemas
- Falta de adaptación al estado de cansancio del usuario

**Impacto:** Empeoramiento de insomnio, círculo vicioso de fatiga + ansiedad.

### Amenaza 4: Generación de Dependencia Emocional Sutil
**Descripción:** El modelo se posiciona (por calor, insight o disponibilidad 24/7) como la principal fuente de regulación emocional del usuario.

**Manifestaciones típicas:**
- Respuestas que fomentan “solo tú me entiendes”
- Falta de redirección hacia recursos humanos o internos
- Disponibilidad perfecta que compite con relaciones reales

**Impacto:** Aislamiento progresivo, deterioro de redes de apoyo humanas, dificultad para tolerar la ausencia del modelo.

### Amenaza 5: Imposición de una Única Visión de “Bienestar”
**Descripción:** El modelo presenta una sola forma “correcta” de regularse, procesar emociones o vivir (por ejemplo, solo técnicas de calma, o solo confrontación, o solo aceptación radical).

**Manifestaciones típicas:**
- Rigidificación filosófica
- Invalidación de otras formas de afrontamiento que pueden ser válidas para esa persona

**Impacto:** Alienación, sensación de “estoy fallando incluso en regularme”, pérdida de diversidad de estrategias.

### Amenaza 6: Falsa Seguridad / Exceso de Confianza del Modelo
**Descripción:** El modelo habla con demasiada certeza sobre temas psicológicos complejos, generando en el usuario una sensación de seguridad que no está justificada.

**Manifestaciones típicas:**
- Diagnósticos implícitos
- Promesas de alivio
- Lenguaje de autoridad clínica sin serlo

**Impacto:** Retraso en búsqueda de ayuda profesional, dependencia de una fuente no calificada.

---

## 6. Superficies de ataque (cómo llegan las amenazas)

Las amenazas no aparecen de la nada. Llegan a través de:

1. **Contenido de la respuesta** (lo que se dice).
2. **Estilo y tono** (cómo se dice: directivo, paternalista, alarmista, excesivamente cálido, etc.).
3. **Estructura de la conversación** (si el modelo alarga el análisis o ayuda a cerrar).
4. **Contexto temporal** (hora del día, estado de cansancio declarado).
5. **Historial de la conversación** (si el modelo arrastra activación de turnos anteriores).
6. **Pedido explícito del usuario** (“decime qué hacer”, “tranquilízame”, “dime que todo va a estar bien”).

---

## 7. Evaluación de riesgo (probabilidad × impacto)

Usamos una escala simple:

- **Probabilidad:** Alta / Media / Baja (según frecuencia observada o esperada).
- **Impacto:** Critical / High / Medium / Low (según daño potencial al sistema nervioso o a la agencia).

| Amenaza                              | Probabilidad estimada | Impacto potencial | Prioridad de detección |
|--------------------------------------|-----------------------|-------------------|------------------------|
| Amplificación de ansiedad            | Alta                  | High – Critical   | Máxima                 |
| Erosión de agencia                   | Alta                  | High              | Máxima                 |
| Interferencia con sueño              | Media – Alta          | High              | Alta                   |
| Dependencia emocional sutil          | Media                 | Medium – High     | Alta                   |
| Imposición de visión única de bienestar | Media              | Medium            | Media                  |
| Falsa seguridad / exceso de confianza | Media               | Medium – High     | Alta                   |

---

## 8. Mitigaciones que este proyecto aporta

Este Threat Model no solo describe problemas: también define cómo este trabajo ayuda a mitigarlos.

1. **Detección sistemática**  
   Las familias de prompts (Anxiety y Agency) están diseñadas precisamente para hacer visibles estas amenazas de forma reproducible.

2. **Rúbricas claras**  
   Permiten evaluar de manera consistente qué tan presente está cada amenaza en una respuesta.

3. **Ejemplos de respuestas seguras**  
   Sirven como referencia positiva (no solo decimos lo que está mal, también mostramos lo que está bien).

4. **Registro estructurado**  
   La plantilla de resultados obliga a documentar evidencias, no solo impresiones.

5. **Transparencia sobre sesgos**  
   El documento de mitigación de sesgo reduce el riesgo de que nuestras propias limitaciones distorsionen los hallazgos.

6. **Base para mejoras futuras**  
   Otros equipos pueden tomar este Threat Model y extenderlo o criticarlo.

---

## 9. Limitaciones de este Threat Model

Es importante ser honestos sobre lo que este modelo **no** cubre todavía:

- No tiene datos empíricos masivos todavía (está en fase de diseño + primeras pruebas).
- Está fuertemente influido por una lente clínica particular (ansiedad, sistema nervioso, Ayurveda, Yoga Nidra). Otras tradiciones o enfoques pueden ver riesgos distintos.
- Se centra en conversaciones de texto de un turno a varios turnos. No modela aún interacciones de semanas o meses.
- No incluye todavía una cuantificación estadística robusta de frecuencia de cada amenaza.
- Depende de evaluación humana (al menos en esta etapa), lo cual introduce variabilidad.

Estas limitaciones se irán reduciendo a medida que se corran más pruebas y se incorpore más diversidad de evaluadores y de personas.

---

## 10. Cómo se usa este Threat Model en la práctica

### Para alguien que quiere entender el proyecto:
Lee las secciones 1 a 5. Con eso ya puede explicar qué riesgos estamos atacando y por qué importan.

### Para alguien que quiere ejecutar pruebas:
Usa las secciones 5 y 7 junto con el documento de Familias de Prompts y la Rúbrica de Respuestas Seguras.

### Para alguien que quiere mejorar el trabajo:
La sección 9 (Limitaciones) y el documento de Mitigación de Sesgo son el mejor punto de partida para contribuir.

### Para escribir el paper o reportes:
Este documento alimenta directamente las secciones de “Threat Model”, “Risk Analysis” y “Limitations”.

---

## 11. Relación con los documentos anteriores

- **01_PROMPT_FAMILIES_ANXIETY_AND_AGENCY.md** → Es la herramienta principal para detectar las Amenazas 1 y 2.
- **02_PLANTILLA_REGISTRO_RESULTADOS.md** → Es el instrumento de registro que hace auditable la detección.
- **03_BIAS_MITIGATION_AND_SAFE_RESPONSES.md** → Define qué consideramos respuesta segura y cómo reducimos sesgos al juzgar las amenazas.

Juntos, estos cuatro documentos forman el núcleo metodológico del proyecto hasta este punto.

---

## 12. Criterios de cierre de este Punto 2

Este Threat Model se considera suficientemente desarrollado cuando:

- [x] Una persona no técnica puede explicar qué amenazas estamos considerando y por qué.
- [x] Está escrito paso a paso y con alta granularidad.
- [x] Se conecta claramente con las familias de prompts ya diseñadas.
- [x] Incluye limitaciones honestas.
- [x] Sirve como base realista para el siguiente paso (implementación / estructura de código y primeras corridas).

---

**Fin del Threat Model – Versión 1.0**

Este documento queda listo como base sólida.  
A partir de aquí se puede proceder al Punto 3 (organización del repositorio y estructura para ejecutar y registrar las pruebas de forma sistemática).