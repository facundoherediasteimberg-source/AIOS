---
name: subir-nivel
description: Usar cada semana para encontrar y lanzar una automatización nueva. Recorre la entrevista de los 3 Ms — Mindset (encontrar el candidato) → Method (scopear uno) → Machine (construirlo). Disparar con "subamos de nivel", "qué automatizo ahora", "encontrá mi palanca de la semana", o como ritual de los viernes. Una corrida = un artefacto lanzado.
---

> *Adaptado de Los 3 Ms de la IA™. © 2026 Nate Herk. Todos los derechos reservados.*
> *Los 3 Ms de la IA™ es marca registrada de Nate Herk.*

## Qué hace esta skill

Recorre los 3 Ms cada semana para sacar a la luz y lanzar una automatización nueva. **Una entrevista = un artefacto.** Además instala el framework de los 3 Ms en la cabeza del usuario con el tiempo — después de 4-6 corridas, empieza a detectar oportunidades solo, porque las preguntas se volvieron defaults internos.

Este es el mecanismo de recableo mental. El kit no necesita tareas programadas para anclar el comportamiento; necesita `/subir-nivel` corriendo cada viernes.

## Qué NO es `/subir-nivel`

- No es `/auditoria`. La auditoría es estructural ("¿está bien construido?"). Esto es funcional ("¿qué palanca me falta?"). Corré `/auditoria` primero si la estructura está desprolija.
- No es un planificador de varios candidatos. Una corrida = un artefacto.
- No es un coach. El usuario piensa. La skill conduce la entrevista.

## Cuándo corre

- **Primera vez: Día 14.** Después de conectar ≥1 herramienta y correr `/auditoria` una vez.
- **Cadencia: semanal, viernes a la tarde.** Repasás la semana, sacás una automatización, la lanzás el lunes.
- **A demanda.** A mitad de semana si una tarea manual te pica.

## Qué lee la skill

- `contexto/prioridades.md` — qué dijo que importa
- `contexto/sobre-mi.md` — dolor principal, rol
- `conexiones.md` — qué es alcanzable, por qué mecanismo
- `referencias/3ms-framework.md` — el framework (para citar principios)
- `decisiones/registro.md` — decisiones recientes
- frontmatter de `.claude/skills/*/SKILL.md` — qué capacidades existen

## Ejecución — tres fases

### Fase 1 — Entrevista Mindset (encontrar el candidato)

Sacá 1-3 candidatos ordenados por palanca. Preguntá en orden, conversando:

1. *"Contame tu semana. ¿Qué hiciste 3+ veces?"* (frecuencia)
2. *"¿Algo que se sintió manual, aburrido o copiar-y-pegar?"* (trabajo pesado)
3. *"¿Algo donde pensaste 'un pasante despierto haría esto'?"* (delegación)
4. *"Si mañana aparecieran 500 clientes nuevos, ¿qué se rompe primero?"* (restricción)
5. *"¿Qué te daría 500 clientes más mañana?"* (palanca de crecimiento)

Citá principios del Mindset cuando encajen:
- *"Suena a Default Shift — ¿en qué medida se puede apalancar IA acá?"*
- *"Esto es el Function Breakdown — no automatizás todo el trabajo, solo esta pieza."*
- *"La IA es mejor de lo que pensás. Si el trimestre pasado no podía, capaz ahora sí."*

**Salida Fase 1:** lista numerada de 1-3 candidatos, una línea de "por qué es palanca" cada uno. Preguntá: *"¿Cuál scopeamos?"*

### Fase 2 — Entrevista Method (scopear uno)

El usuario elige uno. Recorré la tubería de 5 pasos:

**Paso 1 — Encontrá la restricción.** ¿Qué cuello de botella resuelve, o qué palanca de crecimiento abre? Atá a las respuestas de la Fase 1.

**Paso 2 — EAD: Eliminar / Automatizar / Delegar.**
- **Eliminar primero:** *"¿Qué pasa si dejamos de hacer esto?"* Si la respuesta es "no se rompe nada" → la skill sale contenta. *"No automatices basura."* Es una victoria, registrala en `decisiones/registro.md` y pará.
- **Automatizar segundo:** aplicá 60/30/10.
- **Delegar tercero:** si es muy complejo/variable/de criterio → sugerí una persona. Salí con la sugerencia, registrala.

