<div align="center">

# Seneca AIOS

**Convertí a Claude en tu Sistema Operativo de IA.**

Un kit gratuito y open source que personaliza a Claude con tu negocio, en castellano.
Conoce lo que hacés, habla como vos, y te ayuda a pensar, decidir y trabajar más rápido.

![Licencia](https://img.shields.io/badge/licencia-MIT-green)
![Idioma](https://img.shields.io/badge/idioma-espa%C3%B1ol-blue)
![Hecho por](https://img.shields.io/badge/hecho%20por-Seneca%20AI-black)

</div>

---

## ¿Qué es esto?

Un **Sistema Operativo de IA (AIOS)** es un sistema dentro del cual operás tu negocio — como Windows, pero pensado para tu empresa. Captura tus datos, captura tu forma de trabajar, corre tus flujos y te saca a vos como cuello de botella.

Este kit lo arma en minutos. Corrés `/inicio`, contestás 7 preguntas, y Claude queda personalizado con tu negocio. Después tenés dos rituales semanales (`/auditoria` y `/subir-nivel`) para seguir ganando ventaja semana a semana.

**No hace falta ser programador.** Funciona como Proyecto de Claude (sin terminal) o con Claude Code.

## ¿Para quién es?

Dueños de PyME, emprendedores, freelancers y operadores que quieren dejar de hacer todo a mano y empezar a apalancar IA en su negocio — sin perderse en mil herramientas.

## La prueba de fuego

> **"Mientras no estás frente a la compu, tu AIOS observa un hecho real de tu negocio y produce algo más rápido y más preciso de lo que harías vos."**

Cada pieza del kit apunta a eso. Si algo no aporta a esa prueba, no entra.

---

## Arranque rápido

```bash
git clone https://github.com/facundoherediasteimberg-source/AIOS.git mi-aios
cd mi-aios
```

1. Abrí la carpeta en **Claude Code** (o cargá los archivos como **Proyecto de Claude** en claude.ai).
2. Corré **`/inicio`**. Contestá las 7 preguntas. Las muestras de tu voz se **pegan**, no se describen. ~15 minutos.
3. Usalo una semana con preguntas reales. Registrá decisiones en `decisiones/registro.md`.
4. **Día 7:** corré **`/auditoria`** y cerrá una brecha.
5. **Día 14:** corré **`/subir-nivel`** y construí una automatización.
6. **Semana 3+:** `/subir-nivel` cada viernes. Una cosa nueva por semana.

---

## Las cuatro capas (las 4 Cs)

Lo que vas a construir, en orden. Cada capa se apoya en la anterior.

| # | Capa | Qué significa | "Lista" cuando… |
|---|---|---|---|
| 1 | **Contexto** | Conoce tu negocio | Una sesión nueva responde "¿qué hace este negocio y quién trabaja acá?" sin buscar |
| 2 | **Conexiones** | Llega a tus cosas | "¿Qué tengo mañana y qué vence?" → datos en vivo, sin copiar y pegar |
| 3 | **Capacidades** | Sabe hacer el trabajo | Una frase corta dispara un flujo que produce un resultado |
| 4 | **Cadencia** | Corre sin que se lo pidas | Compu cerrada. Llega un resumen al mail. Alguien le pregunta y obtiene una respuesta real |

**Contexto va primero y es obligatorio.** Conexiones y Capacidades pueden ir en paralelo. Cadencia es lo último — no automatices flujos que todavía no funcionan a mano.

## Las tres skills

| Skill | Cuándo | Qué hace |
|---|---|---|
| **`/inicio`** | Día 1 | Entrevista de 7 preguntas. Genera tus archivos y completa `CLAUDE.md`. |
| **`/auditoria`** | Día 7, después semanal | Tablero de las 4 Cs sobre 100. Solo lectura. Mirá subir el puntaje. |
| **`/subir-nivel`** | Día 14, después semanal | Entrevista de los 3 Ms. Una corrida = una automatización lista. |

## Dos modos de usarlo

- **Liviano (Proyecto de Claude):** sin terminal, visual. Cargás tu contexto como "knowledge". Ideal si no sos técnico.
- **Completo (Claude Code):** todo el kit con skills y automatizaciones.

`/inicio` te pregunta cuál querés y arma el set acorde.

---

## Mapa del repo

```
seneca-aios/
├── README.md
├── CLAUDE.md                  ← Tu manual operativo (lo completa /inicio)
├── LICENSE
├── intake.md                  ← Fuente de verdad de /inicio. Editá y re-corré.
├── conexiones.md              ← Registro de cada sistema que tu AIOS alcanza
├── contexto/                  ← Sobre vos y tu negocio (lo completa /inicio)
├── referencias/
│   └── 3ms-framework.md       ← El cerebro operador
├── decisiones/
│   └── registro.md            ← Qué se decidió y por qué
├── archivo/                   ← Cosas viejas. No borrar, mover acá.
└── .claude/skills/
    ├── inicio/  · auditoria/  · subir-nivel/
```

---

## Créditos

Este kit es una adaptación al castellano y al contexto PyME de la metodología de **[Nate Herk](https://www.skool.com/ai-automation-society)** (AI Automation Society).

**Los 3 Ms de la IA™** y **Las 4 Cs de un AIOS™** son marcas registradas de Nate Herk (© 2026 Nate Herk). Se usan en este kit con atribución. No son creación de Seneca AI.

## Licencia

[MIT](LICENSE). Usalo, modificalo y compartilo libremente. Mantené la atribución de los frameworks.

---

<div align="center">

Hecho por **[Seneca AI](#)** — automatización con IA para PyMEs.

_¿Querés que te ayudemos a montar el tuyo? Escribinos._

</div>
