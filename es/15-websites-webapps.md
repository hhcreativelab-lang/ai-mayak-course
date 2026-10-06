# Crea sitios web y aplicaciones web con Claude Code

**Tiempo:** unos 25 min de lectura + 45 min de práctica

---

## Lo esencial

Hacer un sitio web antes era como construir una casa: necesitabas un arquitecto (un diseñador), un maestro de obras (un desarrollador front-end que convierte el diseño en una página que funciona), una cuadrilla (programadores) y varias semanas de trabajo. Con Claude Code es como tener a un constructor experto disponible: describes con palabras lo que quieres, él lo construye y tú vas haciendo ajustes sobre la marcha.

Para esta lección no necesitas saber programar. Vas a describir, mirar y pedir cambios. Sí necesitas Claude Code; la lección [Claude Code de escritorio](05b-claude-code-desktop.md) muestra cómo instalarlo. También es el primer paso si más adelante quieres crear una aplicación con Claude Code.

---

## Conceptos clave

- Claude Code construye un sitio web completo en HTML/CSS/JS (las tres piezas de una página web: estructura, estilo y comportamiento) a partir de una descripción en lenguaje común
- Haces cambios conversando: "pon el fondo más oscuro" en lugar de editar el CSS a mano
- Un servidor local (localhost) te deja revisar el sitio antes de publicarlo (publicar quiere decir ponerlo en línea en internet)
- Publicar en Vercel, Cloudflare Pages o GitHub Pages es gratis para proyectos personales (las condiciones para sitios comerciales están más abajo)

---

## Teoría

### Qué construye Claude Code en realidad

🎨 **Imagínalo así:** Claude Code construye un sitio web como un carpintero con experiencia hace un mueble a la medida. Le dices "quiero una mesa con cajones, de madera oscura", y te hace una mesa real, no una maqueta de cartón. Puedes poner un plato encima desde el primer momento.

Cuando pides un sitio web, el agente genera código real. No una plantilla, no un relleno provisional: HTML, CSS y JavaScript completos y funcionando. Puedes abrir esos archivos en cualquier navegador y van a funcionar.

**Ejemplo de prompt:** "Crea un sitio web para un entrenador de fitness. Nombre: Mike Carter. Especialidad: transformación física en 90 días. Necesito: una página de inicio con un llamado a la acción, una sección con 3 programas (Bajar de peso, Ganar músculo, Reto), testimonios de clientes y un formulario de contacto. Estilo: fondo oscuro, detalles en naranja, minimalismo moderno."

**Lo que construye el agente:**
- `index.html`: la estructura de la página
- `styles.css`: todos los estilos, colores, fuentes y el diseño adaptable (la página se ajusta al tamaño de la pantalla)
- `script.js`: animaciones, formularios, elementos interactivos
- Optimizado para celulares
- Semántica HTML correcta (encabezados, secciones, metaetiquetas)

El primer borrador aparece en minutos, no en semanas.

---

### Un ejemplo completo: el sitio web de un entrenador de fitness

Recorramos de principio a fin un flujo de trabajo real para crear un sitio web.

#### Etapa 1: El primer prompt

```
Crea un sitio web de una sola página para un entrenador personal.
Datos del cliente:
- Nombre: Mike Carter
- Especialidad: transformación física, trabaja con profesionales con poco tiempo
- Promesa principal: resultados visibles en 90 días o te devolvemos tu dinero
- Tres programas: "Bajar de peso" ($200/mes), "Delgado y fuerte" ($250/mes), "Coaching VIP" ($500/mes)
- Estilo: oscuro (#1a1a1a), detalles en naranja (#f5813f), una fuente moderna
- Necesita un formulario para reservar una consulta gratis
```

#### Etapa 2: Haz cambios conversando

🎨 **Imagínalo así:** ajustar un sitio web conversando es como la prueba de un traje con el sastre. "Un poco más ancho de hombros", "solapas más angostas", "botones más oscuros". El sastre hace los cambios y te lo vuelve a mostrar. Tú no coses nada.

Ya abriste el sitio en tu navegador y le diste un vistazo. Ahora haces ajustes:

