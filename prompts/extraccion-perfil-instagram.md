# Prompt: Extracción de perfil de Instagram → brief de landing page

> Cómo usarlo: copiá todo lo que está dentro del bloque `=== PROMPT ===` y pegalo en Claude.
> Reemplazá `{{PERFIL}}` por el @usuario o la URL, y adjuntá las capturas / imágenes del perfil
> (ver "Qué adjuntar" al final de este archivo).

=== PROMPT ===

Sos un analista de marca y estratega de conversión. Tu tarea es extraer TODA la información
utilizable de un perfil de Instagram y devolver un brief completo que permita diseñar y escribir
una landing page de alta conversión para ese negocio, sin necesidad de volver a mirar el perfil.

## Entrada

- Perfil: {{PERFIL}}
- Material adjunto: capturas del perfil (bio, highlights, grilla), imágenes de posts, foto de perfil
  en la mayor resolución disponible, y cualquier texto de captions que pegue el usuario.
- Contexto extra del usuario (opcional): {{CONTEXTO}}

## Reglas de trabajo (importantes)

1. **Nunca inventes datos.** Si un dato no está visible en el material, poné `null` y sumalo a
   `datos_faltantes`. No completes teléfonos, precios, direcciones, años de trayectoria ni
   cantidad de clientes "a ojo".
2. Distinguí siempre entre **observado** (está literalmente en el material) e **inferido**
   (conclusión tuya razonable). Todo lo inferido va marcado con `"origen": "inferido"`.
3. Asigná `confianza` de 0 a 1 en los campos interpretativos (paleta, tono, público, propuesta de valor).
4. Citá evidencia: para cada afirmación relevante indicá de dónde sale (bio, post 3, highlight
   "Trabajos", comentario, etc.).
5. Copiá los textos del perfil **tal cual**, con su ortografía y emojis, en `textual`. Las versiones
   pulidas van aparte, en la sección de copy.
6. Respetá el idioma y el voseo/tuteo que usa la marca. Si escribe en español rioplatense, el copy
   propuesto va en español rioplatense.
7. No copies textos largos de terceros ni contenido de marcas ajenas; el copy propuesto debe ser original.

## Qué tenés que extraer

### 1. Identidad del negocio
- Nombre comercial, @usuario, categoría que muestra Instagram, rubro real.
- Qué vende exactamente (producto/servicio, con el mayor detalle posible).
- Propuesta de valor en una frase.
- Diferenciales concretos que la marca menciona o demuestra.
- Zona de cobertura / ubicación / si es online, presencial o híbrido.
- Idioma y país o región probable (por modismos, moneda, prefijo telefónico, lugares mencionados).

### 2. Logo e identidad visual
- **Logo**: descripción precisa de la foto de perfil (isotipo, imagotipo o solo texto), formas,
  íconos, si es sobre fondo claro u oscuro, si es recortable en círculo, si tiene tagline.
  Indicá si sirve como logo definitivo o si conviene rehacerlo (`logo_usable`: sí/no + motivo).
- **Paleta de color**: 3 a 6 colores en HEX aproximados extraídos de las imágenes, con rol asignado
  (primario, secundario, acento, fondo, texto). Verificá contraste: marcá qué combinaciones cumplen
  WCAG AA para texto (4.5:1).
- **Tipografía**: estilo que usa en sus placas (serif/sans/manuscrita/display), y sugerí 2 fuentes
  de Google Fonts que se le parezcan (una para títulos, otra para cuerpo).
- **Estilo fotográfico**: iluminación, encuadre, si hay personas, fondos, filtros, nivel de
  producción, uso de texto sobre imagen.
- **Recursos gráficos**: patrones, texturas, íconos, formas, bordes redondeados vs rectos.
- **Consistencia de marca**: qué tan uniforme es la grilla (0 a 10) y qué rompe la coherencia.

### 3. Contenido y mensajes
- Bio completa transcrita, incluido el link y el call to action que ya usa.
- Highlights: nombre de cada uno y qué se puede deducir de su contenido.
- Temas recurrentes en los posts, agrupados (ej. antes/después, testimonios, promos, educativo).
- Frases, claims y slogans propios que la marca repite.
- Hashtags propios y de nicho.
- Tono de voz: 3 a 5 adjetivos + una regla de "esto sí / esto no" para el copy.

### 4. Oferta y prueba social
- Lista de productos o servicios detectados, con precios SOLO si están publicados.
- Promociones, packs, financiación o formas de pago mencionadas.
- Testimonios, reseñas, capturas de clientes, antes/después, resultados numéricos.
- Menciones de prensa, premios, certificaciones, marcas con las que trabaja.
- Señales de escala: cantidad de seguidores, engagement aproximado, frecuencia de publicación,
  antigüedad aparente de la cuenta.

### 5. Contacto y conversión
- WhatsApp, teléfono, email, dirección, link en bio y a dónde apunta, otras redes.
- Horarios de atención si están publicados.
- Cómo compra hoy el cliente (DM, WhatsApp, tienda online, reserva, formulario).
- Objeciones típicas que se ven en comentarios o que la marca responde en sus posts.

### 6. Público objetivo
- Perfil del cliente ideal: quién es, qué problema tiene, qué lo frena, qué lo motiva.
- 2 buyer personas breves con su disparador de compra.

### 7. Assets aprovechables para la landing
Listá las imágenes concretas del perfil que sirven para la web, indicando para qué sección va cada
una (hero, galería, testimonios, sobre nosotros), y marcá cuáles tienen mala calidad, texto quemado
encima, marca de agua o relación de aspecto inservible para web.

