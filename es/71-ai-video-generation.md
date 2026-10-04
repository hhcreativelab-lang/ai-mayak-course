# Generación de video con IA: Runway, Kling, Luma y más

**Tiempo:** unos 25 min de lectura + 35 min de práctica

---

## La idea

Un video corto antes requería un camarógrafo, un editor y un estudio. Hoy abres una pestaña del navegador, escribes unas cuantas oraciones y a los pocos minutos tienes un clip. No es Hollywood, pero para redes sociales, una landing page o un anuncio muchas veces es suficiente. En esta lección repasamos las plataformas a octubre de 2026 y armamos un flujo que funciona: Claude escribe el guion y los prompts (un prompt es tu petición a la IA) → Runway genera el video → FFmpeg arma el corte final. Kling se conecta de la misma manera.

🎨 **Imagínalo así:** antes cada video era como una pieza de cerámica hecha a mano: lento, caro, empezando de cero cada vez. Ahora se parece más a una impresora 3D: pones los parámetros y sale la pieza terminada. La calidad está un escalón por debajo de lo hecho a mano, pero es cientos de veces más rápido.

---

## Conceptos clave

- **Text-to-Video** (texto a video): un video generado a partir de la descripción escrita de una escena
- **Image-to-Video** (imagen a video): animar una foto fija o un render (darle vida)
- **Video-to-Video** (video a video): cambiar el estilo o el escenario de un video que ya existe
- **Motion Brush** (pincel de movimiento): una herramienta de versiones anteriores de Runway para controlar con precisión cómo se mueve cada zona del cuadro
- **Animación por fotogramas clave**: tú fijas el primer y el último cuadro, y la IA construye la transición entre ellos
- **El problema de la consistencia**: los personajes pueden "cambiar" de una escena a otra, y cómo manejarlo
- **Licencias comerciales**: qué puedes y qué no puedes hacer con los videos generados

---

## Teoría

### Las plataformas de 2026: quién es quién

Hasta 2024, el video con IA era un juguete de demostración: caras borrosas, movimientos poco naturales, piernas con articulaciones de más. Runway, Kling, Luma y otras plataformas cambiaron la ecuación, y en 2026 el mercado se mueve rápido: Sora fue cerrado, y Runway y Kling lanzaron nuevas generaciones de sus modelos. Los pequeños negocios ya usan video con IA en sus anuncios.

🎨 **Imagínalo así:** las primeras cámaras digitales en 2001 tomaban peores fotos que las de rollo, pero alcanzaban de sobra para una foto de cumpleaños, y siguieron mejorando. El video con IA está en un punto parecido: imperfecto, pero ya útil para el trabajo de todos los días.

---

### Runway: el caballo de batalla con API

Runway es una startup de Estados Unidos y uno de los líderes del mercado, con una API sólida. Justo eso la hace práctica para automatizar. A octubre de 2026, su modelo principal es Gen-4.5; los planes de pago también te dan modelos de socios (por ejemplo, Kling 3.0, Seedance 2.0, Nano Banana Pro), y Aleph 2.0 edita video que ya tienes.

**Qué puede hacer:**

**Text-to-Video.** Escribes un prompt y obtienes un clip de 5-10 segundos. Runway entiende muy bien el lenguaje de cámara: "slow dolly in" (acercamiento lento), "aerial establishing shot" (toma aérea de ubicación), "rack focus from foreground to background" (cambio de foco del primer plano al fondo). Escribe como director y obtendrás una toma de director.

**Image-to-Video.** Subes la foto de un producto o de un interior, y Runway la anima conservando el estilo. Es la función estrella para bienes raíces y tiendas en línea: las fotos fijas cobran vida para los anuncios.

**Motion Brush** (una herramienta de versiones anteriores de Runway; revisa si los modelos actuales todavía la tienen). Pintas sobre el cuadro y le das una dirección de movimiento a cada zona. El agua corre, las hojas se mecen y todo lo demás se queda quieto: control total.

**Precios (a octubre de 2026):**

