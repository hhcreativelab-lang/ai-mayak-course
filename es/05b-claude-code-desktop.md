# Claude Code de escritorio: empieza sin la terminal

**Tiempo:** unos 30 min de lectura + 40 min de práctica

---

## Lo esencial

Hay tres formas de trabajar con Claude Code: en la terminal (una ventana donde escribes comandos de texto), en VS Code (un editor de código popular de Microsoft) y en la app de escritorio de Claude, un programa que instalas en tu computadora como cualquier otra app. Esta lección trata de la app de escritorio. Es una herramienta para el trabajo diario: tres pestañas, sesiones en paralelo, una terminal integrada, un programador de tareas y cambio de modelo con un solo clic.

Para quienes no programan, esta suele ser la forma más fácil de entrar a Claude Code: instalas una app, haces clic aquí y allá, y escribes tus solicitudes en lenguaje normal, en español. No necesitas abrir una terminal para empezar.

🎨 **Imagínalo así:** VS Code con la extensión es como contratar a un chef para que trabaje en la cocina de tu restaurante. La app de escritorio es como abrir tu propio restaurante: cocina, comedor y caja, todo en un solo lugar, bajo un mismo techo.

---

## Conceptos clave

- **Claude Code Desktop**: así llama la documentación a Claude Code dentro de la app de escritorio de Claude (macOS y Windows, con una beta para Linux). La app tiene tres pestañas: Chat, Cowork, Code
- **La pestaña Code**: la principal; trabajo práctico con código y archivos en tu computadora
- **La pestaña Chat**: una conversación normal con Claude (sin acceso a tus archivos), igual que claude.ai en tu navegador
- **La pestaña Cowork**: Dispatch (una conversación continua con Claude a la que le puedes mandar tareas, incluso desde tu celular) y trabajo más largo de agentes (un agente es un programa que realiza tareas por su cuenta): investigación, documentos, hojas de cálculo
- **Modos de permisos**: cuánta libertad le das al agente (desde "pregúntame todo" hasta "adelante, hazlo por tu cuenta")
- **Modelos**: Haiku (rápido), Sonnet (más rápido y más barato que Opus), Opus (el predeterminado), Fable (las tareas más largas y difíciles); puedes cambiar entre ellos a mitad de una sesión. Nombres y versiones vigentes: [Lo vigente](https://aimayak.com/now/)
- **Sesiones en paralelo**: varias conversaciones con el agente al mismo tiempo, cada una con su propia tarea
- **Tareas programadas**: un programador; el agente arranca solo, según un horario

---

## Teoría

### Cómo instalar la app de escritorio

🎨 **Imagínalo así:** instalar Claude Code Desktop es como instalar Word o Photoshop. Lo descargas, lo abres, inicias sesión. Sin Node.js, sin comandos de npm (npm es el gestor de paquetes de Node.js), sin terminal para empezar.

**Requisitos del sistema:**

- **macOS 13.0+** (Ventura o posterior), Intel o Apple Silicon
- **Windows 10 1809+** o Windows Server 2019+
- Linux: la app está en **beta** (Ubuntu y Debian, se instala con apt o con un paquete .deb); la versión de terminal (la CLI, o interfaz de línea de comandos) funciona en Linux sin restricciones
- 4 GB de RAM, conexión a internet y Git (un sistema de control de versiones que lleva el registro de los cambios en el código): solo lo necesitas para las sesiones aisladas (la opción worktree, explicada más abajo). La mayoría de las Mac ya lo traen

**Opción 1: descárgala directamente**

| Plataforma | Enlace |
|---|---|
| **macOS Universal** (Intel + Apple Silicon) | [claude.ai/api/desktop/darwin/universal/dmg/latest/redirect](https://claude.ai/api/desktop/darwin/universal/dmg/latest/redirect) |
| **Windows x64** | [claude.ai/api/desktop/win32/x64/setup/latest/redirect](https://claude.ai/api/desktop/win32/x64/setup/latest/redirect) |
| **Windows ARM64** | [claude.ai/api/desktop/win32/arm64/setup/latest/redirect](https://claude.ai/api/desktop/win32/arm64/setup/latest/redirect) |

**Opción 2: Linux (beta):** instálala con apt o con un paquete .deb para Ubuntu y Debian. Instrucciones: [Claude Desktop on Linux](https://code.claude.com/docs/en/desktop-linux) (Claude Desktop en Linux).

> El comando `brew install --cask claude-code` instala la versión de terminal de Claude Code, no esta app. La versión de terminal se explica en la lección [Modos de arranque de la CLI](08-work-modes.md).

Después de descargarla: abre el DMG (macOS) o el Setup.exe (Windows) → instálala como cualquier otra app → ábrela → inicia sesión en tu cuenta de Anthropic (la misma que usas en claude.ai) → abre la pestaña Code, en la parte de arriba de la ventana.

**Necesitas un plan de pago:** Pro, Max, Team o Enterprise. El plan gratuito de Claude no incluye Claude Code: si haces clic en la pestaña Code con el plan gratuito, la app te pide subir de plan. Precios vigentes de los planes: [Lo vigente](https://aimayak.com/now/).

---

### Tres pestañas: Chat, Cowork, Code

🎨 **Imagínalo así:** las tres pestañas son como tres pisos de un mismo edificio. El primer piso (Chat) es una sala de juntas donde solo platicas. El segundo piso (Cowork) es el taller, al que puedes mandar un trabajo incluso desde tu celular. El tercer piso (Code) es tu oficina privada con computadora: aquí tú y el agente trabajan juntos en los archivos.

| Pestaña | Qué hace | Para qué sirve |
|---|---|---|
| **Chat** | Una conversación con Claude sin acceso a tus archivos | Preguntas, análisis, explicaciones, sin código |
| **Cowork** | Dispatch y trabajo más largo de agentes | Investigación, documentos, hojas de cálculo; tareas enviadas desde tu celular (Dispatch requiere un plan Pro o Max) |
| **Code** | Trabaja con los archivos locales de tu computadora | Programación, automatización, proyectos |

**La pestaña principal de este curso es Code.** Aquí el agente lee tus archivos, escribe código y ejecuta comandos.

Desde el 16 de septiembre de 2026, Anthropic está uniendo Chat y Cowork en uno solo. La actualización llega poco a poco, primero a los planes Pro y Max. Si ves una sola pestaña donde esta lección muestra esas dos, no pasa nada: la pestaña Code funciona igual.

---

### La interfaz de la pestaña Code

🎨 **Imagínalo así:** la pestaña Code es como la cabina de un avión. La barra lateral de la izquierda (tu lista de sesiones) es el GPS y los mapas. El centro es el parabrisas por donde ves lo que estás haciendo. Abajo están los pedales y las palancas (modelos, modos, el cuadro de texto).

**La barra lateral:**

- Una lista de todas tus sesiones; cada sesión es una conversación aparte con el agente
- El botón `+ New session` (nueva sesión) (Cmd+N / Ctrl+N): una conversación nueva y limpia
- La sección **Scheduled** (programadas): sesiones de tareas programadas
- Una insignia **Dispatch** en una sesión: la inició Dispatch, por ejemplo con una tarea que mandaste desde tu celular
- El botón **Routines** (rutinas): crear y administrar horarios
- El botón **Customize** (personalizar): administrar en un solo lugar los conectores (enlaces con servicios externos como Google Calendar o Slack), las skills y los plugins

**El cuadro de texto (abajo):**

- El texto de tu solicitud
- El botón `+`: adjuntar un archivo, una imagen o un PDF
- El menú desplegable **Environment** (entorno): Local / Cloud / SSH (en Windows, también WSL)
- El menú desplegable **Model** (modelo): elige el modelo (Haiku / Sonnet / Opus / Fable)
- El selector del modo de permisos, junto al botón de enviar
- El botón de enviar / detener (Esc)

**Paneles (puedes abrirlos y ocultarlos):**

| Panel | Qué muestra | Atajo de teclado |
|---|---|---|
| Chat | Tu conversación con Claude | — |
| Diff | Los cambios en el código (+/-) | Cmd+Shift+D |
| Browser | Un navegador integrado: tu app en ejecución y cualquier sitio web | Cmd+Shift+B |
| Terminal | La terminal integrada | Ctrl+` |
| Tasks | Tareas en segundo plano y subagentes | — |
| Plan | El plan de acción de Claude | — |

**Vistas de la transcripción:**

Abajo, una "tool call" (llamada a herramienta) es una sola acción que hace Claude, como leer un archivo o ejecutar un comando.

- **Normal**: las tool calls se agrupan en resúmenes cortos
- **Verbose** (detallada): ves cada paso y cada tool call
- **Thinking** (razonamiento): las tool calls se agrupan, pero puedes ver el razonamiento de Claude
- Para cambiar: `Ctrl+O`

---

### Cómo elegir un modelo

🎨 **Imagínalo así:** elegir un modelo es como elegir una herramienta en una obra. Haiku es un martillo para trabajos pequeños. Sonnet es un rotomartillo: más rápido y más barato. Opus es una grúa de construcción, y en las suscripciones es la que te toca por defecto. Fable es la maquinaria pesada para los trabajos más largos y difíciles. Cambias a mitad del trabajo, sin detener la obra.

Para cambiar de modelo: el menú desplegable junto al botón de enviar. Funciona **durante una sesión**; no tienes que empezar de nuevo.

Modelos a octubre de 2026 (lista vigente: [Lo vigente](https://aimayak.com/now/)):

| Modelo | Alias | Para qué sirve | Velocidad / costo |
|---|---|---|---|
| **Haiku 4.5** | `haiku` | Tareas simples y rápidas | El más rápido / el más barato |
| **Sonnet 5.5** | `sonnet` | Trabajo diario | Más rápido y más barato que Opus |
| **Opus 5.5** | `opus` | Razonamiento complejo, decisiones de arquitectura | El modelo predeterminado |
| **Fable 5.1** | `fable` | Las tareas más largas y difíciles | Potente / en las suscripciones puede consumir créditos de uso |
| **OpusPlan** | `opusplan` | Opus planea, Sonnet ejecuta el plan | Híbrido |

Fable 5.1, Opus 5.5 y Sonnet 5.5 tienen una ventana de contexto de 1 millón de tokens (el contexto es todo lo que la IA puede ver de la conversación a la vez; los tokens son los pedacitos de texto que la IA lee y escribe), así que no necesitan una versión aparte con `[1m]`.

**Modelo predeterminado** (el que está puesto a menos que lo cambies): en todas las suscripciones (Pro, Max, Team, Enterprise) y en la API, el predeterminado es Opus 5.5. Antes, el plan Pro usaba Sonnet por defecto; ya no es así.

**Niveles de esfuerzo:**

Puedes elegir qué tanto piensa Claude: `low`, `medium`, `high`, `xhigh`, `max`. Los niveles disponibles dependen del modelo, así que revisa qué ofrece el menú para el que elegiste.

- Menú: `Cmd+Shift+E`
- O escribe `ultrathink` en tu prompt (un prompt es la solicitud en texto que le das a la IA), y Claude pensará con más profundidad esa solicitud

**Razonamiento extendido (extended thinking):**

- Opus 5.5, Sonnet 5.5 y Fable siempre tienen activado el razonamiento extendido; no hay un botón aparte para eso
- Puedes ver el razonamiento de Claude en la vista Thinking o Verbose (cambia con `Ctrl+O`)

---

### Modos de permisos

🎨 **Imagínalo así:** los modos de permisos son qué tanto confías en un contratista con las llaves de tu casa. Manual: el trabajador pregunta antes de cada paso. Accept edits: el trabajador hace cambios por su cuenta, pero pregunta antes de abrir el gas. Auto: el trabajador hace todo mientras una cámara de seguridad lo vigila. Bypass: confianza total, sin cámara, y solo para instalaciones de prueba aisladas.

Para elegir: el menú desplegable junto al botón de enviar. Atajo de teclado: `Cmd+Shift+M`.

| Modo | Qué hace | Cuándo usarlo |
|---|---|---|
| **Manual** (el valor en la configuración es `default`; antes se llamaba Ask permissions) | Pregunta antes de cada archivo y cada comando | Para aprender, tareas desconocidas |
| **Accept edits** (aceptar ediciones; antes Auto accept edits) | Edita archivos por su cuenta, pregunta antes de ejecutar comandos | Tienes clara la tarea y quieres velocidad |
| **Plan** (antes Plan Mode) | Solo analiza, no cambia nada | Para ver qué planea hacer Claude |
| **Auto** | Trabaja sin las preguntas habituales, mientras un modelo verificador aparte compara cada acción con lo que pediste | Usuarios con experiencia, tareas de confianza |
| **Bypass permissions** (omitir permisos) | Casi ninguna pregunta | **Solo** en contenedores aislados (un entorno de prueba cerrado, sin nada importante adentro) |

Auto aparece en la lista cuando elegiste un modelo que lo admite (Opus 4.6 o posterior, Sonnet 4.6 o posterior, o Fable); en una organización, un administrador puede desactivarlo. Bypass permissions aparece solo después de activarlo en la configuración. Revisa la lista en tu versión de la app para ver qué modos tienes.

💡 **Si apenas empiezas:** fíjate qué modo está seleccionado y cámbialo a Manual. Hace muchas preguntas, y de eso se trata: ves lo que el agente va a hacer con tus archivos antes de que lo haga. La app recuerda el modo que eliges para cada carpeta. Pasa a Accept edits cuando tengas clara la tarea.

---

### Sesiones en paralelo

🎨 **Imagínalo así:** las sesiones en paralelo son como varias cuadrillas de construcción en pisos distintos. La primera cuadrilla hace el techo, la segunda la instalación eléctrica, la tercera los acabados. Tú, como contratista general, pasas a revisar cada una.

Cada sesión tiene su propio historial de conversación. Pero dos sesiones abiertas en la misma carpeta editan los mismos archivos. Para separarlas, la app puede darle a una sesión **su propia copia del proyecto**: al iniciar la sesión, activa la opción **worktree** junto al nombre de la rama. Solo funciona en una carpeta que Git lleva registrada (un repositorio) y necesita que Git esté instalado.

**Cómo administrar las sesiones:**

| Acción | Mac | Windows |
|---|---|---|
| Nueva sesión | `Cmd+N` | `Ctrl+N` |
| Cerrar sesión | `Cmd+W` | `Ctrl+W` |
| Sesión siguiente | `Ctrl+Tab` | `Ctrl+Tab` |
| Sesión anterior | `Ctrl+Shift+Tab` | `Ctrl+Shift+Tab` |
| Abrir lado a lado | `Cmd+clic` en una sesión | `Ctrl+clic` en una sesión |

**Side chat** (chat lateral): una pregunta al margen que no interrumpe la conversación principal:

- `Cmd+;` (macOS) / `Ctrl+;` (Windows)
- O escribe `/btw` en tu prompt

---

### Entornos

🎨 **Imagínalo así:** el entorno es donde trabaja tu agente. Local: el agente está en tu oficina. Cloud: el agente trabaja en la nube (y sigue trabajando aunque tú ya te hayas ido a casa). SSH: el agente está en un servidor remoto.

| Entorno | Dónde trabaja el agente | Ventajas |
|---|---|---|
| **Local** | En tu computadora | Acceso directo a tus archivos |
| **Cloud** | En la nube de Anthropic (una sesión en la nube) | Sigue trabajando con la app cerrada, varios repositorios |
| **SSH** | En una máquina remota | Trabajar con un servidor de producción (el servidor en vivo del que dependen tus usuarios reales), un VPS, un Dev Container |

Si apenas empiezas, te basta con Local. Lo demás te servirá más adelante.

**Cómo configurar una conexión SSH:**

1. Menú desplegable Environment → `+ Add SSH connection`
2. Llena: Name, SSH Host (`user@hostname`), SSH Port (22 por defecto), Identity File
3. Claude Code se instala solo en la máquina remota la primera vez que te conectas

---

### Tareas programadas

🎨 **Imagínalo así:** una tarea programada es como ponerle una alarma al agente. Tú te vas a dormir, el agente se despierta, hace el trabajo y vuelve a dormirse hasta la próxima vez. En la mañana, el resultado te está esperando.

Para crear una: la pestaña Code → **Routines** en la barra lateral → **New routine** → Local.

**Campos:**

- **Name**: un nombre (por ejemplo, `morning-report`)
- **Instructions**: lo que Claude debe hacer (texto normal, en lenguaje sencillo). Aquí mismo eliges la carpeta de trabajo; sin ella no puedes guardar la tarea
- **Schedule**: cuándo se ejecuta

**Opciones de horario:**

| Tipo | Ejemplo |
|---|---|
| Manual | Solo se ejecuta a mano |
| Hourly | Cada hora |
| Daily | Todos los días a las 9:00 AM |
| Weekdays | De lunes a viernes a las 8:30 AM |
| Weekly | Los lunes a las 10:00 AM |

Intervalo mínimo: **1 minuto**. Si necesitas un intervalo que no está en la lista, pídele a Claude en cualquier sesión que lo configure.

**Local vs. en la nube:**

- Local: se ejecutan mientras la app está abierta, con acceso a tus archivos
- En la nube (routines): se ejecutan aunque tu computadora esté apagada, se pueden activar con la API (una API es una forma en que los programas se comunican entre sí) o con un evento de GitHub; intervalo mínimo de 1 hora

**Consejo:** las tareas locales solo se ejecutan mientras la app está abierta y tu computadora no está en reposo. Activa **Keep computer awake** (mantener la computadora despierta) (`Settings → This computer → System`) si usas tareas nocturnas. Cerrar la tapa de la laptop igual la pone en reposo.

---

### Computer use (uso de la computadora)

🎨 **Imagínalo así:** computer use es como dejar que el agente vea tu pantalla y use tu mouse y tu teclado. Ve lo que pasa y puede hacer clic, escribir y desplazarse. Es como un escritorio remoto, solo que el agente decide qué hacer.

- Requiere un plan **Pro o Max** (no está disponible en Team ni Enterprise); la función es una research preview (una versión temprana que todavía se está probando)
- Para activarla: `Settings → This computer → System`, sección **Computer use**
- macOS: necesita los permisos de Accessibility (Accesibilidad) y Screen Recording (Grabación de pantalla)

⚠️ Esto permite que el agente actúe dentro de tus apps, así que pruébalo primero con algo inofensivo y mantén cerradas las ventanas sensibles (banco, correo) mientras experimentas.

**Tres niveles de acceso a las apps:**

| Nivel | Apps |
|---|---|
| Solo ver | Navegadores, plataformas de inversión |
| Solo hacer clic | Terminales, IDE (entornos de desarrollo integrados, los programas donde los desarrolladores escriben código) |
| Control total | Todo lo demás |

---

### Atajos de teclado clave del escritorio (lista completa)

> `Cmd+/` muestra todos los atajos de teclado dentro de la app. En Windows, presiona Ctrl donde veas Cmd

| Atajo (Mac) | Qué hace |
|---|---|
| `Cmd+N` | Nueva sesión |
| `Cmd+W` | Cerrar sesión |
| `Esc` | Detener la respuesta de Claude |
| `Cmd+Shift+D` | Panel Diff (ver los cambios) |
| `Cmd+Shift+B` | Browser (con tu app y sitios web) |
| `` Ctrl+` `` | Terminal integrada |
| `Cmd+;` | Side chat (preguntar algo sin interrumpir el hilo principal) |
| `Ctrl+O` | Vista de la transcripción (Normal / Thinking / Verbose) |
| `Cmd+Shift+M` | Menú de modos de permisos |
| `Cmd+Shift+I` | Menú de modelos |
| `Cmd+Shift+E` | Menú de esfuerzo (qué tanto piensa Claude) |
| `Cmd+/` | Mostrar todos los atajos de teclado |

---

### Desktop vs. extensión de VS Code vs. CLI: una comparación

🎨 **Imagínalo así:** tres herramientas para el mismo trabajo. La CLI es un bisturí: precisa y flexible en manos con práctica. VS Code es una navaja suiza: editor y agente en uno. Desktop es tu propio centro quirúrgico: varios quirófanos (sesiones), su propio equipo (paneles), un calendario de guardias (tareas programadas).

| Función | CLI | Desktop | VS Code |
|---|---|---|---|
| Sesiones en paralelo | Terminales separadas | ✅ Barra lateral integrada | ✅ Pestañas y ventanas |
| Terminal integrada | Ella misma corre en una terminal | ✅ | ✅ (la terminal de VS Code) |
| Diff visual | ❌ | ✅ | ✅ |
| Adjuntar archivos/fotos | ❌ | ✅ | ✅ |
| Pantalla de tareas programadas | ❌ (los horarios se configuran de otra forma, por ejemplo con cron, una herramienta del sistema que ejecuta tareas según un horario) | ✅ | — |
| Computer use | Solo macOS, planes Pro y Max | ✅ macOS y Windows, planes Pro y Max | — |
| Conexión SSH desde la app | No hace falta: se instala directo en el servidor | ✅ | — |
| Sesiones en la nube | ✅ (`claude --cloud`) | ✅ | Solo para retomar una que ya empezaste |
| Agent teams (experimental, desactivado por defecto) | ✅ | ❌ | — |
| Automatización/scripts | ✅ (`--print`) | ❌ | ❌ |
| Linux | ✅ | beta | ✅ |

"—" significa que la documentación de la extensión no describe esa función.

**En resumen:** Desktop es la mejor opción para el trabajo práctico diario. La CLI es para automatización y scripts. VS Code es para cuando quieres todo en un solo editor.

---

## Errores comunes

❌ **Error:** Abriste la app de escritorio y te quedaste en la pestaña Chat, pensando que Chat es Claude Code.

✅ **Mejor:** Chat es solo una conversación, sin acceso a tus archivos. Para trabajar con código necesitas la pestaña **Code**.

❌ **Error:** Activar Fable para cada tarea "para que salga mejor".

✅ **Mejor:** Para la mayoría de las tareas diarias el modelo predeterminado es más que suficiente, y Sonnet es más rápido y más barato. Fable es para tareas realmente largas y complejas, y en las suscripciones puede consumir créditos de uso. Haiku es para solicitudes rápidas y sencillas. No gastes tokens (las pequeñas unidades de texto con las que trabaja la IA) en balde.

❌ **Error:** Trabajar en modo Bypass permissions en proyectos reales con datos importantes.

✅ **Mejor:** Bypass permissions es solo para entornos de prueba aislados. En proyectos reales, usa Manual, Accept edits o Auto.

❌ **Error:** Iniciar dos sesiones en la misma carpeta y extrañarte de que se estorben.

✅ **Mejor:** Las sesiones en la misma carpeta editan los mismos archivos. Dales carpetas distintas, o activa la opción worktree para que cada una tenga su propia copia del proyecto.

❌ **Error:** Activar la opción worktree sin tener Git instalado.

✅ **Mejor:** Una copia aparte del proyecto necesita Git. En Windows, instala [Git for Windows](https://git-scm.com/download/win) y vuelve a iniciar la sesión.

---

## Práctica

**Ejercicio: tu primer día en la app de escritorio**

Los pasos usan los atajos de Mac; en Windows, presiona Ctrl donde veas Cmd.

**Paso 1: Instálala (10 min)**

1. Descarga la app de escritorio con el enlace de tu sistema operativo (arriba)
2. Instálala como cualquier otra app
3. Ábrela → inicia sesión en tu cuenta de Anthropic

**Paso 2: Explora la interfaz (5 min)**

1. Abre la pestaña Code, en la parte de arriba de la ventana
2. Presiona `Cmd+/` y revisa la lista de atajos de teclado
3. Abre el menú desplegable de modelos y mira qué hay disponible
4. Abre la lista de modos de permisos, lee sobre cada modo y elige Manual

**Paso 3: Tu primera sesión (10 min)**

1. Presiona `Cmd+N` para una nueva sesión
2. Deja Environment en Local, haz clic en **Select folder** y elige una carpeta (para tu primer intento, crea una carpeta de prueba vacía)
3. Escribe: `¿Qué ves en esta carpeta? Describe su estructura.`
4. Observa cómo el agente explora los archivos

💡 Para tu primerísimo intento, usa una carpeta de prueba y no una con documentos importantes, y revisa que el modo esté en Manual para que Claude pregunte antes de cambiar algo.

**Paso 4: Sesiones en paralelo (5 min)**

1. Presiona `Cmd+N` otra vez para crear una segunda sesión
2. Pregunta una cosa en la primera sesión y otra distinta en la segunda
3. Cambia entre ellas con `Ctrl+Tab`
4. Comprueba que cada una conserve su propia conversación

**Paso 5: Crea tu primera tarea programada (10 min)**

1. Haz clic en **Routines** en la barra lateral → **New routine** → **Local**
2. Name: `morning-check`
3. Instructions: `Revisa todos los archivos .md de esta carpeta y dime qué hay de nuevo.` Elige la misma carpeta de prueba
4. Schedule: Manual (por ahora, solo se ejecuta a mano)
5. Guarda la tarea, haz clic en **Run now** y observa cómo funciona

Terminaste cuando la app está instalada, el agente respondió tu pregunta sobre la carpeta de prueba y la tarea `morning-check` se ejecutó y mostró un resultado.

---

## Herramientas y recursos

- **[Claude Code Desktop: descarga (macOS)](https://claude.ai/api/desktop/darwin/universal/dmg/latest/redirect)**: DMG Universal (Intel + Apple Silicon)
- **[Claude Code Desktop: descarga (Windows x64)](https://claude.ai/api/desktop/win32/x64/setup/latest/redirect)**: Setup EXE
- **[Guía oficial: Desktop Quickstart](https://code.claude.com/docs/en/desktop-quickstart)**: el inicio rápido de Anthropic
- **[Full Desktop Reference](https://code.claude.com/docs/en/desktop)** (referencia completa de Desktop): todas las funciones de la interfaz
- **[Model Configuration](https://code.claude.com/docs/en/model-config)** (configuración de modelos): cómo administrar modelos y niveles de esfuerzo
- **[Desktop Scheduled Tasks](https://code.claude.com/docs/en/desktop-scheduled-tasks)**: tareas programadas
- **[Git for Windows](https://git-scm.com/download/win)**: necesario en Windows para las sesiones aisladas

Lecciones de la biblioteca, opcionales:

→ Mira la lección [Cómo instalar VS Code y la extensión](05-setup.md): la ruta alternativa con VS Code

→ Mira la lección [Modos de arranque de la CLI](08-work-modes.md): si quieres trabajar en la terminal

→ Mira la lección [Loop y tareas programadas](35-loop-scheduled-tasks.md): una mirada más a fondo a la programación de tareas

---

## Ideas clave

> Claude Code Desktop es una app nativa con tres pestañas. Para programar necesitas la pestaña Code. Chat es solo una conversación, sin archivos.

> Puedes cambiar de modelo a mitad de tu trabajo. Opus es el predeterminado, Sonnet es más rápido y más barato, Haiku es para tareas rápidas y Fable es para las más difíciles.

> Mientras aprendes, usa el modo Manual y una carpeta de prueba: el agente pregunta antes de cada cambio.

> Las tareas programadas son un agente con horario. Las tareas locales solo se ejecutan mientras la app está abierta y tu computadora está despierta.

---

## Próxima lección

→ [Crea sitios web y aplicaciones web con Claude Code](15-websites-webapps.md): tu primera construcción, un sitio web a partir de una descripción con palabras

Cómo darle al agente instrucciones claras ya lo viste en [Cómo escribir un buen prompt para Claude Code](06-prompting-fundamentals.md); vale la pena releerla antes de la práctica.