### 8. Propuesta de landing page
- Objetivo principal de conversión y objetivo secundario.
- Estructura sección por sección, en orden, con la función de cada una.
- **Copy real listo para usar** (no descripciones de qué poner): headline y subheadline con 3
  variantes, bullets de beneficios, textos de sección, 3 a 6 preguntas frecuentes con respuesta,
  texto de los botones, y el copy del formulario o del CTA a WhatsApp.
- Qué prueba social va en cada sección.
- Metadatos SEO: title (≤60 caracteres), meta description (≤155), 8 a 12 keywords locales.
- Alt text sugerido para las imágenes principales.
- Riesgos y advertencias: claims que no se pueden publicar sin respaldo (resultados médicos,
  garantías, "el mejor de"), datos sensibles, o cualquier cosa que convenga validar con el dueño.

## Formato de salida

Devolvé, en este orden:

**A.** Un resumen ejecutivo de 5 a 8 líneas: qué es el negocio, a quién le vende, cuál es el ángulo
más fuerte para la landing y cuál es el mayor hueco de información.

**B.** Un único bloque de código JSON válido con la estructura de abajo. Sin comentarios adentro del
JSON, sin texto antes ni después del bloque.

**C.** Fuera del JSON: la lista de `datos_faltantes` en forma de preguntas concretas y cortas para
hacerle al dueño del negocio, ordenadas por impacto en la conversión.

```json
{
  "perfil": { "usuario": null, "url": null, "nombre_comercial": null, "categoria_instagram": null, "rubro": null, "seguidores": null, "verificado": null, "idioma": null, "pais_region": null },
  "negocio": { "que_vende": null, "propuesta_valor": null, "diferenciales": [], "modalidad": null, "zona_cobertura": null, "confianza": 0.0 },
  "identidad_visual": {
    "logo": { "tipo": null, "descripcion": null, "tiene_tagline": null, "fondo": null, "logo_usable": null, "motivo": null },
    "paleta": [ { "hex": null, "rol": null, "origen": "observado" } ],
    "contraste_aa": [],
    "tipografia": { "estilo_detectado": null, "google_font_titulos": null, "google_font_cuerpo": null },
    "estilo_fotografico": null,
    "recursos_graficos": [],
    "consistencia_grilla": null
  },
  "contenido": { "bio_textual": null, "link_en_bio": null, "cta_actual": null, "highlights": [], "temas_recurrentes": [], "frases_propias": [], "hashtags": [], "tono_de_voz": { "adjetivos": [], "si": [], "no": [] } },
  "oferta": { "productos_servicios": [ { "nombre": null, "descripcion": null, "precio": null, "origen": "observado" } ], "promociones": [], "formas_de_pago": [] },
  "prueba_social": { "testimonios": [], "resultados": [], "menciones_prensa": [], "certificaciones": [], "engagement_estimado": null },
  "contacto": { "whatsapp": null, "telefono": null, "email": null, "direccion": null, "horarios": null, "otras_redes": [], "canal_de_venta_actual": null },
  "publico": { "cliente_ideal": null, "dolores": [], "objeciones": [], "personas": [] },
  "assets": [ { "descripcion": null, "seccion_sugerida": null, "calidad": null, "problema": null } ],
  "landing": {
    "objetivo_primario": null,
    "objetivo_secundario": null,
    "secciones": [ { "orden": 1, "nombre": null, "funcion": null, "copy": null } ],
    "headline_variantes": [],
    "subheadline": null,
    "beneficios": [],
    "faq": [ { "pregunta": null, "respuesta": null } ],
    "ctas": [ { "texto": null, "accion": null } ],
    "seo": { "title": null, "meta_description": null, "keywords": [] },
    "alt_texts": []
  },
  "advertencias": [],
  "datos_faltantes": []
}
```

=== FIN DEL PROMPT ===

---

## Qué adjuntar para que funcione bien

Claude no navega Instagram por vos (la mayoría de los perfiles requieren sesión iniciada y el
scraping está bloqueado). Para resultados buenos, pasale:

1. Captura de la cabecera del perfil: foto, nombre, bio, link, cantidad de seguidores.
2. Captura de la grilla completa (2 o 3 pantallazos si hace falta).
3. Captura de los highlights.
4. 5 a 10 posts representativos, con sus captions pegados como texto.
5. La foto de perfil descargada en su máxima resolución (para el logo y la paleta).
6. Opcional: capturas de comentarios con preguntas frecuentes y de las reseñas de Google.

Si en tu entorno hay herramientas de navegación o MCP con acceso a la web, agregale al prompt:
"Si tenés acceso a herramientas web, intentá primero obtener el perfil {{PERFIL}} y sus últimos
12 posts; si no podés acceder, trabajá solo con el material adjunto y decilo explícitamente."

## Prompt corto (versión rápida)

> Analizá este perfil de Instagram {{PERFIL}} con el material que te adjunto y devolveme un brief
> para landing page: identidad de marca (logo, paleta HEX, tipografía, estilo de fotos), qué vende y
> propuesta de valor, público objetivo, oferta y precios publicados, prueba social, datos de
> contacto y canal de venta, assets aprovechables, y una estructura de landing con copy listo para
> usar (headline con 3 variantes, beneficios, FAQ, CTAs, SEO title y meta description).
> No inventes nada: lo que no esté visible lo ponés como `null` y me lo listás al final como
> preguntas para el dueño. Marcá qué es observado y qué es inferido.

## Encadenado sugerido

1. Este prompt → brief en JSON.
2. Segundo prompt: "Con este JSON, generá la landing en HTML + Tailwind, mobile first, con el CTA a
   WhatsApp `https://wa.me/<numero>?text=<mensaje>` y la paleta indicada."
3. Tercer prompt: revisión de conversión y de claims legales antes de publicar.