- Hay un plan gratis con un paquete único de créditos, y varios planes de pago
- Qué tan rápido se gastan los créditos depende del modelo: cada modelo usa una cantidad fija de créditos por segundo de video
- Precios actuales y tarifas de créditos: [runway.com/pricing](https://runway.com/pricing), [Lo vigente](https://aimayak.com/es/now/)

**Lo que más nos importa:** la API oficial (interfaz de programación de aplicaciones, una forma de que tus propios programas hablen con el servicio). Puedes automatizar todo: Claude genera los prompts → un script (un programa pequeño que ejecuta los pasos por ti) los manda a Runway → los videos se descargan solos.

**Licencia comercial:** según la página de precios de Runway, el uso comercial está permitido en los planes de pago. Vuelve a leer las condiciones antes de entregarle trabajo a un cliente.

```python
from runwayml import RunwayML, TaskFailedError  # pip install runwayml

# La clave de API se lee de la variable de entorno RUNWAYML_API_SECRET
client = RunwayML()


def generate_video(prompt: str, duration: int = 5) -> str:
    """
    Genera un video a partir de texto mediante la API de Runway.
    Devuelve la URL del video terminado.
    Los nombres de los modelos y los parámetros permitidos cambian: revisa docs.dev.runwayml.com.
    Si el modelo que eliges solo acepta una imagen inicial, usa
    client.image_to_video.create(...) con el parámetro prompt_image.
    """
    try:
        task = client.text_to_video.create(
            model="gen4.5",         # modelo principal a octubre de 2026
            prompt_text=prompt,
            ratio="1280:720",       # 16:9 horizontal
            duration=duration,
        ).wait_for_task_output()    # el SDK consulta el estado de la tarea por ti
    except TaskFailedError as error:
        raise RuntimeError(f"La generación falló: {error.task_details}")

    return task.output[0]
```

---

### Kling: fuerte en el movimiento humano

Kling es una plataforma de Kuaishou (China). Su línea de trabajo a octubre de 2026 es Kling VIDEO 3.0: clips de 3 a 15 segundos, 4K nativo, sonido con sincronización de labios y varias tomas en una sola solicitud. A finales de septiembre de 2026 se anunció Kling 4.0 (hasta 30 segundos de una sola vez, hasta 10 fotogramas clave, sonido estéreo); se espera un lanzamiento amplio en octubre.

**Puntos fuertes:**

- El movimiento humano: gestos, expresiones faciales, la forma de caminar (según reseñas de usuarios; pruébalo con tus propios prompts)
- Clips de hasta 15 segundos en VIDEO 3.0; la versión 4.0 está anunciada con hasta 30
- Sonido con sincronización de labios dentro del mismo video
- Hay una API disponible (documentación: [kling.ai/document-api](https://kling.ai/document-api))

**Limitaciones:**

- La velocidad de generación depende de la carga y de tu plan: mídela con tus propias tareas
- Preguntas sobre el almacenamiento de datos para clientes de la UE y de Estados Unidos (revisa las condiciones de tu contrato)

**Precios:** hay un plan gratis Basic y varios planes de pago. Precios actuales: [Lo vigente](https://aimayak.com/es/now/).

🎨 **Imagínalo así:** Kling es un camarógrafo de documentales. Filma un movimiento que se ve vivido, no actuado.

**Cómo conectar la API:** entras a la API de Kling con un JWT, un token que se arma con tu Access Key y tu Secret Key y que es válido por 30 minutos. La dirección de la API y los nombres de los modelos cambian entre versiones, así que esta lección no los deja fijos en el código: toma los actuales de la documentación de Kling.

```python
import time
import jwt  # pip install pyjwt


def kling_token(access_key: str, secret_key: str) -> str:
    """Token para la API de Kling: un JWT (HS256) firmado con la Secret Key, válido por 30 minutos."""
    now = int(time.time())
    payload = {"iss": access_key, "exp": now + 1800, "nbf": now - 5}
    return jwt.encode(payload, secret_key, algorithm="HS256")
```

El token va en el encabezado `Authorization: Bearer <token>`. Después de eso, envías una solicitud para crear una tarea y consultas su estado siguiendo los pasos de la documentación de Kling: el mismo ciclo de "enviar la tarea → esperar → descargar el clip" que en el ejemplo de Runway.

---

### Luma: aspecto cinematográfico y control del cuadro

Luma AI hace los modelos de video Ray (a octubre de 2026, Ray 3.2: calidad cinematográfica y control de la dirección cuadro por cuadro) y Creative Agent, que crea y afina video, imágenes, audio y texto con el estilo de tu marca. Tiene API. Puedes probarlo gratis en la app en app.lumalabs.ai.

**Qué lo distingue:**

- Control cuadro por cuadro: fijas el primer y el último cuadro → la IA construye la historia entre ellos
- Videos en bucle: ciclos infinitos para fondos de sitios web (revisa si el modelo actual los soporta)
- Creative Agent, que respeta el estilo de tu marca

**Puntos débiles:** caras y personas, así que revísalos con tus propios prompts. Para productos, interiores, naturaleza y arquitectura, pruébalo primero.

**Precios:** se puede empezar gratis; los planes de pago están en el sitio.

**Licencia comercial:** lee las condiciones de tu plan en el sitio antes de entregarle trabajo a un cliente.

---

### Sora (OpenAI): cerrado

OpenAI cerró la app y el sitio de Sora el 26 de abril de 2026, y la API de Sora se desactivó el 24 de septiembre de 2026; no hay reemplazo para video en la API de OpenAI ([página de OpenAI](https://help.openai.com/en/articles/20001152-what-to-know-about-the-sora-discontinuation)). Si un material más viejo te dice que armes un flujo sobre Sora, ese consejo ya no aplica.

**Opciones cercanas:** Google Flow (desde mayo de 2026, el video en Gemini y Flow lo hace el modelo Gemini Omni: clips cortos con sonido; sin suscripción, Flow te da una pequeña cantidad de créditos gratis al día, y los límites actuales están en el sitio de Google) y Pika ([pika.art](https://pika.art), tiene un nivel gratis). Arma tu flujo sobre una plataforma con API: Runway, Kling, Luma.

---

### Tabla comparativa de plataformas

| | Runway | Kling | Luma |
|---|---|---|---|
| Modelo (octubre de 2026) | Gen-4.5 | VIDEO 3.0 (4.0 anunciado) | Ray 3.2 |
| Duración máxima | ver la documentación | hasta 15 s (4.0 anunciado con hasta 30) | ver el sitio |
| Ideal para | Cualquier contenido + API | Movimiento humano, sonido con sincronización de labios | Aspecto cinematográfico, control cuadro por cuadro |
| Para empezar gratis | créditos únicos | plan Basic | gratis en la app |
| Planes de pago | ver [Lo vigente](https://aimayak.com/es/now/) | ver [Lo vigente](https://aimayak.com/es/now/) | ver el sitio |
| API | ✅ | ✅ | ✅ |
| Uso comercial | planes de pago | revisa las condiciones | revisa las condiciones |

Esta tabla refleja los datos a octubre de 2026; para todo lo que cambia rápido, revisa las páginas de cada servicio.

---

### Flujo de trabajo: Claude como guionista + Kling/Runway como equipo de cámara

🎨 **Imagínalo así:** una línea de ensamble de Ford. Cada estación hace una sola cosa, la hace rápido y la pasa a la siguiente. Tú eres el ingeniero que montó la línea, no el trabajador parado frente a ella.

```
La tarea del cliente
      ↓
Claude (guionista): la divide en 5-8 escenas
      ↓
Claude: escribe un prompt para cada escena (en inglés, en lenguaje de cámara)
      ↓
API de Kling / Runway: genera los clips en paralelo
      ↓
FFmpeg: une los clips en un solo video
      ↓
ElevenLabs: agrega una voz en off (opcional)
      ↓
Un video promocional terminado de 30 segundos
```

**El flujo completo en Python:**

```python
import anthropic
import requests
import subprocess
import json
import os
from pathlib import Path
from runwayml import RunwayML, TaskFailedError  # pip install runwayml

claude = anthropic.Anthropic(api_key=os.environ["ANTHROPIC_API_KEY"])
runway = RunwayML()  # clave de la variable de entorno RUNWAYML_API_SECRET


def create_video_scenes(business_info: str) -> list[dict]:
    """Claude escribe el guion: el tema + un prompt para cada escena."""
    response = claude.messages.create(
        model="claude-sonnet-5-5",  # IDs de modelos actuales: ver la documentación de Anthropic
        max_tokens=2000,
        messages=[{
            "role": "user",
            "content": f"""
Escribe el guion de un video promocional de 30 segundos para este negocio:

{business_info}

Devuelve JSON: una lista de 6 objetos:
{{
  "scene_number": 1,
  "duration": 5,
  "description": "Qué mostramos (en palabras sencillas, como referencia)",
  "video_prompt": "Un prompt detallado en inglés para una plataforma de generación de video. Incluye:
                   el tipo de toma (close-up / wide shot / aerial),
                   el movimiento de cámara (dolly in / pan right / static),
                   la iluminación (golden hour / soft natural / studio),
                   el ambiente (warm and inviting / professional / energetic).
                   Al menos 40 palabras."
}}

Devuelve solo el arreglo JSON, sin ninguna otra palabra.
"""
        }]
    )
    return json.loads(response.content[0].text)


def generate_clip(prompt: str, duration: int = 5) -> str:
    """
    Genera un clip mediante la API de Runway y devuelve la URL del video.
    Para usar Kling, reescribe el cuerpo de esta función siguiendo la documentación de la API de Kling:
    el resto del flujo queda igual.
    """
    try:
        task = runway.text_to_video.create(
            model="gen4.5",
            prompt_text=prompt,
            ratio="1280:720",
            duration=duration,
        ).wait_for_task_output()
    except TaskFailedError as error:
        raise RuntimeError(f"Runway: la generación falló: {error.task_details}")
    return task.output[0]


def download_video(url: str, path: str) -> str:
    """Descarga un video desde una URL."""
    r = requests.get(url, stream=True)
    r.raise_for_status()
    with open(path, "wb") as f:
        for chunk in r.iter_content(chunk_size=8192):
            f.write(chunk)
    return path


def concat_with_ffmpeg(video_files: list[str], output: str) -> str:
    """FFmpeg une los clips en un solo video."""
    list_path = "/tmp/ffmpeg_list.txt"
    with open(list_path, "w") as f:
        for vf in video_files:
            f.write(f"file '{os.path.abspath(vf)}'\n")

    subprocess.run([
        "ffmpeg", "-y", "-f", "concat", "-safe", "0",
        "-i", list_path, "-c", "copy", output
    ], check=True, capture_output=True)
    return output


def create_promo_video(business_info: str, output_dir: str = "/tmp/promo") -> str:
    """
    El flujo completo: descripción del negocio → video promocional.
    """
    Path(output_dir).mkdir(parents=True, exist_ok=True)

    print("Claude está escribiendo el guion...")
    scenes = create_video_scenes(business_info)
    print(f"Listo: {len(scenes)} escenas")

    clip_files = []
    for scene in scenes:
        n = scene["scene_number"]
        print(f"Generando escena {n}/{len(scenes)}: {scene['description']}")

        try:
            video_url = generate_clip(
                scene["video_prompt"],
                scene.get("duration", 5)
            )
            clip_path = f"{output_dir}/scene_{n:02d}.mp4"
            download_video(video_url, clip_path)
            clip_files.append(clip_path)
            print(f"  ✅ La escena {n} está lista")
        except Exception as e:
            print(f"  ❌ La escena {n} falló: {e}")

    if not clip_files:
        raise RuntimeError("No se pudo crear ni un solo clip")

    final_path = f"{output_dir}/promo_final.mp4"
    concat_with_ffmpeg(clip_files, final_path)
    print(f"\n🎬 Video final: {final_path}")
    return final_path


# Ejecútalo
if __name__ == "__main__":
    business = """
    "Acme Realty", una agencia inmobiliaria en Cuenca, Ecuador (un ejemplo inventado para esta lección).
    Especialidad: venta de departamentos a compradores que se mudan desde Estados Unidos.
    Ambiente: profesional, confiable, cálido.
    Ventaja única: atención completa en inglés.
    Propiedades clave: departamentos en el centro histórico.
    """
    create_promo_video(business)
```

---

### Restricciones comerciales y licencias

Las condiciones de licencia cambian de un servicio a otro, y también con el tiempo. El panorama general a octubre de 2026:

- **Los planes de pago** suelen permitir el uso comercial (según la página de precios de Runway, ahí es así)
- **Los planes gratis** suelen restringir el uso comercial o agregar una marca de agua
- Quién es dueño del resultado, y las restricciones sobre caras de personas reales y marcas de otras empresas, están en las condiciones de cada servicio

**La regla principal:** antes de entregarle trabajo a un cliente, revisa las condiciones de tu plan en el sitio del servicio y guarda una captura de pantalla. No le prometas a un cliente más de lo que permite la licencia.

---

### Tus costos: cuánto te cuesta hacer un video

Aquí no hay precios para clientes: dependen del mercado, del nicho y del lugar, y nadie puede garantizar ingresos. Solo contamos lo que te cuesta a ti:

- **Créditos de la plataforma:** número de clips × segundos por clip × créditos por segundo × el precio de un crédito en tu plan (cada modelo de Runway tiene su propia tarifa por segundo; ver la página de precios de Runway)
- **Voz y edición:** ElevenLabs, CapCut y otros, con los precios de sus propios planes
- **Tu tiempo:** el guion, revisar cada clip, las correcciones

Esas líneas se suman al precio de tu servicio: [Cómo poner un precio](d02-pricing-simple.md), [Cuánto te cuesta un cliente y cuánto te deja](d01-unit-economics-simple.md). Formatos típicos: videos cortos para redes sociales, un paquete mensual de videos, un recorrido en video de una propiedad.

🎨 **Imagínalo así:** vendes un video, no horas. Al cliente no le importa si te tomó 2 horas o 2 días. Necesita un resultado que cumpla su función.

---

## Práctica

### Paso 1: Configura cuentas y claves (5 min)

1. Entra a [kling.ai](https://kling.ai), la versión internacional de la plataforma; tiene un plan gratis Basic
2. Para un flujo que funcione, crea una cuenta en Runway y obtén una clave de API en el portal para desarrolladores (el enlace está en la documentación, en [docs.dev.runwayml.com](https://docs.dev.runwayml.com))
3. Guárdala: `export RUNWAYML_API_SECRET="tu_clave"`

### Paso 2: Tu primer video a mano (10 min)

Abre Kling → Text to Video. Prueba este prompt (va en inglés, como los que escribe Claude en el flujo; en español dice: interior de un departamento moderno en Cuenca, Ecuador, con luz dorada del atardecer entrando por ventanales, una toma lenta de cámara que descubre una sala abierta con vista a las montañas, diseño contemporáneo, plantas, pisos de madera, paredes blancas, calidad de anuncio inmobiliario, estilo de fotografía profesional):

```
A modern apartment interior in South America. Cuenca, Ecuador.
Warm golden hour sunlight streaming through large windows.
Slow cinematic dolly shot revealing open living room with mountain views.
Contemporary design, plants, wooden floors, white walls.
Real estate advertisement quality. Professional photography style.
```

Mira el resultado. Prueba cambiar 2-3 palabras y compara, para que sientas cómo el prompt cambia la imagen.

### Paso 3: Automatízalo con la API (10 min)

Instala las dependencias:

```bash
pip install anthropic requests runwayml
```

Corre el script `create_promo_video()` con la descripción de un negocio real de tu ciudad. Observa cómo Claude escribe el guion → Runway genera las escenas → FFmpeg une el video final.

### Paso 4: Compara las herramientas (5 min)

Manda el mismo prompt a Runway, Kling y Luma. Compara:

- Calidad de imagen
- Qué tan realista se ve el movimiento
- Tiempo total de espera

Anota para ti qué herramienta funciona mejor para qué tareas. Eso se vuelve la base de lo que les ofreces a tus clientes.

### Paso 5: Arma una muestra para un pequeño negocio (5 min)

Busca un pequeño negocio en tu ciudad que no tenga contenido en video (un restaurante, una agencia, una estética). Prepara:

- Un video de demostración de 15 segundos para su nicho
- Una descripción corta: qué haces exactamente y qué no prometes (por ejemplo, no garantizas que suban las ventas)

Define tu precio y tus condiciones con las lecciones de precios y de economía por cliente (enlaces arriba). Esto es una pieza de portafolio, no una promesa de ingresos.

---

## Herramientas y recursos

- **[Runway](https://runway.com)**: API sólida, control profesional
- **[Kling AI](https://kling.ai)**: movimiento humano, sonido con sincronización de labios
- **[Luma](https://lumalabs.ai)**: modelos de video Ray, control cuadro por cuadro
- **[Google Flow](https://flow.google.com)**: video de Google, con créditos gratis al día
- **[Pika](https://pika.art)**: un conjunto de apps para estilos y efectos, nivel gratis
- **[FFmpeg](https://ffmpeg.org)**: unir y procesar video desde la línea de comandos, gratis
- **[CapCut](https://www.capcut.com)**: edición final con subtítulos y música
- **[ElevenLabs](https://elevenlabs.io)**: voz en off
- **Precios y versiones:** [Lo vigente](https://aimayak.com/es/now/)

---

## Ideas clave

> Al cliente no le importa cómo hiciste el video: en 2 horas con IA o en 2 días con un videógrafo. Necesita un video que resuelva su problema. Las herramientas de IA aceleran la producción, pero revisar cada clip sigue siendo tu trabajo.

> La API de una plataforma es la diferencia entre el trabajo a mano y una línea de producción. A mano, haces los videos uno por uno; un flujo automatizado procesa toda una serie de escenas mientras tú haces otra cosa.

> Las plataformas cambian rápido: Sora fue cerrado, y Runway y Kling lanzaron nuevas generaciones. Arma tu flujo de modo que puedas cambiar de plataforma cambiando una sola función.

---

## Siguiente lección

→ [El flujo de contenido completo: de la idea a la publicación](72-content-pipeline-complete.md)

Vamos a juntarlo todo: texto (Claude) + voz (ElevenLabs) + video (Runway/Kling) + publicación automática (n8n/Buffer).
