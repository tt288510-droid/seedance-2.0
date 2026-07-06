# Seedance 2.0 Skill OS — Guía rápida

> Versión 6.6.0 · De la instalación a tu primer prompt "dirigido" en unos 5 minutos.
> Documentación completa: [README](../README.md).

## Qué es esto

Seedance 2.0 Skill OS es un agent skill que dirige Seedance 2.0 como un cineasta en lugar de acumular adjetivos. Una sola regla: **dirige el modelo, no microgestiones el encuadre.** Describe lo que la escena está *haciendo* y la skill compila esa intención en un prompt listo para producción.

## 1. Instalación (unos 5 minutos)

Instala este repositorio como **una** skill raíz llamada `seedance-20`; sus sub-skills y references se cargan por ruta relativa.

**Codex (tiene instalador de un comando):**

```bash
python scripts/install_codex_skill.py --force
```

Copia el repo a `~/.codex/skills/seedance-20` (o `$CODEX_HOME/skills/seedance-20`). Reinicia Codex y llama a `$seedance-20`.

**Instalar desde GitHub (si tu cliente admite instalación por URL de repositorio):**

```text
https://github.com/Emily2040/seedance-2.0
```

**Copia manual (otros clientes):** copia la carpeta en el directorio de skills de tu cliente, manteniendo el nombre `seedance-20`. Los destinos habituales —verifícalos en tu propio cliente, no son una garantía— están en la [tabla de instalación del README](../README.md#install): p. ej. Claude Code `.claude/skills/`, Cursor `.cursor/skills/`, GitHub Copilot `.github/skills/`, Windsurf `.windsurf/skills/`.

> Seguridad primero: instálalo solo en clientes de agente en los que confíes. Lee [SECURITY.md](../SECURITY.md) antes de usar esta skill en un agente ajeno o desconocido.

## 2. Elige la skill según tu situación

| Tienes… | Carga primero |
|---|---|
| una idea vaga | `seedance-interview` |
| una escena clara | `seedance-prompt` |
| una historia de varios clips | `seedance-sequence` |
| un clip aceptado que continuar | `seedance-continuation` |
| un resultado malo o bloqueado | `seedance-troubleshoot` |
| un personaje, marca, celebridad o persona real | `seedance-copyright` |

## 3. Dirige antes de escribir — cuatro preguntas

1. **¿Qué está haciendo la escena?** ¿Un giro, una revelación, una emoción, una demostración?
2. **¿Cómo lo dice la cámara?** Plano general para el aislamiento, primer plano para el rostro, un travelling de acercamiento para la revelación.
3. **¿Qué hace la luz?** Hora del día, dura o suave, cálida o fría — al servicio de la intención.
4. **¿Qué hace el sonido?** Casi silencio, un detalle de ambiente, o una línea de diálogo.

## 4. Un ejemplo

**Decorado (débil):**

```
plano épico y cinematográfico de una mujer leyendo una carta, emotivo, iluminación hermosa, 4K
```

**Dirigido (fuerte):**

```
Plano medio corto, a la altura de los ojos; baja la carta y sus manos se detienen mientras llega un lento acercamiento; una luz de ventana suave mantiene su rostro sobrio; casi silencio con el roce de una silla.
```

## 5. Dos reglas que ahorran tomas

- **Conserva las etiquetas de referencia tal cual** — `[Image1]`, `[Video1]`, `[Audio1]`, `@图1`, `@视频1`. Nunca las traduzcas ni las reformatees.
- **No pidas toda la historia en una sola generación.** Genera el Clip 01, observa cómo terminó *realmente* y luego escribe el Clip 02 desde ese final real (`seedance-continuation`).

## 6. Seguridad

- **Seguridad de contenido:** si tu idea usa un personaje protegido, una celebridad, una marca, un logo, una canción o el rostro o la voz de una persona real, no lo escondas en otro idioma: reescríbelo en un equivalente original, con licencia o de posproducción con `seedance-copyright`.
- **Seguridad del agente:** este paquete **no hace llamadas de red ni incluye telemetría**; sus scripts son deterministas y funcionan sin conexión. Nunca pegues claves de API, cookies de cuenta ni material privado en un agente en el que no confíes. Consulta [SECURITY.md](../SECURITY.md).

## 7. Profundiza

- `references/directing-engine.md` — lee la escena y elige una sola intención (35 géneros trabajados).
- `references/capability-map.md` — diseña según las fortalezas del modelo y evita sus límites conocidos.
- `references/api-workflow.md` — API, proveedores, precios, IDs de modelo (con fecha de fuente).
- `references/examples-by-mode.md` — ejemplos de T2V, I2V, V2V, R2V, FLF2V, edición y extensión.

---

Otros idiomas: [English](QUICKSTART.md) · [中文](QUICKSTART.zh.md) · [日本語](QUICKSTART.ja.md) · [한국어](QUICKSTART.ko.md) · [Русский](QUICKSTART.ru.md)
