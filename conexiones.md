# Conexiones

Registro de cada sistema que tu AIOS puede alcanzar. Lo completa `/inicio` con tus respuestas P4-P7; se amplía con el tiempo. `/auditoria` revisa este archivo para ver cobertura y frescura.

| # | Dominio | Herramienta | Mecanismo | Auth | Último chequeo |
|---|---|---|---|---|---|
| 1 | Ingresos / facturación | _lo completa /inicio_ | sin conectar | — | — |
| 2 | Interacción con clientes | _lo completa /inicio_ | sin conectar | — | — |
| 3 | Calendario | _lo completa /inicio_ | sin conectar | — | — |
| 4 | Comunicación | _lo completa /inicio_ | sin conectar | — | — |
| 5 | Tareas / proyectos | _lo completa /inicio_ | sin conectar | — | — |
| 6 | Reuniones / notas | _lo completa /inicio_ | sin conectar | — | — |
| 7 | Conocimiento / archivos | _lo completa /inicio_ | sin conectar | — | — |

**Mecanismos posibles:** `proyecto-claude` (contexto cargado en un Proyecto), `mcp` (servidor MCP), `script` (Python/Bash contra una API, en `scripts/`), `export` (volcado CSV/JSON), `key+ref` (clave en `.env` + guía en `referencias/{herramienta}-api.md`), `sin conectar`.

Herramientas típicas de una PyME argentina: WhatsApp, Gmail, Instagram, MercadoPago, Google Calendar, Google Drive, planillas de Google/Excel, Notion, Trello.

> **Cero credenciales en este archivo.** Las claves van en un `.env` (que está en `.gitignore`).

Cuando conectes una herramienta nueva, guardá también `referencias/{herramienta}-api.md` con endpoints, flujo de auth y consultas comunes — se investiga una vez, queda para siempre.
