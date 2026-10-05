# Ganar dinero con IA: 5 casos de clientes, con cifras

**Tiempo:** unos 30 min de lectura + 20 min de práctica

---

## Lo esencial

Cinco radiografías. Cada caso es una radiografía del negocio de un cliente: se ve el problema, qué está roto por dentro, la solución y el resultado en cifras. Esto no es teoría. Son análisis de proyectos típicos, con las cifras, las herramientas usadas, los errores y lo que funcionó.

Si has buscado formas de ganar dinero con IA que de verdad funcionen, así se ve ese trabajo de cerca: un negocio con un problema real, una construcción y las cuentas detrás del precio.

⚠️ **Importante:** las cifras de estos casos son ilustrativas. Son cálculos de plantilla para enseñarte a calcular el retorno. No son un reporte de clientes reales ni una promesa de ingresos. Tus tarifas, los precios de tus proyectos y tus plazos van a ser distintos. Pon tus propias cifras en la fórmula de la sección "Calculadora de ROI".

---

## Conceptos clave

- **Cálculo del ROI**: cómo calcular cuánto le regresa un proyecto al cliente (ROI, return on investment o retorno de la inversión: lo que el cliente recupera por el dinero que gastó)
- **Tiempo hasta el valor (time-to-value)**: cuántos días pasan antes de que el cliente empiece a ver resultados
- **Estructura de un testimonio de cliente**: cómo reunir testimonios que te ayuden a vender
- **Recurrente vs. único**: un proyecto de una sola vez vs. soporte mensual
- **Un conjunto de herramientas para cada tipo de tarea**: qué usar y por qué

---

## 5 casos con cifras

🎨 **Imagínalo así:** los cinco casos son cinco rutas por la misma ciudad. Una ciudad (la automatización con IA), rutas distintas (boletines, prospectos, un asistente, contenido, un CRM). Cada ruta muestra dónde están los embotellamientos, dónde están las desviaciones y cuánto dura de verdad el viaje.

---

### Caso 1: Automatización de boletines para una agencia digital

**Cliente:** una agencia de marketing digital con 12 clientes y un equipo de 6 personas

**Problema:**
Cada lunes, una persona de marketing pasaba 3 horas armando los reportes semanales de 12 clientes. Los datos se sacaban a mano de Google Analytics, Meta Ads y Google Ads. Copiaba las cifras en una plantilla, escribía comentarios y mandaba los reportes. Un trabajo monótono y tedioso, y había errores.

**Costo del problema:**
```
3 horas × 52 semanas = 156 horas al año
Tarifa de la persona de marketing: $45/hora
Pérdida anual: $7,020
Más el riesgo de errores (pasó: salió un reporte con los datos de otro cliente)
```

**Solución:**
Un flujo automático de boletines en Cloudflare Workers + Trigger.dev:
- Cada domingo a las 11 p.m., Workers saca las métricas de tres API
- Claude Haiku escribe la parte narrativa (tendencias, anomalías, recomendaciones)
- El sistema arma un PDF con Puppeteer
- Un bot de Slack le manda al director de la agencia una vista previa con dos botones: "Enviar a todos" / "Editar"
- Google Sheets lleva un registro de cada envío

**Herramientas:** Cloudflare Workers, Trigger.dev, API de Claude Haiku, Google Analytics API, Meta Marketing API, Google Ads API, Puppeteer (PDF), Slack API, Google Sheets API

**Resultado:**

| Métrica | Antes | Después |
|---|---|---|
| Tiempo dedicado a los reportes | 3 horas/semana | 10 min/semana (revisión) |
| Costo anual | $7,020 | ~$600 (costos de API) |
| Errores | 2-3 al mes | 0 |
| Cuándo recibe el cliente el primer reporte | Lun 11 a.m. | Lun 7 a.m. (antes) |

**Finanzas del proyecto:**
```
Costo de desarrollo: $2,800 (paquete Pro)
Costos de API al mes: ~$50 (Claude Haiku + servicios)
Retorno: unos 5 meses: $2,800 / ($7,020 / 12 - $50)
ROI del primer año: ($7,020 - $600 API - $2,800 proyecto) / $2,800 = 129%
```

