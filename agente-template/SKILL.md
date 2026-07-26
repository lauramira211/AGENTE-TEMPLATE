---
name: agente-template
description: >
  Crea cuadros sinópticos, mapas mentales, mapas conceptuales, cuadros
  comparativos, lluvias de ideas, líneas de tiempo y presentaciones entrando a la
  cuenta de Canva de Laura por el navegador y reemplazando el texto de las
  plantillas que ella ya tiene ahí. Usar cuando Laura: (1) da un tema y pide un
  "cuadro sinóptico", (2) pide un "mapa mental" o "mapa conceptual", (3) pide una
  "lluvia de ideas" o "brainstorm", (4) pide un "cuadro comparativo" o una "línea
  de tiempo", (5) pide una "presentación" o "diapositivas", o (6) da un tema
  esperando el visual sin más preguntas. Investiga el tema con datos reales
  verificados si Laura no adjunta la información.
metadata:
  author: laura
  version: "3.0.0"
allowed-tools: mcp__claude-in-chrome__navigate mcp__claude-in-chrome__computer mcp__claude-in-chrome__browser_batch mcp__claude-in-chrome__read_page mcp__claude-in-chrome__find mcp__claude-in-chrome__tabs_context_mcp WebSearch WebFetch Read
---

# Cuadros sinópticos y diagramas en Canva

Laura da un tema. Tú entregas el diseño terminado y editable en su Canva.
No preguntes detalles que puedas decidir tú.

## Regla que manda sobre todas las demás

> **Lo único que cambia es la información: el texto. Nada más.**

Prohibido, aunque parezca una mejora:

- Borrar elementos, incluso decorativos o que estorben
- Agregar elementos: cajas de texto, notas adhesivas, formas, imágenes, páginas
- Mover, redimensionar o rotar cualquier cosa
- Cambiar colores, fuentes, tamaños de letra o alineaciones
- Reorganizar la estructura del diseño

Si el texto no cabe, **se acorta el texto**. Nunca se agranda la caja ni se baja
la fuente. Si algo del diseño parece sobrar, se lo dices a Laura y ella decide.

Laura ha corregido este punto dos veces. Es innegociable.

## Cómo se trabaja: navegador, no API

Se entra a la cuenta de Canva de Laura **por su Chrome conectado**
(`mcp__claude-in-chrome__*`), donde su sesión ya está iniciada. Se abre la
plantilla, se escribe encima del texto, y listo.

**No uses el conector de Canva** (`read-design`, `edit-design`, `copy-design`,
`generate-design`, `search-designs`, `search-brand-templates`). Laura lo pidió
explícitamente tres veces. Además su cuenta no tiene Pro, así que lo de generar
con IA ni siquiera funciona y gasta cuota.

**Solo se usan las plantillas que ya están en su cuenta.** Nada de galerías
públicas de Canva, nada de links de plantillas externas, nada generado con IA.

## Proceso

- [ ] 1. **Identifica el formato.** Lo que diga Laura manda sobre cualquier
      inferencia. Si de verdad es ambiguo, usa cuadro sinóptico.

- [ ] 2. **Consigue la información real.**
      - Si adjuntó un archivo → léelo con `Read` (sirve con texto, PDF e
        imágenes). Su contenido manda sobre tu conocimiento general.
      - Si no adjuntó nada → `WebSearch` obligatorio antes de escribir una sola
        palabra de contenido.
      - **Nunca inventes** cifras, fechas, nombres ni clasificaciones. Esto lo
        revisan profesores. Un dato inventado es peor que no entregar nada.

- [ ] 3. **Redacta todo el contenido antes de abrir el navegador.** Arma la
      jerarquía completa en texto: título central, ramas, sub-ramas y ejemplos,
      ya con la longitud correcta. Entrar a Canva a improvisar redacción es como
      se cometen errores.

- [ ] 4. **Entra a sus diseños.** Navega a `https://www.canva.com/projects` y
      busca una plantilla del formato pedido. Reconoce cuál sirve:
      - **Lorem ipsum o texto de relleno** → plantilla limpia. Esta es la buena.
      - **Contenido real de un tema** → ya se usó para un trabajo. Descártala,
        aunque su título sea genérico.
      - Si no encuentras nada del formato pedido, dilo y pregunta. No busques
        fuera de su cuenta.

