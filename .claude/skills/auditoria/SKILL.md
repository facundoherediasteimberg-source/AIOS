---
name: auditoria
description: Usar cuando alguien pide una auditoría del AIOS, pide puntuar su setup contra las 4 Cs, o dice "¿anda mi AIOS?" / "auditá mi setup" / "encontrá brechas en mi AIOS". Produce un tablero de las 4 Cs con los 3 arreglos de mayor palanca.
---

## Qué hace esta skill

Corre la **Auditoría de las 4 Cs** sobre el proyecto actual. Lee (nunca escribe) el manual operativo, la memoria, skills, agentes, MCPs, decisiones y referencias. Puntúa cada una de las 4 Cs sobre 25. Muestra fortalezas y las 3 brechas de mayor palanca con próximos pasos concretos.

**El alcance es estructural — "¿está bien construido el AIOS?"** NO es un planificador de capacidades (eso es `/subir-nivel`). La auditoría responde: ¿están en forma los archivos, carpetas, registros y conexiones?

La primera corrida es la línea base. Re-correr semanal para ver subir el puntaje. Ese es el gancho de interés compuesto.

## Contexto de hoy

- **Fecha:** !`date +%Y-%m-%d`
- **Raíz del proyecto:** el directorio actual

## Las 4 Cs (25 cada una = 100 total)

| Capa | Prueba |
|---|---|
| **Contexto** | Conoce el negocio — identidad, equipo, voz, decisiones, referencias |
| **Conexiones** | Llega a las cosas del usuario — MCPs, integraciones, fuentes de datos |
| **Capacidades** | Sabe hacer el trabajo — skills + agentes |
| **Cadencia** | Corre sin que se lo pidan — horarios, hooks, rituales recurrentes |

## Ejecución

### Paso 1: Descubrir la forma del proyecto

La auditoría busca **patrones e intención**, no rutas exactas. Los nombres varían. Usá Glob y Read:

- **Manual operativo:** `CLAUDE.md`, `CLAUDE.local.md`.
- **Memoria:** `MEMORY.md`, carpeta `memory/`, o memoria del proyecto.
- **Skills:** `.claude/skills/*/SKILL.md` — contar + frontmatter.
- **Agentes:** `.claude/agents/*.md` — contar.
- **Mecanismos de conexión** (cualquiera = "alcanzable"): MCPs (`.mcp.json`, `settings.json`), scripts de API (`scripts/`), pipelines de export, claves `.env` + `referencias/{herramienta}-api.md`, o contexto cargado en Proyecto de Claude.
- **Registro de conexiones:** `conexiones.md`.
- **Decisiones:** `decisiones/registro.md` o equivalente.
- **Referencias:** `referencias/`, `docs/`.
- **Plantillas:** `templates/`.
- **Hooks / tareas programadas:** `settings.json` hooks, o skills tipo `diario-*` / `semanal-*` / `mensual-*`.

No penalices nombres no canónicos si la intención está capturada en otro lado.

### Paso 2: Puntuar cada C (25 puntos cada una)

#### Contexto (25)
| Criterio | Puntos | Cómo detectarlo |
|---|---|---|
| Manual operativo existe y es sustancioso (>200 palabras) | 5 | Leer CLAUDE.md |
| Identidad / rol / voz capturados | 5 | CLAUDE.md menciona quién es + rol/misión |
| Memoria persistente con varias entradas | 5 | MEMORY.md o `memory/` con >3 |
| Documentos de referencia | 5 | `referencias/` o `docs/` con ≥1 |
| Decisiones capturadas | 5 | `decisiones/registro.md` con ≥1 entrada |

#### Conexiones (25) — por dominio, agnóstica al mecanismo

Una conexión "alcanzable" cuenta por CUALQUIER mecanismo. El kit es API-first; no prefiere MCPs.

**Los 7 dominios universales (ejemplos adaptados a PyME argentina):**

| # | Dominio | Ejemplos |
|---|---|---|
| 1 | Ingresos / facturación | MercadoPago, transferencia, Stripe, planilla de ventas, AFIP |
| 2 | Interacción con clientes | WhatsApp, Instagram DMs, HubSpot, Gmail-como-CRM |
| 3 | Calendario | Google Calendar, Outlook, Calendly |
| 4 | Comunicación | Gmail, Outlook, WhatsApp, Slack |
| 5 | Tareas / proyectos | Trello, Notion, ClickUp, Asana |
| 6 | Reuniones / notas | Google Meet, Otter, Notion, grabaciones |
| 7 | Conocimiento / archivos | Google Drive, Notion, Obsidian, Dropbox |