(El "paquete Pro" es el nivel intermedio de una oferta Básico/Pro/Empresarial, como en la lección sobre cómo empaquetar tus servicios.)

**Tiempo de construcción:** 9 días hábiles

**Error en el camino:** la Meta Marketing API pedía permisos especiales para leer los datos de las cuentas de anuncios, y se fue un día completo en configurar el flujo OAuth (el intercambio de inicio de sesión y permisos entre apps). Ahora la plantilla reserva 2 días para la autenticación de API.

**Testimonio (uno típico, escrito como ilustración, no es la cita de un cliente real):**
"La primera vez que vi al sistema mandar los 12 reportes solo, un domingo en la noche, no lo podía creer. Lo revisé en la mañana y todo estaba bien. Ahora nuestra persona de marketing dedica el lunes a trabajo de verdad."

---

### Caso 2: Un sistema de generación de prospectos para una empresa SaaS B2B

**Cliente:** una empresa SaaS B2B (software de gestión de proyectos), 8 personas, que vende a pequeños negocios en América Latina

**Problema:**
Un SDR (sales development rep, la persona que consigue prospectos para ventas) buscaba clientes potenciales en LinkedIn a mano, escribía correos personalizados, los mandaba y mantenía el CRM al día. Cada prospecto le tomaba 25-30 minutos. Eso es 8-10 prospectos al día como máximo. Conversión a una llamada: 8%.

**Costo del problema:**
```
Sueldo del SDR: $3,000/mes = $18.75/hora
8 prospectos × 30 min = 4 horas al día ≈ $75/día ≈ $1,500/mes (la mitad del tiempo pagado del SDR)
Resultado: 160-200 prospectos al mes, 13-16 llamadas
```

**Solución:**
Un flujo de generación de prospectos con Claude:
- Se inicia a mano con un comando como "encuentra 20 prospectos en [nicho]"
- Un subagente usa datos de LinkedIn y Apollo.io para encontrarlos (el acceso a la API de LinkedIn es restringido: revisa las condiciones de la plataforma)
- Un segundo subagente busca detalles en LinkedIn para personalizar (su publicación más reciente, vacantes, noticias de la empresa)
- Claude Sonnet escribe un primer correo personalizado para cada prospecto
- El sistema carga todo en HubSpot CRM
- El SDR ve 20 prospectos listos con correos personalizados y hace clic en "Enviar" en cada uno (2-3 minutos de revisión)

**Herramientas:** Claude Code (orquestador), API de Claude Sonnet, datos de LinkedIn, Apollo.io API, HubSpot CRM API, bot de Slack (avisos)

**Resultado:**

| Métrica | Antes | Después |
|---|---|---|
| Prospectos al día | 8-10 | 40-50 (con 2 horas de trabajo del SDR) |
| Tiempo por prospecto | 25-30 min | 2-3 min (revisar y enviar) |
| Conversión a una llamada | 8% | 14% (mejor personalización) |
| Llamadas al mes | 13-16 | 75-90 |

**Finanzas del proyecto:**
```
Desarrollo: $3,200 (proyecto único)
Soporte mensual: $400/mes (monitoreo + actualizaciones de API)
Costos de API: ~$150/mes (Claude Sonnet + Apollo)
Ingresos extra por las nuevas llamadas: el cliente hizo esas cuentas por su lado
```

**Tiempo de construcción:** 14 días hábiles

**Error en el camino:** LinkedIn tiene límites de frecuencia estrictos (topes a cuántas solicitudes puedes mandar en cierto tiempo), y la primera versión fue bloqueada. La solución: poner una pausa entre solicitudes y guardar en caché los datos de los perfiles en Cloudflare KV. Ahora eso es parte estándar de la plantilla de generación de prospectos. Antes de lanzar, lee las condiciones de uso de LinkedIn: la recolección automática de datos de perfiles puede ir contra las reglas de la plataforma.

