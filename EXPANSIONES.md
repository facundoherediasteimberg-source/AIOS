# Expansiones — qué agregar a medida que crecés

El kit arranca liviano a propósito. A medida que tu AIOS madura, sumás piezas. Algunas ideas, en orden de utilidad:

## Conexiones (capa 2)
- Conectá WhatsApp, Gmail, MercadoPago o tu planilla de ventas vía script o MCP.
- Por cada herramienta conectada, guardá `referencias/{herramienta}-api.md`.

## Capacidades (capa 3)
- `templates/` — plantillas que reusás (propuestas, mails, posteos).
- `.claude/skills/{nombre}/SKILL.md` — skills nuevas que armás con `/subir-nivel`.
- `.claude/agents/` — agentes para tareas que necesitan razonar varios pasos.

## Cadencia (capa 4)
- Hooks en `.claude/settings.json` o skills `diario-*` / `semanal-*` que corrés en horario fijo.
- Un resumen matutino. Un repaso de pipeline los viernes.

## Estructura
- `scripts/` — tus scripts de Python/Bash.
- `audits/` — historial de `/auditoria` para ver subir el puntaje.

> Regla: no automatices nada que todavía no funcione a mano. Cadencia va última.