- "Haz el título más grande, se pierde"
- "Agrega una barra de cifras: 3 años de experiencia / más de 200 clientes / 94% satisfechos"
- "La sección de programas se ve apretada, dale más espacio"
- "Agrega una portada de video en la página de inicio (un espacio provisional con un botón de reproducir)"
- "En el formulario de reserva, agrega un campo para elegir el programa"

Cada cambio es una frase en lenguaje común. El agente encuentra el lugar correcto en el código y lo cambia. Tú no miras el código ni editas nada a mano.

En un borrador así, el agente inventa testimonios, cifras y fotos para rellenar. Para un cliente real, cámbialos por los datos reales del cliente: los testimonios y cifras inventados engañan a los compradores.

#### Etapa 3: Revísalo en distintos dispositivos

El agente ya hizo el diseño adaptable, pero vale la pena revisarlo:

```
Revisa cómo se ve el sitio en una pantalla de celular de 375px de ancho.
Si algo se rompe, corrígelo.
```

---

### Un servidor local: revisa antes de publicar

🎨 **Imagínalo así:** un servidor local es como un ensayo general en un teatro vacío. Todo es real: las luces, el vestuario, los diálogos. Pero no hay público. Encuentras los problemas y los arreglas antes del estreno.

Antes de mostrarle el sitio a un cliente o de publicarlo, lo pruebas en tu computadora. Claude Code inicia un servidor local:

```bash
# El agente ejecuta esto por ti (la opción --bind 127.0.0.1 hace que solo tu propia computadora pueda acceder al servidor)
python3 -m http.server 3000 --bind 127.0.0.1
# o
npx serve .
```

Abre tu navegador en `http://localhost:3000` y vas a ver el sitio como si ya estuviera en internet, solo que únicamente tú puedes verlo. En la app de escritorio de Claude, Claude Code abre el sitio por ti en el panel Browser integrado.

**Por qué importa:** algunas cosas no funcionan si solo abres el archivo HTML con doble clic (solicitudes de datos y a una API, módulos de JavaScript). Un servidor local reproduce las condiciones reales.

---

### Publicar: poner tu sitio en internet

🎨 **Imagínalo así:** publicar en Vercel es como usar una cafetera de espresso. Por dentro hay una maquinaria complicada: presión, temperatura, molienda. Tú aprietas un botón y tu café está listo.

#### Vercel (recomendado para empezar)

**Costo:** el plan Hobby es gratis, pero solo para proyectos personales, no comerciales. Para el sitio de un cliente o cualquier sitio comercial necesitas el plan de pago Pro (a octubre de 2026: $20 al mes por desarrollador, que incluye $20 de crédito de uso). Revisa las condiciones actuales en vercel.com/pricing. Si necesitas una opción gratis para el sitio de un cliente, mira Cloudflare Pages (la lección [Publicación 24/7: Cloudflare Workers](18-deployment-cloudflare.md)) y revisa las condiciones en su página de precios.

**Cómo publicar:**
1. Sube tu código a GitHub, un sitio web que guarda proyectos de código (necesitas una cuenta de GitHub y tienes que iniciar sesión tú; la subida se la puedes pedir al agente)
2. Conecta el repositorio (la carpeta de tu proyecto en GitHub) a Vercel (vercel.com)
3. Haz clic en Deploy (Publicar)
4. Obtén una dirección como `fitness-carter.vercel.app`
5. Puedes conectar tu propio dominio

**Actualizaciones automáticas:** cada vez que el agente hace cambios y tú los guardas con un commit (un commit es una foto guardada de tus cambios) y los subes a GitHub (push), Vercel actualiza el sitio automáticamente.

#### GitHub Pages

**Costo:** gratis para repositorios públicos (cualquiera puede ver el código); los privados necesitan un plan de pago de GitHub

**Cuándo elegirlo:** sitios estáticos sin código del lado del servidor, cuando no te importa que cualquiera pueda ver tu código. Según las condiciones de GitHub, GitHub Pages no está pensado para tiendas en línea ni para sitios cuyo fin principal es vender.

**Cómo publicar:** repositorio → Settings → Pages → en "Build and deployment", elige como fuente Deploy from a branch → elige una rama (branch) → Save.

---

### Agregar más funciones

#### Formularios de contacto

