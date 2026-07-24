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
  version: "2.2.0"
allowed-tools: mcp__7a57a327-7c1e-43ef-8728-d0e55eeaa17c__search-designs mcp__7a57a327-7c1e-43ef-8728-d0e55eeaa17c__copy-design mcp__7a57a327-7c1e-43ef-8728-d0e55eeaa17c__read-design mcp__7a57a327-7c1e-43ef-8728-d0e55eeaa17c__edit-design mcp__7a57a327-7c1e-43ef-8728-d0e55eeaa17c__export-design WebSearch WebFetch Read
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

- [ ] 3b. **Verifica que el diseño se pueda rellenar, ANTES de copiarlo.** Llama
      `read-design` en modo solo lectura (sin `open_transaction`) pidiendo
      `design_content`. Tres resultados posibles:
      - **Lorem ipsum o texto de relleno** → plantilla limpia. Esta es la buena.
      - **Contenido real de un tema** → ya se usó para un trabajo. Descártala
        aunque su título sea genérico.
      - **`design_content` vacío, o la página marcada `(UNSUPPORTED)`** → es un
        "Diseño interactivo" de Canva. Su texto no es texto editable y la API no
        puede tocarlo. **No la copies.** Pasa a la siguiente candidata de la
        cuenta.

      Verificar antes de copiar evita llenar su cuenta de copias inservibles.

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
- **El desbordamiento depende del ancho real de las letras, no del número de
  caracteres.** Dos palabras de igual longitud pueden comportarse distinto:
  "AUTOMATIZA" desbordó donde "RESULTADOS", del mismo largo, cabía. Ante la
  duda, acorta y verifica en el thumbnail del paso 7.
- **Sin guiones ni rayas** para separar ideas. Frases naturales completas.
- **Ortografía y gramática correctas**, con tildes. Es material académico.
- **Jerarquía real:** en un cuadro sinóptico la rama madre es más general que
  sus hijas. No repitas el mismo nivel de detalle en todos los niveles.
- **Sin relleno.** Si una rama no tiene contenido real que la sostenga, es señal
  de que la estructura está mal, no de que falte inventar.

## Lo que no se puede editar

- **Gráficos nativos de Canva** (barras, pastel, dona de porcentajes) son
  invisibles para esta API: sus etiquetas, valores y fuente no se pueden leer ni
  editar. Si la plantilla los trae, o eliges otra plantilla, o dejas el gráfico
  y avisas a Laura que esos números los ajusta ella en la tabla de datos del
  gráfico, dentro de Canva.
- **Imágenes e íconos** tampoco. Solo se reemplaza texto.

> **Nunca borres un elemento gráfico.** Ni formas decorativas, ni íconos, ni
> gráficos que no puedas editar. Lo único que cambia entre la plantilla y la
> entrega es el contenido del tema. Si algo estorba, dilo y que Laura decida.

### Si trabajas por el navegador

En los diseños tipo pizarra, **un doble clic que cae en zona vacía crea una nota
adhesiva** con lo que escribas después. Eso es agregar un elemento, o sea está
prohibido. Antes de escribir, confirma con una captura que el cursor entró en
una caja de texto existente. Una caja a la vez, verificando. Si aparece un
elemento que tú creaste sin querer, díselo a Laura de inmediato: borrarlo
requiere su permiso.

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

## Cuando ninguna plantilla de la cuenta se puede rellenar

Puede pasar que el formato pedido solo exista en su cuenta como "Diseño
interactivo". En ese caso:

- **No busques plantillas fuera de su cuenta.** Ni galerías públicas de Canva,
  ni links de plantillas, ni `generate-design`. El material de trabajo son sus
  diseños y nada más.
- **El navegador ya no es salida.** Canva rechaza el navegador automatizado con
  "Actualiza tu navegador" y congela el editor. Verificado el 2026-07-24. No
  prometas rellenarlo por ahí.
- **Lo que sí haces:** entrégale el contenido ya investigado y redactado, caja
  por caja, para que ella lo pegue abriendo la plantilla en su propio Chrome.
  El trabajo de investigación y redacción no se pierde.

## Ground rules

- SIEMPRE investiga con `WebSearch` cuando no haya archivo adjunto.
- SIEMPRE entrega el `edit_url`.
- SIEMPRE verifica que el diseño exponga texto antes de copiarlo.
- SIEMPRE copia antes de editar.
- NUNCA uses una plantilla que no esté en la cuenta de Canva de Laura.
- NUNCA llames `generate-design`, `generate-design-structured`,
  `search-brand-templates` ni `create-design-from-brand-template` — no funcionan
  sin Pro o gastan cuota.
- NUNCA inventes datos, cifras ni fechas.
- NUNCA preguntes por el formato si Laura ya lo dijo o si se infiere del fraseo.
- PREFIERE acortar el texto antes que dejar que desborde la caja.
