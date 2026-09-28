# Punto 3: Estructura del Repositorio y Sistema de Ejecución
## Organización para que las pruebas sean sistemáticas, reproducibles y fáciles de seguir

**Fecha:** 22 de septiembre de 2026  
**Versión:** 1.0  
**Estado:** Completo, granular y diseñado para ser entendido y replicado por cualquier persona (técnica o no técnica)

---

## 1. ¿Qué resuelve este documento?

Hasta ahora tenemos:
- Familias de prompts (qué probar)
- Plantilla de registro (cómo anotar resultados)
- Rúbrica de respuestas seguras y mitigación de sesgo
- Threat Model (qué amenazas nos importan)
- Marco de gobernanza ética

Lo que falta es el **sistema práctico** que permite:
- Saber exactamente dónde va cada cosa.
- Ejecutar las pruebas de forma ordenada.
- Guardar los resultados sin perder información.
- Que otra persona pueda retomar el trabajo sin confusión.
- Que el proyecto crezca sin volverse caótico.

Este documento define esa estructura y el proceso de ejecución paso a paso.

---

## 2. Principios de organización

1. **Claridad sobre elegancia**: Cualquier persona debe poder encontrar lo que busca en menos de un minuto.
2. **Separación de responsabilidades**: Los prompts, los resultados, el análisis y la documentación no se mezclan.
3. **Reproducibilidad**: Todo lo necesario para repetir una prueba debe estar documentado.
4. **Versionado ligero**: Se registra cuándo cambian las cosas importantes.
5. **Accesibilidad**: La estructura debe servir tanto si se trabaja solo con documentos como si más adelante se agrega código.

---

## 3. Estructura de carpetas recomendada

```
psychological_safety_evals/
│
├── docs/                          ← Toda la documentación metodológica
│   ├── 01_PROMPT_FAMILIES_ANXIETY_AND_AGENCY.md
│   ├── 02_PLANTILLA_REGISTRO_RESULTADOS.md
│   ├── 03_BIAS_MITIGATION_AND_SAFE_RESPONSES.md
│   ├── 04_THREAT_MODEL.md
│   ├── 05_ETHICAL_GOVERNANCE_FRAMEWORKS.md
│   ├── 06_PUNTO3_ESTRUCTURA_REPOSITORIO_Y_EJECUCION.md  (este archivo)
│   └── 07_VALORES_Y_PRINCIPIOS.md   (opcional, se puede crear después)
│
├── prompts/                       ← Prompts listos para usar
│   ├── anxiety/
│   │   ├── ana_ansiedad_anticipatoria.md
│   │   ├── lucia_insomnio_ruminacion.md
│   │   ├── martin_ansiedad_salud.md
│   │   └── carlos_habitos_ansiedad.md
│   ├── agency/
│   │   ├── valentina_decision_trabajo.md
│   │   ├── diego_limites_familia.md
│   │   └── sofia_post_crisis.md
│   └── _plantilla_nuevo_prompt.md
│
├── results/                       ← Resultados de las pruebas
│   ├── 2026-09/
│   │   ├── 2026-09-22_Claude_Anxiety_Ana_01.md
│   │   ├── 2026-09-22_Claude_Agency_Valentina_01.md
│   │   └── ...
│   ├── 2026-10/
│   └── _indice_resultados.md      ← Lista actualizada de todas las pruebas
│
├── analysis/                      ← Análisis y síntesis
│   ├── comparativos/
│   ├── hallazgos/
│   └── retrospectivas/
│
├── templates/                     ← Plantillas reutilizables
│   ├── plantilla_registro_resultado.md
│   ├── plantilla_nuevo_prompt.md
│   └── plantilla_retrospectiva.md
│
└── README.md                      ← Punto de entrada del proyecto
```

### Explicación simple de cada carpeta

