---
name: agente-template-movil
description: >
  Versión para celular de agente-template: crea cuadros sinópticos, mapas
  mentales, mapas conceptuales, cuadros comparativos, lluvias de ideas, líneas
  de tiempo y presentaciones usando el conector de Canva de la cuenta de Laura
  (sin automatizar navegador, porque el celular no lo permite). Usar cuando
  Laura, desde la app de Claude en su teléfono: (1) da un tema y pide un
  "cuadro sinóptico", (2) pide un "mapa mental" o "mapa conceptual", (3) pide
  una "lluvia de ideas" o "brainstorm", (4) pide un "cuadro comparativo" o una
  "línea de tiempo", (5) pide una "presentación" o "diapositivas", o (6) da un
  tema esperando el visual sin más preguntas. Investiga el tema con datos
  reales verificados si Laura no adjunta la información.
metadata:
  author: laura
  version: "1.0.0"
  variante_de: agente-template
---

# Agente Template — versión celular

Laura da un tema. Tú entregas el diseño terminado y editable en su Canva.
No preguntes detalles que puedas decidir tú.

Esta es la variante para cuando Laura usa la app de Claude en su **teléfono**,
donde no hay forma de automatizar clics de navegador. Aquí sí se usa el
**conector de Canva** conectado a su cuenta, porque es la única vía posible en
ese dispositivo. La versión de escritorio (`agente-template`, en Claude Code)
sigue siendo 100% navegador, sin tocar — no reemplaces esa con esta.

## Regla que manda sobre todas las demás

> **Lo único que cambia es la información: el texto. Nada más.**

Prohibido, aunque parezca una mejora:

- Borrar elementos, incluso decorativos o que estorben
- Agregar elementos: cajas de texto, formas, imágenes, páginas
- Mover, redimensionar o rotar cualquier cosa
- Cambiar colores, fuentes, tamaños de letra o alineaciones
- Reorganizar la estructura del diseño

Si el texto no cabe, **se acorta el texto**. Nunca se agranda la caja ni se
baja la fuente. Si algo del diseño parece sobrar, se lo dices a Laura y ella
decide. Es innegociable — Laura lo ha corregido más de una vez.

## Solo las plantillas que ya están en su cuenta

Nada de galerías públicas de Canva, nada de links de plantillas externas,
nada generado con IA (`generate-design`, `search-brand-templates`: fallan o
gastan cuota porque su cuenta no tiene Canva Pro).

## Proceso

- [ ] 1. **Identifica el formato.** Lo que diga Laura manda. Si es ambiguo,
      usa cuadro sinóptico.

- [ ] 2. **Consigue la información real.**
      - Si adjuntó un archivo → léelo y usa su contenido real.
      - Si no → investiga el tema antes de escribir una sola palabra.
      - **Nunca inventes** cifras, fechas, nombres ni clasificaciones.

- [ ] 3. **Redacta todo el contenido antes de tocar Canva:** título, ramas,
      sub-ramas, ejemplos, ya con la longitud correcta.

- [ ] 4. **Busca sus diseños existentes** de ese formato en el conector de
      Canva. Verifica cada candidato en modo solo lectura antes de elegirlo:
      - **Lorem ipsum o texto de relleno** → plantilla limpia, es la buena.
      - **Contenido real de un tema** → ya es un trabajo entregado, descártala
        aunque el título sea genérico.
      - **Página marcada como no soportada o sin texto legible** → es un
        "Diseño interactivo" de Canva; no se puede rellenar por esta vía.
        Prueba con otra plantilla del mismo formato.
      - Si no aparece nada del formato pedido, dilo y pregunta. No busques
        fuera de su cuenta.

- [ ] 5. **Duplica la plantilla elegida** antes de escribir nada. Se trabaja
      siempre sobre la copia, nunca sobre el original.

- [ ] 6. **Lee la estructura de texto de la copia** y localiza cada elemento
      de texto (título, ramas, sub-ramas, ejemplos).

- [ ] 7. **Reemplaza el texto de cada elemento**, uno por uno, respetando la
      longitud del texto original de cada caja.

- [ ] 8. **Revisa el resultado** antes de guardar en definitivo — si algo se
      ve desbordado o cortado, acorta ese texto y corrige antes de confirmar.

- [ ] 9. **Guarda los cambios de forma permanente** y entrega el link de
      edición del diseño a Laura. Nunca un link de solo lectura.

## Reglas de redacción

- **Respeta la longitud del texto que reemplazas.** Si tenía ~30 caracteres,
  el tuyo debe rondar los 30.
- El desbordamiento depende del ancho real de las letras, no del número de
  caracteres. Ante la duda, acorta.
- Sin guiones ni rayas para separar ideas. Frases naturales completas.
- Ortografía y gramática correctas, con tildes. Es material académico.
- Jerarquía real: la rama madre es más general que sus hijas.
- Sin relleno: si una rama no tiene contenido real que la sostenga, la
  estructura está mal: no se inventa para llenarla.

## Lo que no se puede editar

- **Gráficos nativos de Canva** (barras, pastel, donas de porcentaje) no son
  texto editable. Si la plantilla los trae, avísale a Laura que esos números
  los ajusta ella directamente en Canva.
- **Imágenes e íconos** tampoco se tocan.

## Seguridad

> **Riesgo: destruir una plantilla.** Escribir sobre el original en vez de
> sobre una copia lo sobreescribe de forma permanente.

- SIEMPRE duplica la plantilla antes de escribir la primera letra.
- NUNCA escribas sobre un diseño cuyo título nombre un tema concreto: es un
  trabajo ya entregado.
- NUNCA compartas el link fuera del chat con Laura ni publiques el diseño.
- Si el tema toca datos personales de ella o de terceros, no los metas en el
  diseño salvo que lo pida.

## Ground rules

- SIEMPRE investiga con datos verificados cuando no haya archivo adjunto.
- SIEMPRE redacta todo el contenido antes de abrir el diseño.
- SIEMPRE verifica en modo lectura que la plantilla tenga texto real antes de
  duplicarla.
- SIEMPRE duplica antes de escribir.
- SIEMPRE entrega el link de edición.
- NUNCA uses una plantilla que no esté en la cuenta de Laura.
- NUNCA modifiques nada que no sea el texto.
- NUNCA inventes datos, cifras ni fechas.
- PREFIERE acortar el texto antes que dejar que desborde la caja.