| Criterio | Puntos | Cómo detectarlo |
|---|---|---|
| Cobertura de dominios | 10 | 1,4 pts por dominio alcanzable. Redondear a 0,5. Tope 10. |
| Guías de referencia | 5 | -1 por herramienta conectada sin `referencias/{herramienta}-api.md`. Piso 0. |
| Frescura de auth / pipeline | 5 | -1 por conexión vencida o script sin correr en 30 días. Piso 0. |
| Documentación en `conexiones.md` | 3 | 0 si falta; 1 escasa; 2 casi todo; 3 cubre todo. |
| Balance lectura Y escritura | 2 | Al menos una conexión puede ESCRIBIR (mandar mail, postear). 0 si todo es solo lectura. |

#### Capacidades (25)
| Criterio | Puntos | Cómo detectarlo |
|---|---|---|
| 3+ skills instaladas | 10 | Contar `.claude/skills/*/SKILL.md` |
| 1+ skill propia del usuario | 10 | Nombres fuera de: `inicio`, `auditoria`, `subir-nivel` |
| 1+ agente definido | 5 | Contar `.claude/agents/*.md` ≥ 1 |

#### Cadencia (25)
| Criterio | Puntos | Cómo detectarlo |
|---|---|---|
| 1+ disparador recurrente/programado | 10 | Hooks en `settings.json`, o skill `diario-*`/`semanal-*`/`mensual-*` |
| Señal de actividad reciente | 10 | Archivos en `.claude/skills/` modificados en 30 días, o entrada en `decisiones/registro.md` en 30 días |
| Carpeta de plantillas poblada | 5 | `templates/` con ≥1 |

### Paso 3: Top 3 brechas por palanca

Por cada criterio que perdió puntos: palanca = (puntos perdidos) × (multiplicador de impacto).

**Multiplicadores:** 0 dominios alcanzables: **4x** · manual ausente o flaco: **3x** · ≤2 dominios: **3x** · 0 skills: **2x** · sin disparador recurrente: **2x** · todo solo lectura: **2x** · 0 guías de referencia: **1,5x** · sin registro de decisiones: **1,5x** · resto: **1x**.

Ordená descendente. Tomá las 3 primeras. Por cada una, un próximo paso concreto.

### Paso 4: Imprimir el reporte

En el chat (Markdown):

```
# Auditoría AIOS — {fecha}
**Puntaje: {total}/100** ({etapa})

Etapas:
- 0-39 → Etapa 0: Fundación
- 40-69 → Etapa 1: Construido
- 70-89 → Etapa 2: Componiendo
- 90-100 → Etapa 3: Autónomo

## Tablero
Contexto      {barra}  {n}/25  {etiqueta}
Conexiones    {barra}  {n}/25  {etiqueta}
Capacidades   {barra}  {n}/25  {etiqueta}
Cadencia      {barra}  {n}/25  {etiqueta}

(barra = ## por cada 5 pts; etiqueta = "Fuerte" ≥20, "Sólido" 15-19, "Flaco" 8-14, "Falta" <8)

## Fortalezas
- {1-3 bullets de los criterios más altos}

## Top 3 brechas (por palanca)
1. **{brecha}** (-{puntos} × {mult}) → {próximo paso}
2. ...
3. ...

## Sugerido: {la acción de mayor palanca}

---
Solo brechas estructurales. Para brechas de CAPACIDAD (qué podría HACER tu AIOS que todavía no), corré /subir-nivel.
```

### Paso 5: Ofrecer guardar

Después de imprimir, preguntá: "¿Guardo esta auditoría en `audits/auditoria-{fecha}.md` para seguir el puntaje en el tiempo?" Si sí, escribila (creando `audits/` si hace falta). Es el único efecto de escritura.

## Notas

- **Solo lectura por default.** Nunca modifiques archivos del proyecto. El único write opcional es el reporte.
- **Flexible con los nombres.** No penalices nombres no canónicos.
- **Honesto, no generoso.** Un 95/100 es para mostrar. La mayoría cae entre 40 y 70.
- **No sugieras skills que no existen.**
- **La velocidad importa.** Reporte en menos de 60 segundos. Leé archivos puntuales, contá carpetas de skills sin leer cada una entera.
