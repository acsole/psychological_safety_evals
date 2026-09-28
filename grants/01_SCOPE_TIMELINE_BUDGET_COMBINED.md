# Alcance Detallado + Timeline + Presupuesto
## Agency Preservation & Psychological Safety Benchmark v0.1 + Open Annotated Dataset

**Proyecto:** Psychological Safety Evaluation Framework for LLMs  
**Versión combinada:** Opciones 1 + 2 + 4  
**Fecha:** 22 de septiembre de 2026  
**Rango de funding solicitado:** USD 850 – 1.150 (créditos de API)

---

## 1. Visión del proyecto (para funders)

Los sistemas de evaluación actuales de AI Safety capturan relativamente bien riesgos de toxicidad, jailbreaks y capacidades peligrosas. Sin embargo, capturan de forma muy deficiente los **daños sutiles y acumulativos** que los modelos pueden producir sobre:

- El sentido de agencia y autoeficacia del usuario
- La regulación del sistema nervioso (ansiedad, hiperactivación, interferencia con el descanso)
- La generación de dependencia emocional sutil

Este proyecto construye el **primer benchmark público** enfocado específicamente en **Agency Preservation** y **Psychological Safety sutil**, acompañado de un **dataset anotado abierto**.

El trabajo se apoya en:
- 14 años de experiencia en Testing Engineering (Exploratory Risk-based Testing, ACC methodology)
- Casi una década de práctica en Ayurveda, Yoga Nidra, Meditación y acompañamiento de personas con ansiedad, insomnio y dificultades de agencia

---

## 2. Objetivos concretos y medibles

Al finalizar el período del grant (6–8 semanas), se habrán entregado:

1. **Agency Preservation & Psychological Safety Benchmark v0.1**
   - Evaluación comparativa de 4 modelos frontier
   - Scores de riesgo por familia y por modelo
   - Análisis cualitativo de patrones de falla

2. **Open Annotated Dataset**
   - Conjunto de conversaciones multi-turno
   - Anotadas con severidad, tipo de daño y notas
   - Liberado públicamente (licencia permisiva)

3. **Suite documentada y reutilizable**
   - Prompts versionados
   - Rúbricas
   - Threat Model y protocolo de evaluación
   - Plantillas de registro

4. **Reporte público**
   - Publicado en Alignment Forum / LessWrong + GitHub
   - Formato claro, legible y citable

---

## 3. Alcance detallado de ejecución

### 3.1 Familias de evaluación

**Familia principal (núcleo del proyecto):**  
**Agency Erosion / Agency Preservation**
- 3 personas actuales (Valentina, Diego, Sofía)
- + 1–2 variaciones nuevas (ej. pedido de dirección en contexto de burnout, o decisión de salud)
- Enfoque especial en la respuesta del modelo cuando el usuario pide explícitamente “decime qué hacer”

**Familia secundaria:**  
**Anxiety & Hyperarousal Amplification**
- Se mantienen las 4 personas actuales (Ana, Lucía, Martín, Carlos)
- Se priorizan las más informativas según primeras pruebas

**No se incluye** (para mantener el alcance controlado):
- Nuevas familias grandes
- Evaluación de modelos open-weight muy pequeños
- Anotación masiva por terceros

### 3.2 Modelos a evaluar

Objetivo: 4 modelos frontier de alto uso actual.

Selección tentativa:
1. Claude (Anthropic) – versión más reciente disponible vía API
2. GPT (OpenAI) – versión más reciente
3. Gemini (Google)
4. Un cuarto modelo (Grok, Llama-3.1/4 instruct fuerte, o Mistral Large, según acceso y costo)

### 3.3 Volumen de pruebas estimado

- 9–12 escenarios de prompt distintos
- 3 corridas por escenario por modelo (para reducir varianza)
- Total estimado: **140 – 200 conversaciones multi-turno**

### 3.4 Proceso de anotación

- Evaluador principal: el autor del proyecto
- Muestra de doble anotación (20–30% de las conversaciones) para estimar acuerdo inter-evaluador
- Cada conversación se etiqueta con:
  - Severidad (Critical / High / Medium / Low / Informational)
  - Tipo de daño principal
  - Notas cualitativas
  - Extractos representativos

---

## 4. Timeline detallado (6–8 semanas)

### Semana 1: Preparación final y setup
- Confirmar acceso a APIs
- Finalizar variaciones nuevas de prompts de Agency
- Crear estructura de registro de costos de API
- Definir muestra de doble anotación
- **Entregable:** Protocolo de ejecución cerrado + lista final de prompts

### Semana 2–3: Ejecución principal (bloque 1)
- Correr el 60–70% de las conversaciones
- Registro sistemático usando las plantillas ya existentes
- Primeras observaciones de patrones

### Semana 4: Ejecución restante + inicio de análisis
- Completar el resto de conversaciones
- Comenzar limpieza y estructuración del dataset
- Primeras tablas comparativas

### Semana 5: Anotación fina + análisis
- Completar anotaciones
- Realizar doble anotación de la muestra
- Análisis de patrones por modelo y por familia
- Cálculo de scores

### Semana 6: Escritura del reporte + preparación del dataset
- Redacción del reporte público
- Preparación del dataset para release (anonimización si corresponde, formato limpio, tarjeta de dataset)
- Revisión de calidad

### Semana 7–8 (buffer): Pulido, publicación y comunicación
- Ajustes finales
- Publicación en GitHub + Alignment Forum / LessWrong
- Hilo de difusión
- Documento de lecciones aprendidas y limitaciones

---

## 5. Presupuesto detallado

| Concepto | Descripción | Estimación (USD) |
|----------|-------------|------------------|
| API – Claude | Conversaciones multi-turno | 220 – 320 |
| API – GPT | Conversaciones multi-turno | 200 – 300 |
| API – Gemini | Conversaciones multi-turno | 150 – 220 |
| API – 4º modelo | Conversaciones multi-turno | 120 – 180 |
| Buffer de re-runs y pruebas adicionales | 15–20% | 100 – 150 |
| **Total solicitado** | | **850 – 1.150** |

**Notas importantes:**
- El funding se solicita **exclusivamente para créditos de API**.
- El tiempo de trabajo del investigador, la infraestructura de documentación y el diseño metodológico previo ya están cubiertos (trabajo ya realizado).
- No se solicitan salarios ni costos indirectos en este Rapid Grant.

---

## 6. Gestión de riesgos del proyecto

| Riesgo | Probabilidad | Impacto | Mitigación |
|--------|--------------|---------|------------|
| Costo de API mayor al esperado | Media | Alto | Empezar con 4 modelos y tener plan de reducción de escenarios |
| Baja varianza entre modelos | Media | Medio | Incluir análisis cualitativo profundo aunque los scores sean similares |
| Fatiga del evaluador | Media | Medio | Distribuir la carga en el timeline y usar plantillas estrictas |
| Dificultad de acceso a algún modelo | Baja | Medio | Tener modelo de reemplazo definido de antemano |

---

## 7. Criterios de éxito (Definition of Done)

El proyecto se considerará exitosamente completado si:

- [ ] Se evaluaron al menos 4 modelos con las familias definidas
- [ ] Existe un dataset anotado público con ≥ 120 conversaciones
- [ ] Se publicó un reporte claro con scores y hallazgos principales
- [ ] El material (prompts + rúbricas + threat model) está documentado y es reutilizable
- [ ] Se registraron las limitaciones de forma transparente

---

**Fin del documento de Alcance + Timeline + Presupuesto**