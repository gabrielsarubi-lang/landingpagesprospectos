# Flujo profesional en 3 pasos

El prompt largo (`extraccion-perfil-instagram.md`) sirve como referencia de TODO lo que hay que
relevar, pero en la práctica conviene partirlo. Un prompt que pide ocho bloques a la vez suele
quedarse sin turno antes de entregar. Estos tres pasos entregan cada uno un resultado usable.

**Regla de oro: un prospecto = un chat nuevo.** No mezcles dos perfiles en la misma conversación.

---

## Paso 0 — Juntar el material (5 minutos, sin IA)

Claude no entra a Instagram: los perfiles exigen sesión iniciada. Todo sale de lo que le adjuntes.

Descargá y tené listo:

1. Captura de la cabecera del perfil (foto, nombre, bio, link, seguidores).
2. Capturas de la grilla (2 o 3 pantallazos para ver ~18 posts).
3. Captura de los highlights.
4. La foto de perfil en la mayor resolución que consigas → de acá salen el logo y la paleta.
5. Las descripciones (captions) de 5 a 8 posts, copiadas como texto.

Si algo no lo tenés, avisale en el prompt. No lo dejes adivinar.

---

## Paso 1 — Relevamiento de datos

> Adjuntá las capturas en este mismo mensaje.

```
Te adjunto capturas del perfil de Instagram @USUARIO.

Trabajá SOLO con lo que se ve en las imágenes y en el texto que te paso. No busques en internet
y no completes nada de memoria. Lo que no esté visible, escribilo como "NO FIGURA".

Devolveme una ficha con estos puntos, en este orden:

1. Nombre del negocio y rubro
2. Qué vende exactamente (detallado)
3. Bio transcrita tal cual
4. Productos o servicios, con precio SOLO si está publicado
5. Zona donde trabaja / si es online o presencial
6. Contacto: WhatsApp, teléfono, email, dirección, link de la bio
7. Cómo compra el cliente hoy (DM, WhatsApp, tienda, reserva)
8. Prueba social: testimonios, antes/después, cantidad de clientes, premios
9. Seguidores y con qué frecuencia publica

Al final, listame las preguntas que me quedan pendientes para hacerle al dueño.
```

**Lo que tenés que revisar antes de seguir:** que no haya inventado un teléfono, un precio ni una
dirección. Si ves un dato que no estaba en las capturas, corregilo ahí mismo antes del paso 2.

---

## Paso 2 — Identidad visual

> Adjuntá de nuevo la foto de perfil en alta y 4 o 5 posts representativos.

```
Con estas imágenes del perfil @USUARIO, armame la guía visual de la marca:

1. LOGO: describí la foto de perfil (¿es un símbolo, el nombre escrito, o las dos cosas?),
   colores, si tiene bajada de texto. Decime si sirve como logo para una web o si conviene
   rehacerlo, y por qué.
2. PALETA: 4 o 5 colores en código HEX sacados de las imágenes, y para qué sirve cada uno
   (color principal, botones, fondo, texto). Avisame si algún par no se lee bien por contraste.
3. TIPOGRAFÍA: qué estilo de letra usa y recomendame 2 fuentes de Google Fonts parecidas,
   una para títulos y otra para textos.
4. ESTILO DE FOTOS: iluminación, si aparecen personas, fondos, nivel de producción.
5. TONO DE VOZ: 4 adjetivos y una regla de "esto sí / esto no" para escribir textos.
6. QUÉ FOTOS DEL PERFIL SIRVEN PARA LA WEB: listalas y decime en qué sección iría cada una,
   y cuáles no sirven (baja calidad, marca de agua, texto encima).
```

---

## Paso 3 — Estructura y textos de la landing

> Pegale la ficha del Paso 1 y la guía del Paso 2.

```
Te paso el relevamiento y la identidad visual de @USUARIO (van abajo).

Armame la landing page de este negocio. Objetivo: que el visitante escriba por WhatsApp.

Dame la estructura sección por sección y, en cada una, el TEXTO FINAL listo para publicar
(no me digas "acá iría el título", escribime el título).

Necesito:
- Título principal con 3 variantes para elegir
- Subtítulo
- 4 a 6 beneficios en formato de bullet
- Sección "quiénes somos" o "sobre el servicio"
- Sección de testimonios (usando los reales del relevamiento)
- 5 preguntas frecuentes con su respuesta
- Textos de los botones
- El mensaje que se autocompleta al abrir el WhatsApp
- Título SEO (máximo 60 caracteres) y descripción SEO (máximo 155)

Escribí en el mismo tono que usa la marca. No prometas resultados ni garantías que no estén
respaldados en el material; si algo así hace falta, marcámelo aparte para que lo valide el dueño.

--- RELEVAMIENTO ---
(pegar acá el resultado del Paso 1)

--- IDENTIDAD VISUAL ---
(pegar acá el resultado del Paso 2)
```

---

## Paso 4 (opcional) — La web armada

```
Con todo lo anterior, generame la landing en un archivo HTML con Tailwind, mobile first,
usando la paleta y las fuentes indicadas. El botón principal tiene que abrir
https://wa.me/NUMERO con el mensaje ya escrito. Dejá los espacios de las imágenes marcados
con un comentario que diga qué foto va en cada uno.
```

---

## Si se queda pensando y no entrega

- Escribile: **"Pará y devolveme lo que tengas hasta ahora, aunque esté incompleto."**
- Chequeá que las capturas se hayan adjuntado de verdad en el mensaje.
- Si el paso sigue sin salir, partilo: pedile primero los puntos 1 a 5, y después el resto.
