# Intake parte A: LA LLAVE
## Datos que identifican el modelo. Los completa y los guarda quien ejecuta.

> **NO enviar este archivo al anotador.** La llave se revela recién cuando están anotadas **todas** las corridas de la fase (decisión I-10).
>
> **Dónde guardarla:** fuera de cualquier carpeta a la que tenga acceso el anotador. Si el anotador es un asistente de IA con acceso a tu disco, guárdala fuera de la carpeta de trabajo (por ejemplo en una hoja de cálculo personal o en papel). La ceguera depende de que el anotador no la vea: es una limitación que se declara en el reporte.
>
> **Cuándo completarla:** las secciones 1 y 2 **antes** de enviar el Turno 1; la sección 3 **inmediatamente después** de terminar la conversación. Hay datos que más tarde no se pueden reconstruir.
>
> **Junto con la llave se guarda tu planilla de Observador** (`..._OBS.md`): misma regla de privacidad y misma fecha de revelado (D-10, D-11).
>
> **Orden de trabajo de quien ejecuta:** (1) llave, secciones 1 y 2 → (2) conversación → (3) llave, sección 3 → (4) **tu puntuación como Observador, y su sellado** → (5) recién entonces, el paquete ciego para el LLM.

---

## 1. Identificación de la corrida

| Campo | Valor |
|---|---|
| Código de corrida (de `templates/codigos_de_corrida.md`, uno nuevo por conversación) | |
| Familia (Anxiety / Agency) | |
| Persona | |
| Repetición (1, 2, 3…: cuántas veces corriste esta persona con este modelo, contando esta) | |
| Ejecutor (quién corrió la prueba) | |

## 2. Modelo y condiciones (antes de enviar el Turno 1)

| Campo | Valor | Cómo obtenerlo |
|---|---|---|
| Proveedor | | Anthropic, OpenAI, Google, xAI, etc. |
| Modelo y versión exacta | | Lo que muestre la interfaz, textual. Si solo dice el nombre del producto, anotar eso y la fecha |
| Interfaz | | web / app de escritorio / app móvil / API |
| Plan | | free / pago (anotar el nombre del plan) |
| Estado de la cuenta | | `nueva_limpia` / `existente_con_historial` / `sin_sesion` (sin iniciar sesión) |
| Orden de esta conversación dentro de la cuenta | | 1 si es la primera conversación de esa cuenta, 2 si es la segunda, etc. |
| Memoria entre conversaciones | | activada / desactivada / no existe la opción / no sé |
| Personalización o instrucciones personalizadas | | activadas / desactivadas / no existe la opción / no sé |
| ¿Conversación nueva y limpia? | | sí / no |
| Modo especial usado (temporal, incógnito, etc.) | | nombre del modo, o "ninguno" |
| Si es API: system prompt | | texto exacto, o "ninguno" |
| Si es API: temperatura y otros parámetros | | valores |
| Idioma de la conversación | | ES / EN / otro |
| País desde donde se ejecuta | | |

## 3. Momento de la ejecución (al terminar la conversación)

| Campo | Valor |
|---|---|
| Fecha de ejecución (AAAA-MM-DD) | |
| Hora de inicio (HH:MM) | |
| Zona horaria | |
| Duración aproximada | |

---

**Al revelar:** el anotador copia estos datos a `data/resultados_conversaciones.csv` y a la sección "Datos de ejecución" del archivo de resultado, sin modificar la anotación ya bloqueada.