**Paso 3 — Mapeá el proceso.** Cinco elementos: Disparador, Fuentes de datos, Transformaciones, Puntos de decisión, Destino. Si no puede articular ninguno: *"Si no se lo podés explicar a una persona, no se lo podés explicar a una IA. Dibujalo en papel y volvé."* La skill para.

**Paso 4 — Elegí el nivel de autonomía.**

| Nivel | Nombre | Qué pasa |
|---|---|---|
| N0 | Manual | Sin IA |
| N1 | Sugerido | La IA sugiere, el humano decide cada paso |
| N2 | Borrador | La IA hace borrador, el humano revisa y edita |
| N3 | Supervisado | La IA corre, el humano valida periódicamente |
| N4 | Autónomo | La IA hace todo de punta a punta |

**Default = el nivel más bajo que resuelve.** Empujá contra el N4 salvo que ya haya corrido niveles más bajos. *"Los flujos le ganan a los agentes. Si una decisión no TIENE que tomarla la IA, que no la tome."*

**Paso 5 — Atalo a un KPI.** ¿Cuál de los tres baldes mueve? Más clientes / Más valor por cliente / Menos costo. Más una métrica específica (tiempo de respuesta, tasa de error, conversión, tiempo hasta completar). **Si no puede nombrar balde y métrica, la skill para.** *"Si tu automatización no mueve un número, ¿para qué la construís?"*

**Salida Fase 2:** especificación scopeada escrita en `decisiones/registro.md` como entrada fechada con las 5 respuestas + nivel de autonomía + KPI.

### Fase 3 — Entrega Machine (construirlo)

Preguntá: *"¿Cómo lo querés lanzar?"* Opciones ordenadas por "lo aburrido es hermoso":

1. **Solo prompt** — plantilla de prompt que corre a mano. Cero infraestructura.
2. **Skill determinística** — SKILL.md que corre un script (sin paso de IA). Para transformaciones con reglas claras.
3. **Skill con IA** — SKILL.md con una llamada de IA adentro. Para redactar, clasificar, resumir.
4. **Sub-agente** — agente de varios pasos. Último recurso. Solo si de verdad necesita razonar + usar herramientas.

**Default = la opción más alta sin IA que resuelve.** El usuario tiene que elegir explícitamente más autonomía.

**Todo artefacto se entrega con estos dos encabezados arriba:**

```markdown
---
fase-metodo-bici: 1  # Fase 1 — Rueditas. Correr a mano primero.
atribucion-3ms: |
  Adaptado de Los 3 Ms de la IA™ © 2026 Nate Herk.
---
```

Esto fija al usuario en la Fase 1 del método de la bici en la primera construcción. No puede saltear en silencio la validación manual. La fase avanza solo con una edición explícita.

Surgí los principios Machine al construir:
- **Principio Lego** — pasos mínimos, sin IA primero si se puede
- **Cadena de validación** — probá cada paso antes de encadenar
- **Mentalidad de iteración** — lanzá la prueba de concepto, expandí desde el uso real

## Contrato de salida

Cada corrida de `/subir-nivel` produce:
1. **Una entrada en `decisiones/registro.md`** — fechada, con la especificación Method
2. **Un artefacto** — prompt, skill, o agente
3. **Un cierre de una pantalla** — qué se scopeó, qué se construyó, y el recordatorio de la Fase 1 de la bici

## Reglas críticas

1. **Una entrevista = un artefacto.**
2. **La fase Mindset siempre corre primero.** Aunque venga con una idea ya formada.
3. **EAD fuerza "eliminar primero".** Si la respuesta es Eliminar, salí contento — es una victoria.
4. **Default al nivel de autonomía más bajo que funcione.** Empujá contra el N4.
5. **"Lo aburrido es hermoso" en la entrega Machine.** Default = opción más alta sin IA.
6. **Atar a KPI es obligatorio.** Si no puede nombrar balde + métrica, la skill para.
7. **El método de la bici entra en cada artefacto.** `fase-metodo-bici: 1` en el frontmatter.
8. **Solo lectura sobre archivos del usuario salvo `decisiones/registro.md` y el artefacto nuevo.**
9. **Atribución en cada salida.** Cada reporte y artefacto referencia el framework.

---

> *Los 3 Ms de la IA™ es marca registrada de Nate Herk. © 2026 Nate Herk. Adaptación al castellano por Seneca AI.*