- [ ] 5. **Duplica la plantilla antes de escribir.** En el editor:
      `Archivo` → `Hacer una copia`. Se trabaja sobre la copia, **nunca sobre la
      plantilla original**, o se pierde para siempre.

- [ ] 6. **Reemplaza el texto, una caja a la vez.** Para cada caja:
      doble clic encima → `Ctrl+A` → escribir el texto nuevo → `Escape`.
      **Toma una captura entre caja y caja** y confirma que el texto entró donde
      debía antes de seguir con la siguiente. Ver las trampas de abajo.

- [ ] 7. **Revisa el resultado completo** con una captura final. Si hay texto
      desbordado o cortado, acorta ese texto y reescríbelo.

- [ ] 8. **Entrega el link de edición** del diseño (`canva.com/design/...`),
      nunca el de solo lectura. Laura necesita poder editarlo.

## Trampas del navegador

Aprendidas a la mala. Respétalas o se rompe la regla de no modificar la
plantilla.

> **Un doble clic que cae en zona vacía crea una nota adhesiva.** En los diseños
> tipo pizarra, si el cursor no entra en una caja de texto existente, Canva crea
> un elemento nuevo con lo que escribas. Eso es agregar un elemento, o sea está
> prohibido. Por eso se verifica con captura caja por caja.

- **Si creas un elemento sin querer, díselo a Laura de inmediato.** Borrarlo
  requiere su permiso, y ella lo hace en dos segundos.
- **El editor se congela a veces.** Si la captura falla con "renderer frozen",
  espera unos segundos y vuelve a capturar. **No repitas clics a ciegas** — es
  así como aparecen elementos basura.
- **Los "Diseño interactivo" no se pueden abrir.** Canva responde "Actualiza tu
  navegador" y bloquea el editor, aunque el Chrome esté al día. Si una plantilla
  hace eso, no insistas: elige otra del mismo formato en su cuenta.
- **Los gráficos nativos** (barras, pastel, donas de porcentaje) no son texto.
  No los toques. Si la plantilla los trae, avísale a Laura que esos números los
  ajusta ella en la tabla de datos del gráfico.

## Reglas de redacción

El texto va dentro de cajas de tamaño fijo. La plantilla no crece.

- **Respeta la longitud del texto que reemplazas.** Si tenía ~30 caracteres, el
  tuyo debe rondar los 30.
- **El desbordamiento depende del ancho real de las letras, no del número de
  caracteres.** "AUTOMATIZA" desbordó donde "RESULTADOS", del mismo largo,
  cabía. Ante la duda, acorta.
- **Sin guiones ni rayas** para separar ideas. Frases naturales completas.
- **Ortografía y gramática correctas**, con tildes. Es material académico.
- **Jerarquía real:** la rama madre es más general que sus hijas. No repitas el
  mismo nivel de detalle en todos los niveles.
- **Sin relleno.** Si una rama no tiene contenido real que la sostenga, la
  estructura está mal; no se inventa para llenarla.

## Seguridad

> **Riesgo: destruir una plantilla.** Escribir sobre el original en vez de sobre
> una copia lo sobreescribe de forma permanente.

- SIEMPRE `Archivo` → `Hacer una copia` antes de escribir la primera letra.
- NUNCA escribas sobre un diseño cuyo título nombre un tema concreto: es un
  trabajo ya entregado.
- NUNCA compartas el link fuera del chat con Laura ni publiques el diseño.
- Si el tema toca datos personales de ella o de terceros, no los metas en el
  diseño salvo que lo pida.

## Ground rules

- SIEMPRE investiga con `WebSearch` cuando no haya archivo adjunto.
- SIEMPRE redacta todo el contenido antes de abrir Canva.
- SIEMPRE duplica la plantilla antes de escribir.
- SIEMPRE verifica con captura entre caja y caja.
- SIEMPRE entrega el link de edición.
- NUNCA uses el conector de Canva ni ninguna API.
- NUNCA uses una plantilla que no esté en la cuenta de Laura.
- NUNCA modifiques nada que no sea el texto.
- NUNCA inventes datos, cifras ni fechas.
- PREFIERE acortar el texto antes que dejar que desborde la caja.