**Tiempo hasta el valor:** el SDR recibió los primeros 20 prospectos listos el día 3 del desarrollo (un primer vistazo al trabajo en curso). Esto importa: el cliente ve avances pronto.

---

### Caso 3: Un asistente ejecutivo para el director de un pequeño negocio

🎨 **Imagínalo así:** un asistente ejecutivo con IA es un asistente personal que nunca se enferma, nunca se va de vacaciones y se acuerda de todo. Lee el correo, prepara un resumen antes de cada reunión y escribe los reportes. El director trabaja en la estrategia; el asistente se encarga de la operación diaria.

**Cliente:** el director general (CEO) de una empresa de administración de inmuebles: 15 propiedades, un equipo de 4

**Problema:**
El director dedicaba 15-20 horas a la semana a la rutina operativa: contestar por correo dudas de rutina de los inquilinos, armar reportes semanales para los inversionistas, agendar reuniones, preparar materiales para negociaciones. El trabajo estratégico se iba a los fines de semana.

**Costo del problema:**
```
Tarifa del director: $150/hora (su propia estimación)
15 horas de rutina × $150 = $2,250/semana = $9,000/mes
O dicho de otra forma: 15 horas de rutina = 15 horas sin dedicar a la estrategia
```

**Solución:**
Un asistente ejecutivo construido con Claude, con tres módulos:

**Módulo 1: Clasificación del correo**
Revisa el correo entrante cada 30 minutos. Las dudas de rutina (estado de un pago, una solicitud de reparación, una pregunta sobre las condiciones del contrato de renta) reciben una respuesta automática a partir de una base de conocimiento. Todo lo demás se ordena por prioridad y se le reenvía al director en Slack con un resumen corto.

**Módulo 2: Reporte semanal para inversionistas**
Cada viernes a las 5 p.m., saca los datos de las hojas de cálculo de contabilidad y genera un reporte estructurado para los inversionistas con las métricas clave, las anomalías y las recomendaciones. El director lo revisa y lo manda.

**Módulo 3: Preparación de reuniones**
Una hora antes de una reunión (según Google Calendar), reúne los correos más recientes con esa persona, el historial de tratos en el CRM, y noticias relevantes si es un socio externo. Lo junta todo en un resumen corto en Slack.

**Herramientas:** Cloudflare Workers (cron, es decir, tareas programadas), API de Claude Sonnet, Gmail API, Google Calendar API, bot de Slack, Airtable (base de datos de propiedades), Google Sheets (datos financieros)

**Resultado:**

| Métrica | Antes | Después |
|---|---|---|
| Horas de rutina a la semana | 15-20 | 3-4 (revisión y aprobación) |
| Correos de rutina: tiempo de respuesta | 4-24 horas | 15 minutos (automático) |
| Reporte para inversionistas | 2-3 horas/semana | 20 minutos de revisión |
| Preparación de reuniones | 30-45 min | 5 min (el resumen ya está listo) |

**Finanzas del proyecto:**
```
Desarrollo: $5,500 (3 módulos)
Soporte mensual: $750/mes
Costos de API: ~$80/mes
Ahorro para el cliente: ~$9,000/mes (según la propia estimación del cliente)
Retorno: menos de 1 mes
```

**Tiempo de construcción:** 18 días hábiles (tres módulos, uno tras otro)

**Aprendizaje clave:** el director quería automatizar la agenda de reuniones, con la IA proponiendo horarios. Después de analizarlo, decidieron no construirlo: creaba un riesgo de choques en reuniones importantes. Concentrarse en la preparación de reuniones resultó más valioso.

---

### Caso 4: Un flujo de contenido para un canal de YouTube

🎨 **Imagínalo así:** un flujo de contenido es la línea de producción de un periódico. La redacción saca una edición cada día: los reporteros reúnen los hechos, un redactor escribe la nota, un diseñador arma la página. El creador ahora es el editor en jefe: aprueba el tema y edita el texto final. El flujo se encarga de la rutina.

**Cliente:** un creador independiente de YouTube sobre finanzas personales, 180 mil suscriptores

