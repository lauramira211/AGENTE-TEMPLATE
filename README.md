# AGENTE TEMPLATE

Skills para Claude Code.

## Skills

### `agente-template`

Crea cuadros sinópticos, mapas mentales, mapas conceptuales, cuadros
comparativos, lluvias de ideas, líneas de tiempo y presentaciones rellenando
plantillas reales de una cuenta de Canva.

No usa generación por IA: busca los diseños que ya existen en la cuenta
conectada, los copia y reemplaza el texto. Funciona sin Canva Pro.

Investiga el tema con datos verificados antes de escribir contenido.

### `agente-template-movil`

Misma skill, adaptada para usarse desde la app de Claude en el celular. En vez
de navegar y hacer clic en Chrome (imposible en un teléfono), usa el conector
de Canva de la cuenta para leer y reemplazar el texto de las plantillas.

## Instalación — Claude Code (escritorio)

Clona el repo dentro de la carpeta de skills de Claude Code:

```bash
git clone https://github.com/lauramira211/AGENTE-TEMPLATE.git ~/.claude/skills/agente-template-repo
```

O copia solo la skill que necesites:

```bash
cp -r agente-template ~/.claude/skills/
```

**No instales `agente-template-movil` en Claude Code** — es solo para la app
de Claude en el celular, y podría confundirse con la versión de escritorio.

## Instalación — app de Claude (celular)

1. Abre `agente-template-movil/SKILL.md` en este repo desde el navegador del
   teléfono.
2. Copia todo el contenido.
3. En la app de Claude: **Configuración → Customize → Skills → "+" → Create
   skill**.
4. Pega el contenido, dale un nombre y guarda.

## Requisitos

- Claude Code (para `agente-template`) o la app de Claude (para
  `agente-template-movil`)
- Conector de Canva activo en la cuenta
