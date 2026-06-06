---
name: inicio
description: Usar el Día 1 de una instalación de Seneca AIOS, cuando alguien dice "configurame", "armemos esto", "empecemos", "completá mi AIOS", o recién clonó el kit. Asistente combinado — corre la entrevista de 7 preguntas Y arma el set de archivos del Día 1 al final. Idempotente — re-correr cuando se edita intake.md.
---

## Qué hace esta skill

Asistente único combinado. Lee o escribe `intake.md` (la entrevista canónica), corre la entrevista de 7 preguntas si el archivo no está completo, y después arma el set de archivos del Día 1. Una sola corrida.

**El momento "wow":** al final, sugerí el prompt de cierre *"Probá esto — preguntame: ¿en qué me debería enfocar esta semana?"*. El usuario lo corre una vez. Ese es el wow. El prompt mismo planta el Mindset (Default Shift) para que lo internalice.

## Cuándo NO correr esto

- Si ya hizo el inicio y quiere refrescar: corré igual, pero salteá lo ya contestado (idempotente).
- Si quiere agregar una conexión nueva: eso no es inicio — mandalo a editar `conexiones.md`, o a un `/subir-nivel`.

## Ejecución

### Paso 1: Leer la entrevista

Leé `intake.md`. Fijate qué secciones P1-P7 tienen contenido vs. marcadores `[Tu respuesta acá]`.

- **Todo completo** → salteá el Paso 2, andá al Paso 3 (armar).
- **Algo completo** → preguntá: "Veo P1, P3, P4 contestadas. ¿Completamos el resto ahora, o armo con lo que hay?" Decisión del usuario.
- **Nada completo (clon fresco)** → corré el Paso 2 conversando.

### Paso 1.5: Elegir modo

Preguntá: *"¿Lo querés en modo liviano (Proyecto de Claude, sin terminal, ideal si no sos técnico) o completo (Claude Code, con skills y automatizaciones)?"* Ajustá el lenguaje del cierre según la respuesta. En modo liviano, al armar explicá que los archivos de `contexto/` se cargan como "knowledge" del Proyecto.

### Paso 2: La entrevista (7 preguntas, tope duro)

Una a la vez. Escribí cada respuesta en `intake.md` a medida que avanzás (así puede retomar si se corta).

**P1 — ¿Quién sos, qué vendés, a quién?** Identidad, oferta, cliente ideal.

**P2 — Pegá 1-2 cosas que escribiste hace poco. No las edites.** *Única pregunta con regla dura.* Las muestras de voz se PEGAN, no se tipean en la charla. Si empieza a escribir prosa nueva, frenalo:
> *"Pará — pegalo crudo. Si lo escribís acá mientras hablamos, la muestra ya quedó moldeada por nuestra charla. Abrí tu último mail o posteo en otra pestaña y pegá el texto sin editar. Esta es la única regla que no puedo aflojar."*
Pedí dos muestras.

**P3 — ¿Tus 2-3 prioridades de los próximos 90 días?** Si dice "crecer el negocio", empujá: que nombre un número, una fecha, o un entregable.

**P4 — ¿Dónde entra la plata y dónde se registra?** Mapea al Dominio 1.

**P5 — ¿Dónde le hablás a clientes, equipo y al mundo?** WhatsApp, Gmail/Outlook, Instagram, Slack. Mapea a Dominios 2 + 4.

**P6 — ¿Dónde viven grabaciones, notas y documentos?** Mapea a Dominios 6 + 7.

**P7 — ¿Qué tarea te come la semana, y dónde anotás el trabajo?** Captura el dolor principal (lo usa `/subir-nivel`) + Dominio 5.

El Dominio 3 (Calendario) se infiere de P5: Gmail → Google Calendar; Outlook → Outlook. Confirmá en el Paso 3.

### Paso 3: Armar el set del Día 1

Con la entrevista completa, generá estos archivos (o actualizá si re-corrés). Respaldá los originales en `archivo/intake-{AAAA-MM-DD-HHMM}/` si existen.

1. **`contexto/sobre-mi.md`** — de P1 (identidad, rol) + P7 (dolor principal).
2. **`contexto/sobre-el-negocio.md`** — de P1 (oferta, cliente ideal) + P4 (modelo de ingresos).
3. **`contexto/prioridades.md`** — de P3. Lista numerada.
4. **`referencias/voz.md`** — de P2. Pegá las muestras tal cual, con un encabezado corto ("Igualá este registro al redactar; no falsees la voz en contenido externo sin mostrar primero").
5. **`conexiones.md`** — poblá la tabla de 7 filas con P4-P7. Cada fila `mecanismo: sin conectar`.
6. **`CLAUDE.md`** — completá todos los `{{...}}`: nombre, prioridad declarada, resumen de registro de voz, resumen de conexiones.

### Paso 4: La pantalla de cierre

Imprimí una pantalla. Tres líneas máximo:

```
✓ Día 1 listo. Tu AIOS sabe quién sos, qué vendés, qué importa este trimestre y cómo sonás.

Hoy:    preguntame — "¿en qué me debería enfocar esta semana?"
Mañana: elegí una herramienta de conexiones.md y conectala.
Día 7:  corré /auditoria para ver tu puntaje.
```

Cuando corra el prompt de cierre ("¿en qué me debería enfocar esta semana?"), respondé usando solo los archivos nuevos de contexto. Pegá:
- Lista de 3 prioridades, en su registro de voz de P2
- Cada bullet atado a una prioridad de 90 días de P3
- Línea final: *"Si tuviera que elegir una cosa para el lunes, sería [X], porque [razón de prioridades]. ¿Querés que arranque el primer borrador? Y — ¿dónde aplica el Default Shift acá? ¿En qué medida se puede apalancar IA en esta tarea?"*

## Reglas críticas

1. **El tope de 7 preguntas es innegociable.** No agregues una P8 en la charla.
2. **Pegar la voz no se puede saltear.** Si tipea las muestras en el chat, rechazá y pedí que pegue de un texto real.
3. **Armado de una sola pasada.** Después del Paso 2, escribí los archivos del Paso 3 en un solo lote. Sin confirmación de varios turnos.
4. **Idempotente.** Re-correr con un intake editado refresca los archivos; respaldá los originales en `archivo/intake-{ts}/`. Salteá lo ya contestado salvo que quiera revisar.
5. **Pantalla de cierre = tres líneas.** No un menú.
6. **No generes skills extra.** El kit trae 3 skills; las demás las crea el usuario con `/subir-nivel`.
7. **Solo lectura sobre `referencias/3ms-framework.md`.** Ya viene en el kit. No lo pises.
8. **Nada de `.env`.** No pidas claves de API el Día 1. Las conexiones vienen el Día 2.

---

> *Adaptado de Los 3 Ms de la IA™ y Las 4 Cs de un AIOS™ © 2026 Nate Herk. Adaptación al castellano por Seneca AI.*