Un sitio estático no puede recibir por sí solo los envíos de un formulario (no tiene lado del servidor). Tus opciones:

- **Formspree**: tiene un plan gratis con un límite mensual de envíos (revisa el límite actual en su página de precios); solo apuntas la acción del formulario a su dirección
- **Netlify Forms**: si publicas en Netlify, activa la detección de formularios en la configuración y agrega al formulario el atributo netlify
- **EmailJS**: envía el formulario directamente desde el navegador a través de su API

El agente conoce todos estos servicios y va a configurar uno si se lo pides.

#### Un CMS para el contenido

Si el cliente quiere editar los textos por su cuenta, sin un programador, necesita un CMS (sistema de gestión de contenidos, un panel para editar el sitio):

- **Decap CMS** (antes Netlify CMS): de código abierto, gratis
- **Sanity**: más potente, tiene plan gratis
- **Contentful**: una opción popular

El agente puede conectar cualquiera de ellos a un sitio estático.

#### Pagos

Para vender servicios directamente desde el sitio:

- **Stripe**: acepta tarjetas de todo el mundo (la disponibilidad depende del país donde está registrado tu negocio)
- **PayPal**: el widget lleva unas cuantas líneas de código

---

### Lo que más piden los clientes

🎨 **Imagínalo así:** un sitio web sencillo es como un fotógrafo que hace una sesión profesional en un solo día. Antes eso requería un estudio, iluminación y un equipo. Ahora es una persona con la herramienta adecuada.

Los sitios web son uno de los servicios que puedes ofrecer con Claude Code. Esto es lo que más piden los clientes:

**Un sitio sencillo para un negocio local:** una estética, un restaurante, un consultorio dental.

**Una landing page (página de aterrizaje) para un producto o servicio:** una sola pantalla que explica con claridad el valor, con un formulario de registro.

**Un portafolio para un freelancer:** el cliente quiere mostrar su trabajo.

**Un sitio para un evento:** una conferencia, una fiesta, un evento de empresa.

El precio y los tiempos dependen del mercado, del nicho y de cuántas rondas de correcciones haya; no existen cifras universales. Cómo calcular tu propio precio lo ves en las lecciones [Precios basados en el valor](39-monetization-pricing.md) y [Cómo poner tu precio](d02-pricing-simple.md).

---

### Límites: lo que Claude Code no hace solo

**Los límites, con honestidad:**

- Las aplicaciones web complejas (inicio de sesión de usuarios, bases de datos, funciones en tiempo real) necesitan más que HTML/CSS/JS: necesitan un backend (el lado del servidor que guarda los datos y ejecuta la lógica). Claude Code puede con eso, pero es bastante más difícil y lleva más tiempo
- El diseño no siempre sale "wow" al primer intento; hace falta ir ajustando
- El agente no dibuja ilustraciones complejas ni fotos: los íconos sencillos los puede hacer con código, y para lo demás usa imágenes de banco gratuitas o emoji
- Las fotos originales las tienes que poner tú

**Conclusión práctica:** para landing pages y sitios sencillos de negocios, es una herramienta excelente. Para aplicaciones web complejas con usuarios, pagos y datos reales, necesitas saber más de arquitectura (las lecciones [API e integraciones](16-apis-integration.md) y [Publicación 24/7: Cloudflare Workers](18-deployment-cloudflare.md)).

---

## Práctica

**Ejercicio: crea un sitio web de una página**

Elige una opción:
- **Opción A:** Un sitio sobre ti (quién eres, a qué te dedicas, cómo contactarte)
- **Opción B:** Un sitio de práctica para un negocio inventado (invéntalo tú)
- **Opción C:** Si ya tienes un cliente real, empieza su sitio

El proceso:
1. Describe lo que necesitas en un solo prompt (tema, secciones, estilo, colores)
2. Mira el resultado en tu navegador con el servidor local
3. Haz al menos 5 cambios conversando
4. Publica en Vercel o en GitHub Pages
5. Comparte el enlace: ya tienes un sitio web en línea

⚠️ Si es el sitio de un cliente real (Opción C), recuerda que el plan gratis Hobby de Vercel es solo para proyectos no comerciales (mira la sección de publicación más arriba). GitHub Pages necesita que el código sea público y no está pensado para sitios cuyo fin principal es vender, así que no pongas ahí datos privados.

