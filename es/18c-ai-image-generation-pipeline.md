# Generadores de imágenes con IA en 2026: herramientas y flujos de trabajo

**Tiempo:** unos 25 min de lectura + 35 min de práctica

---

## La idea

La generación de imágenes con IA en 2026 es como la cámara del celular en 2010. Cualquiera puede apretar un botón y sacar una foto. Pero la diferencia entre una foto cualquiera y una fotografía está en la técnica, en conocer tu herramienta y en la edición posterior.

El mercado se reparte entre 5 jugadores principales, cada uno con su especialidad. Midjourney es el artista. ChatGPT Images es el todoterreno que ya tienes a la mano. Flux trae modelos abiertos y velocidad. Recraft es el especialista en vectores. Ideogram es el tipógrafo. No hay un solo campeón para todo. Un profesional tiene 2 o 3 herramientas en su flujo y sabe cuál es más fuerte en qué.

En esta lección vamos a ver con honestidad los rangos de precios, los flujos de trabajo profesionales para distintas tareas, las trampas legales y los antipatrones que separan una "imagen de IA" de un material listo para publicarse.

Un aviso: este mercado cambia más rápido que cualquier otro. Los nombres de versiones y las condiciones de esta lección son a octubre de 2026; para los precios y versiones actuales, revisa la página [Lo vigente](https://aimayak.com/es/now/) y [el catálogo de Herramientas](https://aimayak.com/es/tools/). Donde un ejemplo no funciona sin una cifra, la cifra lleva fecha; en todo lo demás, el precio se reemplaza con un enlace a la página de precios del servicio.

🎨 **Imagínalo así:** la cocina de un buen restaurante. El chef no tiene un solo cuchillo para todo; tiene un juego completo. Un cuchillo para filetear pescado, uno chico para pelar verduras, una cuchilla para los huesos. Podrías cortar todo con un solo cuchillo, pero sería lento y quedaría mal. La generación de imágenes funciona igual: una sola herramienta para todo significa resultados mediocres en todo.

---

## 🎯 Árbol de decisión: qué modelo elegir

La pregunta clave **no es "cuál es la mejor herramienta"**, sino "¿qué estoy haciendo y para qué plataforma?"

**Elige Midjourney si:**
- ✓ Haces contenido artístico, ilustraciones, arte conceptual
- ✓ Necesitas tableros de inspiración (mood boards) o miniaturas de YouTube con un toque artístico
- ✓ Te parece bien trabajar en una app web con suscripción (antes la entrada principal era Discord)
- ✓ Te importa más la calidad que iterar rápido

**Elige ChatGPT Images (los modelos GPT Image) si:**
- ✓ Necesitas fotorrealismo más texto en la imagen
- ✓ Ya usas ChatGPT (un modo básico de imágenes está disponible incluso en el plan gratis)
- ✓ Quieres una API sencilla sin pelearte con configuraciones
- ✓ Necesitas maquetas rápidas para presentaciones

**Elige Flux si:**
- ✓ Necesitas velocidad y volumen (100+ imágenes al día)
- ✓ Quieres fotorrealismo con precisión fotográfica
- ✓ Necesitas pesos abiertos o quieres correrlo en tu propia máquina (con una tarjeta gráfica potente)
- ✓ Vas a revisar la licencia desde el principio: cambia de un modelo de Flux a otro

**Elige Recraft si:**
- ✓ Haces logotipos, gráficos vectoriales, íconos
- ✓ Trabajas en identidad de marca o infografías
- ✓ Necesitas archivos SVG como resultado
- ✓ Necesitas texto de calidad profesional en las imágenes

**Elige Ideogram si:**
- ✓ Haces pósters, anuncios, anuncios para redes sociales con tipografía
- ✓ Necesitas texto largo en la imagen (varias líneas)
- ✓ Tu presupuesto es mínimo (hay un plan gratis)

**Por defecto, Flux + Ideogram + Recraft cubre la mayoría de las tareas.** Agrega Midjourney cuando necesites un toque artístico, y ChatGPT Images si ya usas ChatGPT.

🎨 **Imagínalo así:** la flotilla de vehículos de una empresa. No necesitas un solo vehículo para todos los viajes. Necesitas un camión (Flux, para volumen), un sedán (ChatGPT Images, para comodidad), una camioneta todoterreno (Midjourney, para el toque artístico) y una van (Recraft, para trabajos especiales).

---

## Conceptos clave

- **Modelo de difusión**: un modelo de IA que aprende a reconstruir una imagen a partir de ruido. Muchos generadores de imágenes se basan en este principio
- **Ingeniería de prompts**: el oficio de redactar una petición para que el modelo te dé lo que quieres. Mucho depende del prompt
- **Relación de aspecto (AR)**: las proporciones de la imagen final. 16:9 para YouTube, 9:16 para Reels/TikTok, 1:1 para Instagram, 4:5 para Facebook
- **Seed** (semilla): un número que controla el azar. Mismo prompt + misma semilla = mismo resultado
- **Style reference (sref)**: una imagen de referencia de la que el modelo copia el estilo
- **Character reference (cref)**: una imagen de referencia que mantiene igual la apariencia de un personaje entre generaciones
- **Inpainting**: editar una parte de una imagen sin tocar el resto
- **Outpainting**: extender una imagen más allá de sus bordes (ampliar el lienzo)
- **Prompt negativo**: una descripción de lo que NO debe aparecer en la imagen
- **Guidance scale (CFG)**: qué tan estrictamente sigue el modelo el prompt. Rangos aproximados: 7-8 para fotorrealismo, 4-6 para trabajo creativo (dependen del modelo, y no todos los servicios tienen este ajuste)

---

## Teoría

### Los 5 jugadores principales en 2026

#### Midjourney V8

El jugador más antiguo y más reconocible. Pone el énfasis en la calidad artística. V8.2 salió en julio de 2026 (24 de julio de 2026), con una estética mejorada y personalización según tu gusto. A partir de V8 hay un modo HD con resolución nativa de 2K y más, además de texto más preciso dentro de la imagen; hay un Edit Model para hacer cambios a partir de referencias, y puedes convertir imágenes en videos cortos.

**Precio:** solo suscripciones de pago, empezando por el plan Basic (precios actuales: [Lo vigente](https://aimayak.com/es/now/) y la página de planes de Midjourney). Los planes más altos te dan más tiempo de GPU rápido y generaciones ocultas (stealth mode, modo sigiloso). No hay plan gratis. El modo HD y algunas otras funciones gastan más tiempo de GPU. Planes exactos: [https://www.midjourney.com/account](https://www.midjourney.com/account)

**Forma de trabajo:** una app web con suscripción. Antes, la entrada principal era un bot de Discord con los comandos `/imagine`, `/blend` y `/describe`; parámetros como `--ar` van al final del prompt.

**Puntos fuertes:**
- Un estilo artístico muy marcado
- Referencias de estilo y de personaje para mantener la consistencia
- Una comunidad enorme que comparte ajustes predefinidos
- Modo sigiloso en los planes altos: tus generaciones no se ven públicamente

**Puntos débiles:**
- No tiene una API pública oficial (revisa el estado actual en el sitio del servicio)
- El texto en las imágenes es mejor que antes, pero Ideogram es más confiable para la tipografía
- Difícil de iterar con scripts
- La interfaz y los parámetros se sienten extraños para quien empieza

**Ideal para:** miniaturas artísticas de YouTube, portadas de libros, arte conceptual, ilustraciones para artículos, tableros de inspiración.

---

#### ChatGPT Images / GPT Image (OpenAI)

DALL-E 2 y DALL-E 3 se apagaron en la API de OpenAI el 12 de mayo de 2026. Los reemplazó la familia de modelos GPT Image: en la API son `gpt-image-2` y `gpt-image-2.5`. Dentro de ChatGPT, la generación de imágenes está integrada: el modo básico está disponible incluso en el plan gratis, y el modo Thinking en los planes de pago. La versión 2.0 (abril de 2026) dibuja mejor el texto, incluido el texto en alfabetos no latinos. La versión 2.5 (8 de septiembre de 2026) agregó bocetos directamente en el chat, plantillas de pósters y ediciones a partir de comentarios que pones sobre la propia imagen.

**Precio:** en ChatGPT, la generación de imágenes está incluida en tu plan, dentro de sus límites. En la API pagas por tokens con `gpt-image-2`, y el costo de una sola imagen depende de su tamaño y calidad. Tarifas actuales: [Lo vigente](https://aimayak.com/es/now/) y la página de precios de OpenAI. Precios actuales: [https://developers.openai.com/api/docs/pricing](https://developers.openai.com/api/docs/pricing)

**Puntos fuertes:**
- Maneja bien prompts largos y descriptivos
- Puedes editar con una descripción directamente en la conversación
- Texto dentro de la imagen (bastante mejor desde la versión 2.0)
- Una API REST sencilla

**Puntos débiles:**
- Menos ajustes manuales que los modelos abiertos
- El "aspecto de IA" se nota más que con Flux
- Los filtros a veces bloquean peticiones inofensivas

**Ideal para:** maquetas rápidas para diapositivas, fotos de producto fotorrealistas, imágenes para artículos de blog cuando necesitas algo rápido y sin complicaciones.

---

#### Flux (Black Forest Labs)

Un equipo de ex integrantes de Stability AI lanzó Flux en 2024. A octubre de 2026, el sitio de la empresa (bfl.ai) presenta la familia FLUX 3: FLUX 3 Image (lanzado el 1 de octubre de 2026), FLUX 3 Video y FLUX Tools para edición precisa. Puedes usarlo con el Playground en tu navegador, con la API o descargando los pesos abiertos y corriéndolos en tu propia máquina. Sin código, la forma más fácil de entrar es un servicio concentrador como Krea, que ya ofrece FLUX 3 Image.

Antes (Flux 1), la familia se dividía en el rápido Schnell, Dev con licencia no comercial y Pro, disponible solo por API. Todavía vas a ver esos nombres en materiales viejos, pero las versiones nuevas tienen otra línea de modelos y otras licencias. **La licencia depende del modelo: antes de cualquier uso comercial, abre la página del modelo y lee las condiciones.**

**Precio:** con proveedores de API (fal.ai, Replicate y otros), pagas por imagen; los precios cambian según la versión y con el tiempo. Revisa los precios del proveedor que elijas: [https://fal.ai/models](https://fal.ai/models). Correr tú mismo los pesos abiertos es gratis, pero necesitas una tarjeta gráfica potente.

**Puntos fuertes:**
- Fotorrealismo muy logrado
- Velocidad (las versiones rápidas responden en segundos)
- Pesos abiertos para algunos de los modelos
- Soporte de LoRA para afinarlo a tu marca
- Inpainting/outpainting con las herramientas de edición (FLUX Tools)

**Puntos débiles:**
- El texto en las imágenes es más débil que el de Ideogram
- Menos estilo artístico que Midjourney
- La línea de versiones y licencias cambia rápido

**Ideal para:** fotos de producto para comercio electrónico, fotos de bienes raíces, fotografía de comida, moda, cualquier fotorrealismo en volumen.

---

#### Recraft V4

Una startup enfocada en gráficos vectoriales e identidad de marca. El modelo V4 salió el 17 de febrero de 2026, y V4.1 el 14 de mayo de 2026; el sitio también ofrece un V4.1 Flash rápido. Puede generar gráficos vectoriales editables (SVG), te deja definir tu propio estilo sin entrenar un modelo, y puede hacer maquetas, aumentar la resolución de imágenes y quitar fondos.

**Precio:** puedes probarlo gratis; para las condiciones de los planes de pago (créditos, acceso a la API), ve la página de precios: [https://www.recraft.ai/pricing](https://www.recraft.ai/pricing)

**Puntos fuertes:**
- Resultado vectorial nativo (SVG)
- El estilo propio de tu marca sin entrenar un modelo
- Buen control de la tipografía
- Íconos, logotipos e infografías son su fuerte

**Puntos débiles:**
- No sirve para fotorrealismo
- Menos estilos listos que Midjourney
- Los planes funcionan con créditos: calcula tu uso por adelantado

**Ideal para:** logotipos, íconos de interfaz, infografías, un paquete de identidad de marca, presentaciones.

---

#### Ideogram 4.0

Lo lanzaron ex investigadores de Google Brain. Se especializa en imágenes con letras: pósters, portadas, banners, empaques. Ideogram 4.0 (3 de junio de 2026) es un modelo de pesos abiertos con licencia comercial: texto denso en varios idiomas, control de dónde va un logotipo o un titular mediante marcos (bounding boxes) y salida en 2K. Funciona en el sitio y por API.

**Precio:** hay un plan gratis; para las suscripciones de pago y las condiciones de la API, ve esta página: [https://ideogram.ai/manage-subscription/subscribe](https://ideogram.ai/manage-subscription/subscribe)

**Puntos fuertes:**
- Uno de los mejores para texto en imágenes
- Tipografía muy lograda (distintas fuentes, letras estilizadas)
- Pósters, anuncios, anuncios en redes sociales
- Hay un plan gratis

**Puntos débiles:**
- Fotorrealismo promedio
- Menos flexibilidad artística que Midjourney
- El acceso a la API depende de tu plan

**Ideal para:** pósters con texto largo, anuncios en redes sociales, portadas de podcasts, composiciones tipográficas.

---

### Tabla comparativa

| Uso | Qué usar | Cómo pagas | ¿API? |
|---|---|---|---|
| Ilustración artística | Midjourney | Suscripción | Sin API pública oficial (revisa) |
| Fotorrealismo | Flux | Por imagen, con un proveedor de API o un concentrador | ✅ |
| Texto en imágenes | Ideogram | Plan gratis, suscripción o API | ✅ |
| Vector / logotipo | Recraft | Planes con créditos | ✅ |
| Foto + texto corto | ChatGPT Images | Incluido en ChatGPT; la API cobra por tokens | ✅ |
| Prototipos rápidos | Versiones rápidas de Flux | Por imagen, con un proveedor | ✅ |
| En tu propio equipo (cualquier volumen) | Modelos de pesos abiertos (Flux, Ideogram 4.0) | Tu propia tarjeta gráfica | ✅ |

Los precios concretos no están en la tabla porque cambian seguido. Haz las cuentas con las fórmulas de "Costos reales" más abajo.

---

### Flujos de trabajo profesionales

Una herramienta te da un resultado. Una combinación de herramientas te da una línea de producción. Aquí hay 4 flujos que cubren la mayor parte de lo que necesita hacer alguien de marketing de contenidos o un diseñador.

#### Flujo A: Contenido para redes sociales (un póster para Instagram)

**Tarea:** un póster semanal con la cita de un experto para una cuenta de Instagram.

**Herramientas:**
1. **Ideogram**: genera el póster de texto con la cita
2. **Midjourney**: genera un fondo artístico si lo necesitas
3. **Photopea** (una alternativa gratis a Photoshop): diseño final

**Tiempo:** 30 minutos por publicación.
**Costo inicial:** una suscripción a Midjourney (el plan de entrada Basic; ver la página de precios) + el plan gratis de Ideogram.
**Costo por pieza:** usa la fórmula de la sección "Costos reales".

**Flujo:**
```
Ideogram: "cita sobre fondo blanco" → PNG
   ↓
Midjourney: "fondo abstracto, azul profundo --ar 9:16" → PNG
   ↓
Photopea: superponer texto + fondo → PNG final de 1080x1920
```

---

#### Flujo B: Fotos de producto para comercio electrónico

**Tarea:** 100 fotos de producto sobre fondo blanco para una tienda en línea.

**Herramientas:**
1. **Flux**: genera las fotos de producto
2. **Photoshop / Canva**: agrega el logotipo y la marca

**Tiempo:** 5 minutos por producto (en lote, con un script).
**Costo inicial:** $0 (pagas por uso mediante la API).
**Costo:** el precio por imagen del proveedor × el número de imágenes (más un margen para los intentos fallidos).

**Flujo:**
```python
# batch_products.py: un ejemplo simplificado
# el ID del modelo en fal.ai cambia; revísalo en la página del modelo
import fal_client

products = ["ceramic mug", "wireless headphones", "leather wallet"]

for product in products:
    result = fal_client.run(
        "fal-ai/flux-pro",
        arguments={
            "prompt": f"professional product photography, {product}, white background, studio lighting, soft shadow, commercial e-commerce style",
            "image_size": "square_hd",
            "num_inference_steps": 28
        }
    )
    # guarda result["images"][0]["url"]
```

Compara esto con lo que pagas ahora por fotografía de producto, pero ten en cuenta los límites: la IA no reemplaza a un estudio cuando necesitas la forma y el color exactos de un producto real. Si los compradores esperan una foto real (publicaciones en marketplaces como Amazon, Mercado Libre, Etsy o eBay), revisa las reglas de la plataforma: muchas exigen fotos del producto real o un aviso de que la imagen está hecha con IA.

---

#### Flujo C: Paquete de identidad de marca

**Tarea:** un paquete de marca completo para un proyecto nuevo: logotipo, íconos, tablero de inspiración, maquetas.

**Herramientas:**
1. **Recraft**: logotipo + íconos (SVG)
2. **Midjourney**: tablero de inspiración (12 referencias artísticas)
3. **Flux**: maquetas fotorrealistas (tarjetas de presentación, empaques)

**Tiempo:** 4-8 horas para el paquete completo.
**Costo inicial:** suscripciones mientras dure el proyecto (Recraft, Midjourney) + pago por imagen con un proveedor de Flux; ver las páginas de precios.
**Costo por paquete:** lo que gastas en generaciones + tu tiempo.

**Flujo:**
```
Recraft → 10 opciones de logotipo en SVG
   ↓ elige 1-2
Recraft → 12 íconos de interfaz en SVG (estilo consistente)
   ↓
Midjourney → tablero de inspiración (cuadrícula de 3x4) → referencias para el equipo
   ↓
Flux → maquetas: tarjeta de presentación, taza, empaque, espectacular
   ↓
Photoshop → PDF final con la guía de marca
```

---

#### Flujo D: Miniaturas para blog / YouTube

**Tarea:** 20 miniaturas de YouTube a la semana, o imágenes de encabezado para artículos de blog.

**Herramientas:**
1. **Ideogram**: el texto superpuesto de la miniatura
2. **Una versión rápida de Flux**: fondos (rápido y barato)
3. **Canva**: armado final con las plantillas de tu canal

**Tiempo:** 15 minutos por miniatura.
**Costo:** número de generaciones por miniatura × precio por imagen (casi nada al lado de tu tiempo, pero haz las cuentas de todos modos).

**Flujo:**
```
Versión rápida de Flux: "fondo para una miniatura de YouTube" → 4 opciones
   ↓ elige una
Ideogram: "texto GANCHO grande + subtítulo pequeño"
   ↓
Canva: diseño con la plantilla del canal + logotipo
   ↓ exportar a 1920x1080
```

Para un canal con varios videos a la semana, suma tu gasto semanal en miniaturas y compáralo con lo que cobraría un freelancer en tu zona.

---

### El arte del prompt para generar imágenes

La calidad depende mucho del prompt. Estas son las técnicas principales que separan a un principiante de un profesional.

**Referencias de estilo:**
```
"retrato de un hombre, al estilo de la fotografía de Annie Leibovitz"
"paisaje, al estilo de la animación de Studio Ghibli"
"foto de producto, estética de publicidad de Apple, minimalista"
```

Poner nombres de artistas y estudios vivos en los prompts es un terreno en disputa (derechos de autor, ética). Es más seguro describir el estilo con palabras: iluminación, paleta, textura, composición.

**Prompts negativos (Flux, Ideogram):**
```
prompt: "interior de oficina moderna"
negative_prompt: "sin personas, sin texto, sin logotipos, sin desorden, sin plantas"
```

**Relaciones de aspecto (SIEMPRE fija una):**
- `--ar 16:9`: miniaturas de YouTube, fondos de pantalla de computadora
- `--ar 9:16`: TikTok, Instagram Reels, Stories
- `--ar 1:1`: publicaciones del feed de Instagram
- `--ar 4:5`: anuncios de Facebook
- `--ar 3:2`: fotografía estilo cámara réflex (DSLR)
- `--ar 21:9`: cinematográfico, banners ultra anchos

**Parámetros de calidad (Midjourney; los parámetros cambian entre versiones, así que consulta la documentación de la versión actual para ver la lista completa):**
```
--q 2          # calidad doble (más lento, cuesta más)
--s 250        # estilización media
--s 750        # estilización fuerte (más artística)
--chaos 50     # más variedad entre los 4 resultados
```

**Guidance scale (Flux y otros modelos abiertos; ChatGPT Images no tiene este ajuste):**
- 4-6: creativo, el modelo improvisa
- 7-8: el punto ideal para el fotorrealismo
- 9-10: sigue el prompt al pie de la letra (puede verse "forzado")

**Consistencia mediante referencias:**
```
Midjourney sref: --sref https://example.com/style.png
Midjourney cref: --cref https://example.com/character.png  (las versiones nuevas pueden usar otros parámetros para personajes)
Flux: lo que puedes hacer depende de la versión y del proveedor
```

---

### Cómo evitar los clichés de las imágenes con IA en 2026

En 2024, los problemas principales eran los seis dedos, los ojos raros y las manos derretidas. Para 2026 esto está **casi resuelto** en los modelos actuales.

**Los nuevos problemas de 2026 (el "aspecto de IA"):**
- Piel demasiado lisa (sin poros ni arrugas)
- Superficies brillantes con reflejos poco naturales
- Caras genéricas (todos parecen de foto de stock)
- Composiciones demasiado simétricas
- Luz amarilla / de atardecer en todas partes (a los modelos les encanta esa luz)
- Enfoque perfecto en todo (sin profundidad de campo natural)

**Soluciones: agrega esto a tu prompt:**
```
✅ "textura natural de la piel, poros visibles, pequeñas imperfecciones en la piel"
✅ "pose espontánea, composición asimétrica, sujeto descentrado"
✅ "grano de película, fondo ligeramente desenfocado, poca profundidad de campo"
✅ "luz dura de mediodía" en lugar del atardecer de siempre
✅ "momento real capturado, no posado, ligero desenfoque de movimiento"
✅ "encuadre imperfecto, como foto de celular"
```

**Edición posterior para darle un "toque humano":**
1. Lightroom / Photoshop → agrega grano (Filter → Noise → Add Noise, es decir Filtro → Ruido → Añadir ruido, 3-5%)
2. Una corrección de color ligera (sombras más frías, luces más cálidas)
3. Una viñeta sutil
4. Un recorte imperfecto (sujeto descentrado)
5. Una ligera aberración cromática en los bordes

🎨 **Imagínalo así:** la IA genera una foto "perfecta". Una foto real siempre tiene imperfecciones, y eso es lo que la hace sentirse viva. Agrégale un poco de aspereza, y la imagen deja de verse hecha por una máquina.

---

### El lado legal

Este es un capítulo importante que mucha gente se salta. En 2026 el panorama se volvió más complicado. Esto es información general, no asesoría legal: las leyes cambian de un país a otro, y para cualquier cosa seria necesitas un abogado.

**Derechos de autor sobre imágenes generadas con IA:**
- **Estados Unidos:** la Oficina de Derechos de Autor de EE. UU. (US Copyright Office) decidió en 2023 (y lo confirmó en 2025) que las imágenes generadas solo con IA **no se pueden registrar con derechos de autor**. Solo cuando hay una modificación humana importante (por ejemplo, un retrabajo serio en Photoshop)
- **UE:** no está claro; los reguladores todavía lo discuten
- **Qué significa en la práctica:** las imágenes generadas sin más no están protegidas por derechos de autor en EE. UU., así que es difícil impedir que otros las copien. La protección entra cuando haces una edición sustancial

Más información: [https://www.copyright.gov/ai/](https://www.copyright.gov/ai/)

**Uso comercial, servicio por servicio:** las condiciones cambian y dependen del plan, así que en lugar de una respuesta lista, la tabla te dice qué revisar.

| Servicio | Qué revisar antes del uso comercial |
|---|---|
| Midjourney | Condiciones de la suscripción: el uso comercial depende de tu plan y del tamaño de tu empresa (página de Terms of Service) |
| ChatGPT Images / GPT Image | Los términos de uso de OpenAI: derechos sobre el resultado y restricciones de contenido |
| Flux | La licencia del modelo específico: algunas versiones son no comerciales (el viejo Dev), otras tienen otras condiciones; lee la página del modelo |
| Recraft | Condiciones del plan: qué plan permite el uso comercial |
| Ideogram | Se indica que el modelo de pesos abiertos 4.0 viene con licencia comercial; en el servicio en sí, las condiciones dependen de tu plan |

**Imagen de personas reales:**
- Cada servicio tiene sus propias reglas sobre imágenes de personas reales, sobre todo de figuras públicas
- Los modelos abiertos pueden no tener ningún bloqueo integrado, y la responsabilidad legal es tuya
- GDPR (UE) y el derecho de publicidad (EE. UU.): usar la imagen de una persona real normalmente requiere su consentimiento

**Marcas de agua y etiquetado:**
- Google (Nano Banana en Gemini): las imágenes llevan una marca de agua invisible SynthID
- Otros servicios usan otras etiquetas (por ejemplo, metadatos C2PA); revisa las reglas del servicio específico
- Tendencia para 2026-2027: la Ley de IA de la UE introduce requisitos de etiquetado para el contenido generado; revisa fuentes actuales para los plazos y detalles

**Buena práctica:** agrega una etiqueta de "generado con IA" si usas las imágenes en marketing. Para fotos de producto en comercio electrónico, revisa las reglas de la plataforma.

---

### Costos reales: cómo calcularlos

Los precios de esta lección no están metidos a propósito en tablas: pueden cambiar en un mes. En lugar de cifras listas, aquí hay fórmulas en las que pones los valores actuales de las páginas de precios.

**Para una suscripción:**
```
costo por imagen = precio mensual de la suscripción / número de imágenes que de verdad hiciste
```

**Para una API (pago por imagen):**
```
gasto mensual = número de imágenes × precio por imagen × (1 + proporción de intentos fallidos)
```

La proporción de intentos fallidos suele ser considerable: la gente genera 4-8 opciones y elige una.

**Para correrlo en tu propia máquina (pesos abiertos):**
```
meses para recuperar la inversión = precio de la tarjeta gráfica / (gasto mensual en API que reemplazas − electricidad)
```

Un ejemplo con cifras inventadas (pon las tuyas): una tarjeta gráfica cuesta $1,500 y la API te cuesta $50 al mes, así que se paga sola en unos 30 meses; con $200 al mes, en unos 8. Correrlo tú mismo tiene sentido si generas mucho y de forma constante, y además necesitas privacidad o control total.

Compara suscripciones y APIs con el mismo volumen: toma tus propias 1,000 imágenes al mes y haz las cuentas con cada fórmula.

---

### Tendencias en la generación de imágenes en 2026

**Generación en tiempo real:**
- Las versiones rápidas de los modelos responden en segundos
- LCM (Latent Consistency Models): unos cuantos pasos en lugar de 28-50
- Usos: apps web interactivas, filtros de realidad aumentada, diseño en vivo

**Consistencia entre varias imágenes:**
- Las referencias de personaje (en Midjourney, en Flux mediante concentradores y en Nano Banana) están mejorando rápido
- Puedes hacer un cómic de decenas de páginas con un personaje consistente
- Contar historias con IA se está volviendo viable

**Generación de video:**
- Runway: Gen-4.5; Kling: VIDEO 3.0 (4.0 se anunció a finales de septiembre de 2026); Luma: Ray 3.2
- Google Flow: el video en Gemini y Flow lo hace Gemini Omni (que reemplazó a Veo 3.1)
- Sora (OpenAI) fue cerrado: el sitio y la app desde el 26 de abril de 2026 (revisa el anuncio de OpenAI), la API desde el 24 de septiembre de 2026
- Pika: clips cortos y un conjunto de apps
- Una lección aparte sobre generación de video: [Generación de video con IA](71-ai-video-generation.md)

**3D a partir de imágenes:**
- Ya hay modelos que convierten una sola imagen en una malla 3D (por ejemplo, Trellis de Microsoft y Hunyuan3D de Tencent; revisa si siguen vigentes)
- Usos: desarrollo de videojuegos, vistas 3D de productos en comercio electrónico

**Inpainting / edición:**
- FLUX Tools: edición precisa y localizada
- Adobe Firefly: integrado directamente en Photoshop
- Ideogram: edición de imágenes con instrucciones de texto
- ChatGPT Images: ediciones a partir de comentarios puestos sobre la propia imagen (versión 2.5)

---

### Antipatrones

❌ **Usar la configuración predeterminada**: el resultado sale genérico. Siempre fija la relación de aspecto, el estilo y la calidad.

❌ **No fijar una relación de aspecto**: el modelo hace una imagen 1:1 cuando necesitas 16:9 para YouTube. No puedes recortarla sin perder calidad.

❌ **Confiar en una sola generación**: SIEMPRE genera 4-8 opciones y elige la mejor. Cuesta poco y te ahorra horas de rehacer.

❌ **Personas fotorrealistas hechas con IA sin avisarlo**: es un problema ético y legal. Te puede costar la reputación y meterte en problemas legales.

❌ **Saltarte la edición posterior**: el resultado de la IA rara vez está listo para publicarse. Dedica al menos 5 minutos en Photoshop/Lightroom a los toques finales.

❌ **Una herramienta para todo**: Midjourney para un logotipo = un resultado flojo comparado con Recraft. Cada tarea lleva su herramienta.

❌ **Prompts escritos a mano cada vez**: no guardas prompts de plantilla en una biblioteca, así que escribes cada prompt desde cero. Crea una carpeta `prompts/`.

❌ **Ignorar la licencia comercial**: algunas versiones de Flux tienen licencia no comercial; usarlas comercialmente sin revisar las condiciones = una infracción. Revisa las condiciones del modelo y de tu plan antes de usar cualquier cosa en producción.

---

### Quién debería usar qué

Aquí no hay precios: cambian, así que usa las fórmulas de arriba y las páginas de precios actuales.

**Principiante (pasatiempo, aprendizaje):**
- Flux en playgrounds gratis o en concentradores
- Ideogram: plan gratis
- Photopea (una alternativa gratis a Photoshop en tu navegador)
- **Total: $0/mes**

**Quien hace marketing de contenidos (cuenta de Instagram, blog, contenido regular):**
- Midjourney (el plan de entrada; precio actual en la página de precios)
- Ideogram y Recraft: planes gratis
- Canva para el armado final (no siempre necesitas el plan de pago)
- **Total: la suscripción de Midjourney + lo que decidas pagar aparte**

**Diseñador freelance (proyectos para clientes):**
- Midjourney en un plan más alto
- Recraft en un plan de pago
- Flux por API, pagando lo que usas
- Photoshop (Creative Cloud) o una alternativa
- **Total: tus suscripciones más el uso de la API; súmalo con las páginas de precios**

**Estudio profesional (alto volumen, consistencia de marca):**
- Todo lo de arriba
- Tu propia tarjeta gráfica para modelos abiertos: una compra única más la electricidad
- Planes más altos de Recraft y Adobe Creative Cloud
- **Total: calcula cada concepto por separado**

🎨 **Imagínalo así:** una cocina profesional. Un estudiante de cocina aprende en una sola estufa, y con eso le basta. Un buen cocinero casero compra una buena estufa y un par de cuchillos. Un chef ejecutivo tiene 5 estufas, 20 cuchillos y una olla para cada cosa. No compres el equipo del chef mientras todavía eres estudiante.

---

## Práctica

### Paso 1: Configura Flux con fal.ai

El inicio más rápido es Flux con fal.ai: puedes probarlo en el playground sin código, y para los scripts necesitas una clave. Los IDs de los modelos en fal.ai cambian cuando salen versiones nuevas: antes de correr cualquier cosa, abre la página del modelo que quieres y usa su ID actual en lugar de los de los ejemplos de abajo.

```bash
# Regístrate en fal.ai (inicio de sesión con Google)
# Revisa las condiciones del crédito de prueba al registrarte

# Instala el SDK de Python
pip install fal-client python-dotenv pillow

# Crea un archivo .env
echo "FAL_KEY=your-fal-key-here" > .env
```

Obtén tu FAL_KEY aquí: [https://fal.ai/dashboard/keys](https://fal.ai/dashboard/keys)

---

### Paso 2: Un generador sencillo con una versión rápida de Flux

```python
# flux_simple.py: lo mínimo para empezar (revisa el ID del modelo en fal.ai)
import os
import fal_client
from dotenv import load_dotenv
import requests
from pathlib import Path

load_dotenv()
os.environ["FAL_KEY"] = os.getenv("FAL_KEY")

def generate_image(prompt: str, output_path: str, aspect_ratio: str = "square"):
    """Genera una imagen con una versión rápida de Flux."""
    print(f"Generando: {prompt[:50]}...")

    result = fal_client.run(
        "fal-ai/flux/schnell",  # revisa el ID actual en fal.ai
        arguments={
            "prompt": prompt,
            "image_size": aspect_ratio,
            "num_inference_steps": 4,
            "num_images": 1,
        }
    )

    # Guárdala
    image_url = result["images"][0]["url"]
    image_data = requests.get(image_url).content
    Path(output_path).write_bytes(image_data)
    print(f"Guardada: {output_path}")
    return output_path


if __name__ == "__main__":
    generate_image(
        prompt="professional product photography, ceramic coffee mug, white background, soft studio lighting, natural shadow",
        output_path="output/mug.png",
        aspect_ratio="square_hd"
    )
```

**Relaciones de aspecto para Flux:**
- `square_hd`: 1024x1024
- `square`: 512x512
- `portrait_4_3`: 768x1024
- `portrait_16_9`: 576x1024
- `landscape_4_3`: 1024x768
- `landscape_16_9`: 1024x576

---

### Paso 3: Genera fotos de producto en lote

```python
# batch_products.py: genera 10 productos en paralelo
import os
import fal_client
import asyncio
import aiohttp
from pathlib import Path

os.environ["FAL_KEY"] = os.getenv("FAL_KEY", "your-key")

# valor de ejemplo: usa el precio por imagen de la página de precios de tu proveedor
PRICE_PER_IMAGE = 0.05

PRODUCTS = [
    "ceramic coffee mug",
    "wireless bluetooth headphones",
    "leather wallet brown",
    "stainless steel water bottle",
    "wooden cutting board",
    "scented candle in glass jar",
    "linen tote bag",
    "minimalist desk lamp",
    "ceramic plant pot",
    "knit wool scarf grey",
]

PROMPT_TEMPLATE = (
    "professional product photography, {product}, pure white background, "
    "soft studio lighting from top-left, subtle natural shadow underneath, "
    "centered composition, commercial e-commerce style, photorealistic, "
    "high detail, sharp focus, no people, no text"
)

async def generate_one(session, product: str, idx: int):
    """Genera un producto de forma asíncrona."""
    prompt = PROMPT_TEMPLATE.format(product=product)

    # una versión más potente de Flux para comercio electrónico (revisa el ID en fal.ai)
    handler = await fal_client.submit_async(
        "fal-ai/flux-pro/v1.1",
        arguments={
            "prompt": prompt,
            "image_size": "square_hd",
            "num_images": 1,
            "guidance_scale": 7.5,
        }
    )
    result = await handler.get()

    image_url = result["images"][0]["url"]
    async with session.get(image_url) as resp:
        data = await resp.read()

    filename = f"output/product_{idx:02d}_{product.replace(' ', '_')}.png"
    Path(filename).write_bytes(data)
    print(f"✅ [{idx}/10] {product}")
    return filename


async def main():
    Path("output").mkdir(exist_ok=True)
    async with aiohttp.ClientSession() as session:
        tasks = [
            generate_one(session, product, i + 1)
            for i, product in enumerate(PRODUCTS)
        ]
        results = await asyncio.gather(*tasks)
    print(f"\n¡Listo! Se generaron {len(results)} productos.")
    print(f"Costo: ~${len(results) * PRICE_PER_IMAGE:.2f}")


if __name__ == "__main__":
    asyncio.run(main())
```

**Ejecútalo:**
```bash
python batch_products.py
# En un minuto o dos tendrás 10 fotos de producto
# Costo: número de imágenes × el precio por imagen de tu proveedor
```

---

### Paso 4: Combina Flux + Ideogram para miniaturas de YouTube

```python
# youtube_thumbnails.py: un flujo para miniaturas
import os
import fal_client
import requests
from pathlib import Path

os.environ["FAL_KEY"] = os.getenv("FAL_KEY")

def generate_background(topic: str, save_path: str):
    """Una versión rápida de Flux hace el fondo."""
    result = fal_client.run(
        "fal-ai/flux/schnell",  # revisa el ID actual en fal.ai
        arguments={
            "prompt": f"abstract dramatic background for YouTube thumbnail, {topic} theme, dark blue and orange tones, cinematic lighting, no text, no people, vignette",
            "image_size": "landscape_16_9",  # 1024x576
            "num_inference_steps": 4,
        }
    )
    url = result["images"][0]["url"]
    Path(save_path).write_bytes(requests.get(url).content)
    return save_path


def generate_text_overlay(hook_text: str, save_path: str):
    """Ideogram hace el texto superpuesto (también está disponible en fal.ai)."""
    result = fal_client.run(
        "fal-ai/ideogram/v2",  # revisa la versión actual de Ideogram en fal.ai
        arguments={
            "prompt": f"big bold text '{hook_text}' on transparent background, white text with red outline, condensed sans-serif font, dramatic typography for YouTube thumbnail",
            "aspect_ratio": "16:9",
            "style": "design",
        }
    )
    url = result["images"][0]["url"]
    Path(save_path).write_bytes(requests.get(url).content)
    return save_path


def assemble_thumbnail(bg_path: str, text_path: str, output_path: str):
    """Armado final con PIL."""
    from PIL import Image

    bg = Image.open(bg_path).convert("RGBA")
    text = Image.open(text_path).convert("RGBA")

    # Ajusta el texto superpuesto al tamaño del fondo
    text = text.resize(bg.size)

    # Combina las capas
    combined = Image.alpha_composite(bg, text)
    combined.convert("RGB").save(output_path, "PNG")
    print(f"Listo: {output_path}")


if __name__ == "__main__":
    Path("output").mkdir(exist_ok=True)

    bg = generate_background(
        topic="AI image generation tools comparison",
        save_path="output/bg.png"
    )
    text = generate_text_overlay(
        hook_text="MIDJOURNEY vs FLUX",
        save_path="output/text.png"
    )
    assemble_thumbnail(bg, text, "output/thumbnail_final.png")
```

---

### Paso 5: Una biblioteca de prompts: guarda los prompts que funcionan

```bash
mkdir -p prompts/{product,thumbnail,social,brand}
```

```yaml
# prompts/product/ecommerce-white-bg.yaml
name: "E-commerce white background"
model: "flux-pro"
template: |
  professional product photography, {product},
  pure white background, soft studio lighting from top-left,
  subtle natural shadow underneath, centered composition,
  commercial e-commerce style, photorealistic, high detail,
  sharp focus, no people, no text, no logos
params:
  image_size: "square_hd"
  guidance_scale: 7.5
  num_inference_steps: 28
negative_prompt: "blurry, low quality, distorted, watermark, signature"
notes: |
  - Prueba 4 generaciones por producto y elige la mejor
  - Edición posterior: refuerza un poco la sombra en Photoshop
  - Costo: según la página de precios del proveedor
```

**Consejo:** crea `.claude/agents/image-prompt-engineer.md`, un agente que lea estos archivos YAML y arme los prompts finales para cada tarea.

---

## Herramientas y recursos

- **[Midjourney](https://www.midjourney.com)**: sitio oficial, acceso por Discord, app web
- **[ChatGPT Images (GPT Image)](https://learn.chatgpt.com/docs/image-generation)**: generación de imágenes integrada en ChatGPT
- **[OpenAI API Pricing](https://developers.openai.com/api/docs/pricing)**: precios actuales de la API para gpt-image-2 y gpt-image-2.5
- **[Black Forest Labs (Flux)](https://bfl.ai)**: el sitio oficial de Flux, detalles técnicos
- **[fal.ai](https://fal.ai)**: el proveedor principal de la API de Flux, con un playground para probar
- **[Replicate](https://replicate.com)**: un hosting alternativo de API para Flux, Stable Diffusion y otros modelos
- **[Recraft](https://www.recraft.ai)**: gráficos vectoriales + identidad de marca
- **[Ideogram](https://ideogram.ai)**: la herramienta de referencia para texto en imágenes
- **[Photopea](https://www.photopea.com)**: una alternativa gratis a Photoshop en tu navegador
- **[Canva](https://www.canva.com)**: armado final con plantillas
- **[Lexica](https://lexica.art)**: búsqueda por prompts y estilos
- **[PromptHero](https://prompthero.com)**: una biblioteca de prompts que funcionan
- **[US Copyright Office on AI](https://www.copyright.gov/ai/)**: la postura oficial de EE. UU. sobre los derechos de autor de imágenes con IA
- Precios y versiones actuales: [Lo vigente](https://aimayak.com/es/now/)

---

## Lista de verificación: un flujo profesional

✅ Hay un modelo principal elegido para cada uso (no una herramienta para todo)
✅ El flujo de trabajo está estandarizado (escrito en el README del proyecto)
✅ Hay una biblioteca de prompts (una carpeta `prompts/` con plantillas YAML/JSON)
✅ La relación de aspecto está fijada para cada plataforma (16:9, 9:16, 1:1, 4:5)
✅ Hay un proceso de edición posterior (al menos grano + corrección de color)
✅ Revisión legal: la licencia de uso comercial corresponde al uso
✅ Un flujo de respaldo por si la API principal se cae (un modelo abierto corriendo localmente como respaldo)
✅ Seguimiento de costos: conoces el costo por pieza para tu presupuesto
✅ Política de transparencia: las imágenes generadas con IA llevan etiqueta donde la ética o la ley lo exigen
✅ Los archivos fuente (PSD, imágenes originales) se guardan en `/sources` para reutilizarlos

---

## Ideas clave

> En la generación de imágenes en 2026, una herramienta para todo significa ceder en todo. Un profesional tiene 2-3 modelos en su flujo: Flux para fotorrealismo, Ideogram para texto, Recraft para vectores o Midjourney para trabajo artístico. Una combinación de herramientas te da mejores resultados a un costo razonable.

> La calidad depende mucho del prompt. La relación de aspecto, los prompts negativos, las referencias de estilo y el guidance scale no son "opciones"; son ajustes obligatorios (donde el servicio los soporte). Configuración predeterminada = resultado genérico.

> El panorama legal en 2026 no es sencillo. Las imágenes con IA no están protegidas por derechos de autor en EE. UU. La licencia comercial depende del modelo y del plan. Revisa la licencia **antes** de usar imágenes en producción, no después.

> La edición posterior es la diferencia entre una "imagen de IA" y un material listo para publicarse. Dedica al menos 5 minutos al grano, la corrección de color y pequeñas imperfecciones, y la imagen deja de verse hecha por una máquina (y aun así etiquétala como generada con IA donde se exija).

---

## Siguiente lección

→ [Qué son las Skills](19-skills-intro.md): el inicio del módulo sobre experiencia reutilizable. Si necesitas video, ve [Generación de video con IA](71-ai-video-generation.md).