**Problema:**
El 90% del tiempo del creador se iba en la preproducción: buscar temas (5-6 horas), escribir el guion (4-6 horas), preparar la descripción y las etiquetas de YouTube (1 hora), escribir las indicaciones de la miniatura para el diseñador (30 min). Total: 11-14 horas antes de empezar a grabar.

**Solución:**
Un flujo de contenido en tres etapas:

**Etapa 1: Investigación de temas**
Una vez a la semana, un subagente analiza las tendencias de YouTube en el nicho con la YouTube Data API, Reddit (r/personalfinance) y Google Trends. Claude elige 10 temas prometedores y explica cada elección (volumen de búsqueda, competencia, afinidad con la audiencia). El creador escoge 1-2 en 10 minutos.

**Etapa 2: Generación del guion**
Para el tema elegido, Claude Opus (escogido por calidad) escribe un guion completo con el estilo del canal, usando como ejemplo 5 de los mejores guiones anteriores. Estructura: gancho → problema → contenido principal (3-5 secciones) → CTA (llamado a la acción). El creador pasa 30-60 minutos editando en lugar de 4-6 horas escribiendo.

**Etapa 3: Paquete de distribución**
A partir del guion terminado, de forma automática: una descripción para YouTube (optimizada para SEO), 15 etiquetas, las indicaciones de la miniatura para el diseñador, un hilo para Twitter/X y una versión corta para Shorts. Todo en 5 minutos.

**Herramientas:** Trigger.dev (calendario semanal), API de Claude Opus (guiones), API de Claude Haiku (distribución), YouTube Data API, Reddit API, Google Trends (extracción de datos), Slack (entrega)

**Resultado:**

| Métrica | Antes | Después |
|---|---|---|
| Tiempo de preproducción | 11-14 horas | 2-3 horas |
| Videos al mes | 4 | 6-7 |
| Calidad del SEO | Subjetivamente "bien" | Estructurada a partir de datos |

**Finanzas del proyecto:**
```
Desarrollo: $2,400 (paquete Pro)
Soporte mensual: $350/mes (actualizaciones cuando cambian las plataformas)
Costos de API: ~$120/mes (Claude Opus para los guiones cuesta más)
Modelo: totalmente recurrente = ingresos mensuales predecibles
```

**Tiempo de construcción:** 11 días hábiles

**Error en el camino:** los primeros guiones de Claude salían demasiado "pulidos" y no sonaban a este creador en particular. La solución: agregar al contexto 3-5 transcripciones de los mejores videos del canal. Después de eso, el estilo coincidía en un 80% aproximadamente.

---

### Caso 5: Una integración con el CRM para una inmobiliaria

**Cliente:** una inmobiliaria con 8 agentes y 40-60 operaciones activas en todo momento; muchos de sus clientes le escriben a su agente por WhatsApp

**Problema:**
Los agentes pasaban a mano los datos de los clientes entre WhatsApp, el correo, el CRM (HubSpot) y los reportes de Google Sheets. Cada interacción con un cliente implicaba actualizar tres lugares. Algunos datos se perdían. El director de la inmobiliaria no podía ver en tiempo real un panorama actualizado de las operaciones.

**Solución:**
Un centro de integración en Cloudflare Workers:

**Receptor de webhooks:** la WhatsApp Business API manda cada mensaje a un endpoint de Workers (un webhook es un aviso automático que una app le manda a otra cuando pasa algo). Claude lo clasifica: ¿es un prospecto nuevo o un cliente existente? ¿Una pregunta de precio? ¿Una solicitud de visita? ¿La confirmación de una cita?

**Actualización automática del CRM:** según esa clasificación, el registro en HubSpot se actualiza solo: etapa de la operación, fecha del último contacto, un resumen de la conversación (Claude escribe 2-3 oraciones).

**Panel del director:** una hoja de Google con fórmulas muestra en tiempo real: operaciones por etapa, agentes por actividad, las propiedades más solicitadas y las operaciones "estancadas" (sin contacto por más de 7 días).

**Sistema de alertas:** un bot de Slack le avisa al director: un prospecto nuevo muy interesado, una operación sin movimiento, un agente sin actividad por más de 24 horas.