---

## Herramientas y recursos

- **Claude Code**: construye HTML/CSS/JS a partir de una descripción
- **[Vercel](https://vercel.com)**: publicación; el plan gratis es solo para proyectos no comerciales
- **[GitHub Pages](https://pages.github.com/)**: una alternativa para repositorios públicos
- **[Cloudflare Pages](https://pages.cloudflare.com/)**: publicación rápida, tiene plan gratis y una CDN global (una red de servidores en todo el mundo que entrega tu sitio rápido). A octubre de 2026, Cloudflare recomienda Workers con archivos estáticos para proyectos nuevos; Pages sigue funcionando
- **[Formspree](https://formspree.io)**: manejo de formularios, tiene plan gratis con límite
- **[EmailJS](https://www.emailjs.com/)**: envía formularios directamente desde el navegador
- **[Playwright](https://playwright.dev/)**: pruebas automáticas de aplicaciones web (en varios navegadores)
- **[Puppeteer](https://pptr.dev/)**: automatiza Chrome para pruebas y capturas de pantalla
- **[Google Fonts](https://fonts.google.com/)**: fuentes gratis; el agente sabe cómo agregarlas
- **[Unsplash](https://unsplash.com)**: fotos gratis (el agente puede tomar imágenes de ahí)
- **[Coolors](https://coolors.co)**: un generador de paletas de colores, por si no sabes cuáles elegir
- **[Lighthouse](https://developer.chrome.com/docs/lighthouse)**: revisa el rendimiento y la accesibilidad de un sitio (viene integrado en Chrome DevTools)

Precios y versiones actuales: [Lo vigente](https://aimayak.com/now/).

---

## Errores comunes

**Error 1: No probar en pantallas de celular**
El sitio se ve perfecto en la computadora, pero en el celular el texto se sale de la pantalla y los botones quedan demasiado pequeños. Revisa siempre: "Revisa cómo se ve en una pantalla de 375px de ancho" (es el ancho del iPhone SE, una de las pantallas populares más angostas).

**Error 2: Olvidar la etiqueta meta viewport**
Sin `<meta name="viewport" content="width=device-width, initial-scale=1.0">` el sitio se ve en el celular como una versión de computadora encogida. Claude normalmente la agrega, pero revísalo.

**Error 3: No revisar qué tan rápido carga**
Imágenes enormes, fuentes sin optimizar, animaciones pesadas, y el sitio tarda 8 segundos en cargar. Pídele al agente: "Optimiza todas las imágenes y asegúrate de que el sitio cargue en menos de 3 segundos." O usa Lighthouse en Chrome DevTools.

---

## Lecciones relacionadas

- **[Claves de API y configuración de .env](11-api-keys-env.md)**: cómo configurar un archivo `.env` (donde viven las claves secretas, para que queden fuera del código de tu sitio) para las integraciones de API de tu sitio (Stripe, Formspree)
- **[Publicación 24/7: Cloudflare Workers](18-deployment-cloudflare.md)**: publicar en Cloudflare Workers y Pages a detalle
- **[RAG: Retrieval Augmented Generation](14-rag.md)**: si tu sitio necesita un chatbot con una base de conocimiento

---

## Ideas clave

> Un sitio sencillo que antes llevaba una semana de trabajo ahora puede llevar unas cuantas horas. No es solo un poco más de eficiencia; es otro tipo de trabajo. Proyectos que antes requerían un equipo ahora están al alcance de una sola persona.

> Hacer cambios en lenguaje común es la mayor ventaja. No estás aprendiendo CSS; estás describiendo lo que quieres. Eso cambia de raíz quién puede crear sitios web.

> Publicar tu primer sitio es una habilidad que te va a servir en el trabajo y en proyectos personales. No dejes la práctica para después.

---

## Próxima lección

→ [La lección que no esperabas](100-intrigue.md): el cierre del curso, las cualidades tuyas que la IA no va a reemplazar

En la biblioteca, opcional: [API e integraciones](16-apis-integration.md): cómo se comunican los programas entre sí y cómo aprovecharlo
