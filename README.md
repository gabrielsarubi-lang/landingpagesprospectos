# Landing pages para prospectos

Prompts y plantillas para pasar de un perfil de Instagram a una landing page lista para vender.

## Contenido

- `prompts/extraccion-perfil-instagram.md` — prompt principal: extrae identidad de marca, logo,
  paleta, oferta, prueba social, contacto y devuelve un brief en JSON + copy de landing.
- `schemas/brief-landing.example.json` — esqueleto del JSON que devuelve ese prompt, para validar
  la salida o usarlo como entrada de la etapa de generación.

## Flujo

1. Juntar capturas del perfil (cabecera, grilla, highlights, posts y foto de perfil en alta).
2. Correr el prompt de extracción → brief JSON + preguntas pendientes para el dueño.
3. Completar los `datos_faltantes` con el prospecto.
4. Generar la landing a partir del JSON.