**Herramientas:** Cloudflare Workers, API de Claude Haiku (clasificación; es más barato), WhatsApp Business API, HubSpot API, Google Sheets API, Slack API

**Resultado:**

| Métrica | Antes | Después |
|---|---|---|
| Tiempo dedicado a actualizar el CRM | 15-20 min/agente/día | ~0 (automático) |
| Qué tan actualizados están los datos del CRM | 60-70% (a los agentes se les olvidaba) | 95%+ |
| Tiempo del director revisando el estado | 1-2 horas/día | 15 min/día |
| Prospectos "perdidos" | 5-8% (nunca se registraron) | ~0% |

**Finanzas del proyecto:**
```
Desarrollo: $4,200 (una integración compleja, 4 API)
Soporte mensual: $600/mes (la API de WhatsApp necesita monitoreo)
Costos de API: ~$90/mes
Ahorro: 8 agentes × 20 min/día × 22 días × $25/hora = $1,467/mes
Retorno: unos 3 meses solo por el tiempo ahorrado; unos 5-6 meses
         ya restando el soporte y los costos de API
```

**Tiempo de construcción:** 17 días hábiles (la verificación de la WhatsApp Business API tomó 4 días)

**La lección principal:** la WhatsApp Business API exige que Meta verifique el negocio. Deja un margen de varios días hábiles en el calendario (en este caso tomó 4 días) y avísale al cliente desde el principio.

---

## Patrones en los 5 casos

🎨 **Imagínalo así:** los patrones de estos casos son como las reglas de tránsito escritas después de miles de accidentes. Que la autenticación de API cause retrasos no es mala suerte; así funciona ese camino en particular. Conoce la regla y esquivas el bache en lugar de caer en él.

| Patrón | Qué significa para ti |
|---|---|
| Ingresos recurrentes en 4 de 5 | Ofrece soporte: esa es tu estabilidad |
| La autenticación de API es el principal retraso | Suma 3-5 días para las integraciones |
| Claude Haiku para clasificar | Ahorra dinero donde no hace falta una comprensión profunda |
| Una app de chat (Slack) como canal de entrega | Lo más fácil para el cliente; no hay que construir otra interfaz |
| "Muestra avances pronto" | Enseña un resultado parcial el día 3-5 |

---

## Práctica

**Ejercicio: un cálculo de ROI para tu propio proyecto potencial**

1. Elige a una persona de tu Mapa de Confianza (la lista de contactos cercanos que hiciste en una lección anterior) cuyo problema conozcas

2. Llena la plantilla del caso:
   ```
   Cliente (tipo): ____________
   Problema: ____________
   Horas a la semana que le dedica: ___
   Tarifa por hora: $___
   Pérdida anual: $___
   
   Solución propuesta: ____________
   Herramientas: ____________
   Reducción esperada: ___%
   
   Precio del proyecto: $___
   Soporte mensual: $___
   Retorno: ___ meses
   ```

3. Escribe un título para el caso con una cifra de oro (la única cifra que muestra el resultado de un vistazo)

4. Identifica qué API podría dar problemas (pide verificación o tiene una configuración OAuth complicada) y suma días al calendario

**Meta:** un cálculo de ROI terminado para tu primera conversación real con un cliente potencial.

---

## Calculadora de ROI: una fórmula universal

🎨 **Imagínalo así:** una calculadora de ROI funciona como el simulador de crédito hipotecario en el sitio de un banco. El cliente ve el pago mensual y piensa: "Eso sí lo puedo pagar". Tú le muestras: invierte $3,500 → ahorra $23,000 al año → lo recuperas en 2 meses. La calculadora convierte un precio abstracto en una decisión concreta.

```
### Calculadora de ROI para cualquier proyecto

Costo actual del proceso:
  [horas/semana] × [tarifa $/hora] × 52 semanas = [costo anual del problema]

Costo de la automatización:
  [desarrollo único] + [soporte mensual × 12] + [costos de API × 12] = [costo anual de la solución]

ROI = (Ahorro - Costo de la solución) / Costo de la solución × 100%

Retorno = Costo de desarrollo / Ahorro mensual = [X meses]
```