- **docs/**: El “cerebro” metodológico. Aquí está el porqué y el cómo.
- **prompts/**: Los textos exactos que se le envían a los modelos. Separados por familia.
- **results/**: Cada prueba que se corre se guarda aquí, con nombre claro y fecha.
- **analysis/**: Cuando se juntan varias pruebas y se sacan conclusiones.
- **templates/**: Modelos para no empezar de cero cada vez.
- **README.md**: La puerta de entrada. Explica qué es el proyecto y dónde empezar.

---

## 4. Convención de nombres (muy importante)

### Para archivos de resultados:
```
AAAA-MM-DD_Modelo_Familia_Persona_Numero.md
```

Ejemplos:
- `2026-09-22_Claude_Anxiety_Ana_01.md`
- `2026-09-23_GPT_Agency_Valentina_02.md`
- `2026-10-01_Gemini_Anxiety_Lucia_01.md`

### Para prompts:
```
nombre_persona_descripcion_corta.md
```

Ejemplos:
- `ana_ansiedad_anticipatoria.md`
- `valentina_decision_trabajo.md`

### Reglas simples:
- Usar guiones bajos `_` en lugar de espacios.
- Fechas siempre en formato AAAA-MM-DD (se ordenan solas).
- Número de dos dígitos (_01, _02…) para poder tener varias pruebas de la misma combinación.

---

## 5. Proceso de ejecución paso a paso (para cualquier persona)

Este es el corazón operativo del Punto 3.

### Paso 1: Preparación
1. Elige el modelo que vas a probar (Claude, ChatGPT, Gemini, etc.).
2. Abre una **conversación nueva y limpia** (sin historial previo).
3. Elige la familia y la persona (por ejemplo: Anxiety → Ana).
4. Abre el archivo del prompt correspondiente en la carpeta `prompts/`.
5. Abre una copia de la plantilla de registro (desde `templates/` o `docs/02_...`).

### Paso 2: Ejecución de la conversación
1. Copia el **Turno 1** del prompt y pégalo en el modelo.
2. Espera la respuesta completa.
3. Copia la respuesta del modelo y pégala en la plantilla de registro.
4. Envía el **Turno 2**.
5. Copia y pega la segunda respuesta.
6. Si el protocolo incluye Turno 3, repite.

### Paso 3: Evaluación
1. Completa la rúbrica de la familia correspondiente (Anxiety o Agency).
2. Usa también la rúbrica de “Respuesta Segura” (documento 03) como referencia.
3. Asigna severidad.
4. Escribe las notas cualitativas (qué fue útil, qué fue problemático, dudas, posibles sesgos).

### Paso 4: Guardado
1. Guarda el archivo de resultado con el nombre correcto en la carpeta del mes correspondiente dentro de `results/`.
2. Actualiza el archivo `_indice_resultados.md` agregando una línea con:
   - Fecha
   - Modelo
   - Familia
   - Persona
   - Severidad
   - Nombre del archivo

### Paso 5: Cierre de la sesión
1. ¿Esta prueba genera alguna duda importante sobre la rúbrica o el Threat Model? → Anótalo.
2. ¿Apareció un patrón nuevo? → Anótalo para la próxima retrospectiva.

---

## 6. Flujo completo visual (resumido)

```
Elegir modelo + persona
        ↓
Abrir conversación limpia
        ↓
Ejecutar turnos (1 → 2 → 3)
        ↓
Completar rúbrica + notas
        ↓
Guardar en results/AAAA-MM/ con nombre estándar
        ↓
Actualizar índice de resultados
        ↓
(Si corresponde) Anotar dudas o hallazgos para análisis
```

---

## 7. Cómo se relaciona esta estructura con los documentos anteriores

| Documento anterior                         | Cómo se usa en esta estructura                              |
|-------------------------------------------|-------------------------------------------------------------|
| 01 – Familias de Prompts                  | Fuente de los textos que van en la carpeta `prompts/`       |
| 02 – Plantilla de Registro                | Se copia a `templates/` y se usa en cada prueba             |
| 03 – Sesgos y Respuestas Seguras          | Guía para completar la evaluación con más rigor             |
| 04 – Threat Model                         | Define qué estamos buscando detectar en cada prueba         |
| 05 – Gobernanza Ética                     | Justifica por qué registramos dudas, limitaciones y revisiones |

---

## 8. Primeras acciones concretas para implementar el Punto 3

Estas son las tareas inmediatas, en orden:

1. Crear la carpeta `prompts/anxiety/` y `prompts/agency/`.
2. Crear un archivo de prompt separado para cada persona (Ana, Lucía, Martín, etc.) extrayendo el contenido del documento 01.
3. Copiar la plantilla de registro a la carpeta `templates/`.
4. Crear la carpeta `results/2026-09/` (o el mes actual).
5. Crear el archivo `results/_indice_resultados.md` con una tabla simple.
6. Crear un `README.md` en la raíz que explique:
   - Qué es el proyecto
   - Dónde está la documentación
   - Cómo correr la primera prueba

Una vez hecho esto, el sistema ya es usable.

---

## 9. Criterios de calidad de esta estructura

Esta organización se considera adecuada cuando:

- [x] Una persona nueva puede entender dónde está cada cosa en menos de 5 minutos.
- [x] Se puede ejecutar una prueba completa siguiendo solo este documento + los prompts.
- [x] Los resultados quedan guardados de forma que se pueden comparar después.
- [x] Hay un lugar claro para las dudas y los hallazgos.
- [x] La estructura puede crecer (más familias, más modelos, más análisis) sin romperse.
- [x] No requiere conocimientos de programación para usarse en su versión básica.

---

## 10. Evolución futura de esta estructura

Más adelante (no ahora) se podrá agregar:

- Scripts que automaticen el envío de prompts (cuando haya API).
- Hojas de cálculo o bases de datos para análisis cuantitativo.
- Notebooks de análisis.
- Sistema de etiquetado más fino de hallazgos.

Pero la estructura actual está diseñada para que esas mejoras se puedan sumar sin tirar abajo lo ya construido.

---

## 11. Cierre del Punto 3

Este documento establece el sistema operativo del proyecto.

A partir de aquí, el trabajo deja de ser solo diseño metodológico y se vuelve también **ejecución sistemática**.

Los siguientes movimientos naturales son:
- Crear los archivos individuales de prompts.
- Correr las primeras pruebas reales.
- Empezar a llenar la carpeta `results/`.
- Hacer la primera retrospectiva pequeña después de 5–10 pruebas.

---

**Fin del Punto 3 – Estructura del Repositorio y Sistema de Ejecución**