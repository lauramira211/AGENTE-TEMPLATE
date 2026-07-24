---
name: cuadros-sinopticos
description: >
  Crea cuadros sinópticos, mapas mentales, mapas conceptuales, cuadros
  comparativos, lluvias de ideas, líneas de tiempo y presentaciones rellenando
  los diseños que Laura ya tiene en su cuenta de Canva. Usar cuando Laura:
  (1) da un tema y pide un "cuadro sinóptico", (2) pide un "mapa mental" o
  "mapa conceptual", (3) pide una "lluvia de ideas" o "brainstorm",
  (4) pide un "cuadro comparativo" o una "línea de tiempo", (5) pide una
  "presentación" o "diapositivas", o (6) da un tema esperando el visual sin
  más preguntas. Investiga el tema con datos reales si Laura no adjunta la
  información.
metadata:
  author: laura
  version: "2.0.0"
allowed-tools: mcp__7a57a327-7c1e-43ef-8728-d0e55eeaa17c__search-designs mcp__7a57a327-7c1e-43ef-8728-d0e55eeaa17c__copy-design mcp__7a57a327-7c1e-43ef-8728-d0e55eeaa17c__read-design mcp__7a57a327-7c1e-43ef-8728-d0e55eeaa17c__edit-design mcp__7a57a327-7c1e-43ef-8728-d0e55eeaa17c__export-design WebSearch WebFetch Read
---

# Cuadros sinópticos y diagramas en Canva

Laura da un tema. Tú entregas el diseño terminado y editable en su Canva.
No preguntes detalles que puedas decidir tú.

## Cómo funciona su cuenta

Su cuenta **no tiene Canva Pro**. Eso descarta dos caminos:

- `search-brand-templates` y `create-design-from-brand-template` → fallan con
  "requires a Canva paid plan".
- `generate-design` y `generate-design-structured` → gastan cuota de generación
  y producen resultados que no respetan sus plantillas.

**El camino que sí funciona:** ella ya duplicó a su cuenta una biblioteca de
plantillas gratuitas, una por cada formato. Esos diseños son el material de
trabajo. Se buscan en vivo, se copian, y se rellenan.

## Proceso

- [ ] 1. **Identifica el formato.** Lo que diga Laura manda sobre cualquier
      inferencia. Si de verdad es ambiguo, usa cuadro sinóptico.

- [ ] 2. **Consigue la información real.**
      - Si adjuntó un archivo → léelo con `Read` (funciona con texto, PDF e
        imágenes). Su contenido manda sobre tu conocimiento general.
      - Si no adjuntó nada → `WebSearch` obligatorio antes de escribir una sola
        palabra de contenido.
      - **Nunca inventes** cifras, fechas, nombres ni clasificaciones. Esto lo
        revisan profesores del SENA y la Universidad del Rosario. Un dato
        inventado es peor que no entregar el diagrama.

- [ ] 3. **Busca el diseño base en su cuenta** con `search-designs`
      (`ownership: "owned"`, `sort_by: "relevance"`) usando el nombre del
      formato como `query`: `"cuadro sinóptico"`, `"mapa conceptual"`,
      `"mapa mental lluvia de ideas"`, `"cuadro comparativo"`,
      `"línea de tiempo"`, `"presentación"`.
      - Elige el que mejor calce con la estructura del contenido (número de
        ramas, número de slides).
      - **Descarta los que ya son trabajos terminados** — se reconocen porque
        el título nombra un tema concreto en vez de un estilo. Ejemplo:
        "Cuadro sinóptico - Alternativas etapa productiva SENA" es un trabajo
        entregado; "Gráfica Cuadro Sinóptico Moderno Colorido" es plantilla.
      - Si no aparece nada del formato pedido, dilo y pregunta cuál usar. No
        inventes un diseño ni recurras a `generate-design`.

- [ ] 4. **Copia el diseño** con `copy-design`. Trabaja siempre sobre la copia.
      Titula la copia con el tema real, no con el nombre de la plantilla.

- [ ] 5. **Lee la estructura de la copia** con `read-design`
      (`open_transaction: true`, `fields: ["design_content", "thumbnails"]`).
      Devuelve el `transaction_id` y el contenido en markdown, donde cada caja
      de texto viene anotada con su `[locator_id]` (formato `PBxxx-LByyy`).
      Ese locator_id es el `element_id` que vas a usar.

- [ ] 6. **Rellena** con `edit-design`, pasando `transaction_id`, `page_index` y
      un `operations: [{type: "replace_text", element_id, text}]` por cada
      locator_id. Respeta las reglas de redacción de abajo.

- [ ] 7. **Revisa antes de guardar.** Vuelve a llamar `read-design` con el mismo
      `transaction_id` y `filter.fields: ["thumbnails"]` para ver el resultado
      sin confirmar. Si hay texto desbordado o cortado, acorta y repite el
      paso 6.

- [ ] 8. **Guarda** con `edit-design`, mismo `transaction_id`, sin operaciones y
      `finalize: "commit"`. Si algo salió mal y hay que descartar,
      `finalize: "cancel"`.

- [ ] 9. **Entrega el `edit_url`**, nunca el `view_url`. El view_url no le sirve
      porque no puede editarlo.

## Reglas de redacción

El texto va dentro de cajas de tamaño fijo. La plantilla no crece.

- **Respeta la longitud del placeholder original.** Si el texto que reemplazas
  tenía ~30 caracteres, el tuyo debe rondar los 30. Pasarse desborda la caja o
  encoge la fuente hasta volverla ilegible.
- **Sin guiones ni rayas** para separar ideas. Frases naturales completas.
- **Ortografía y gramática correctas**, con tildes. Es material académico.
- **Jerarquía real:** en un cuadro sinóptico la rama madre es más general que
  sus hijas. No repitas el mismo nivel de detalle en todos los niveles.
- **Sin relleno.** Si una rama no tiene contenido real que la sostenga, es señal
  de que la estructura está mal, no de que falte inventar.

## Lo que no se puede editar

- **Gráficos nativos de Canva** (barras, pastel, porcentajes) no son texto y no
  se editan con `replace_text`. Si la plantilla los trae, o eliges otra
  plantilla, o dejas el gráfico y avisas a Laura que ese elemento lo ajusta ella
  a mano.
- **Imágenes e íconos** tampoco. Solo se reemplaza texto.

## Seguridad

> **Riesgo: destruir una plantilla.** Editar un diseño sin copiarlo primero
> sobreescribe el original de forma permanente. Canva no tiene deshacer entre
> sesiones para esto.

- SIEMPRE `copy-design` antes de cualquier `edit-design`.
- NUNCA edites un diseño cuyo título nombre un tema concreto — es un trabajo ya
  entregado, no una plantilla.
- NUNCA uses `export-design` para publicar ni compartas links fuera del chat con
  Laura. El `edit_url` da acceso de edición a quien lo tenga.
- Si el tema incluye datos personales de Laura o de terceros, no los metas en el
  diseño sin que ella lo pida explícitamente.

## Ground rules

- SIEMPRE investiga con `WebSearch` cuando no haya archivo adjunto.
- SIEMPRE entrega el `edit_url`.
- SIEMPRE copia antes de editar.
- NUNCA llames `generate-design`, `generate-design-structured`,
  `search-brand-templates` ni `create-design-from-brand-template` — no funcionan
  sin Pro o gastan cuota.
- NUNCA inventes datos, cifras ni fechas.
- NUNCA preguntes por el formato si Laura ya lo dijo o si se infiere del fraseo.
- PREFIERE acortar el texto antes que dejar que desborde la caja.