**Ejemplo (del Caso 1):**
```
Costo anual del problema: 3 h/semana × $45/hora × 52 = $7,020
Costo anual de la solución: $2,800 + $0 soporte + $600 API = $3,400
ROI = ($7,020 - $3,400) / $3,400 = 106%
Retorno = $2,800 / ($7,020/12 - $50 API) = 5.2 meses
```

**Ejemplo (del Caso 3, el asistente ejecutivo):**
```
Costo anual del problema: 15 h/semana × $150/hora × 52 = $117,000
Costo anual de la solución: $5,500 + $9,000 + $960 = $15,460
ROI = ($117,000 - $15,460) / $15,460 = 557%
Retorno = $5,500 / ($9,000 - $750 soporte - $80 API) = 0.7 meses
```

Arma este cálculo una vez en Google Sheets y úsalo en cada conversación de venta.

---

## Errores comunes

- **ROI de palabra, no en papel.** "Vas a ahorrar mucho tiempo" no convence a nadie. "$23,040 al año de ahorro con una inversión de $3,500, recuperada en 2 meses" sí. Muestra un archivo de Excel o de Google Sheets con las fórmulas.
- **Inflar el ROI.** Si la automatización de verdad cubre el 70% del trabajo, no digas 100%. Un ROI honesto genera confianza. Y si el cliente ve que el resultado real supera lo que prometiste, se lo va a contar a sus conocidos.
- **Dejar los costos de API fuera de las cuentas.** API de Claude, Apify, Gmail API: todo cuesta. $50-150/mes en API: inclúyelo siempre en el costo de la solución que le muestras al cliente.
- **Ignorar el costo de oportunidad.** Un director que pasa 15 horas en la rutina = 15 horas que NO dedica a la estrategia. El costo no es solo $150/hora × 15; también son los tratos y las decisiones que nunca pasaron.

---

## Cómo se conecta con otras lecciones

- **→ [Precios](39-monetization-pricing.md)**: la fórmula de ROI de esta lección es la base para fijar precios según el valor
- **→ [Portafolio y casos de estudio](41-portfolio-case-studies.md)**: estos 5 casos son plantillas para tus propios casos de estudio
- **→ [El modelo de fábrica](48-factory-model.md)**: los patrones de estos casos son la base de las plantillas de la Fábrica

---

## Herramientas y recursos

- **Trigger.dev**: [trigger.dev](https://trigger.dev/): pone en marcha flujos que corren con un calendario; tiene plan gratis (a octubre de 2026, con un crédito mensual de $5)
- **Apollo.io**: [apollo.io](https://www.apollo.io/): una base de datos de contactos B2B para proyectos de generación de prospectos
- **HubSpot**: un CRM con un nivel gratis y una API
- **WhatsApp Business API**: a través de [Meta for Developers](https://developers.facebook.com/); exige la verificación del negocio (Meta pone los plazos, así que deja un margen)
- **Precios de la API de Claude**: [platform.claude.com/docs/en/about-claude/pricing](https://platform.claude.com/docs/en/about-claude/pricing): para tener costos de API precisos en tus cuentas de ROI; hay un resumen en la página [Lo vigente](https://aimayak.com/now/)
- **Google Sheets**: para armar tu calculadora de ROI (la armas una vez y la usas con cada cliente)

---

## Ideas clave

> Los ingresos recurrentes son lo que le da estabilidad al negocio. Solo uno de los 5 casos es de una sola vez. Ofrece siempre soporte mensual.

> La autenticación de API es la principal fuente de retrasos. Deja un margen y avísales a tus clientes.

> Muestra resultados pronto. Haz una demostración parcial el día 3-5. El cliente ve avances y la confianza crece.

> Un cálculo de ROI vende mejor que cualquier palabra. Las cifras quitan las dudas.

---

## Siguiente lección

→ [El modelo de fábrica](48-factory-model.md): plantillas y repetibilidad
