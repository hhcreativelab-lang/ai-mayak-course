# Cómo entregar un proyecto y conservar al cliente

**Tiempo:** unos 25 min de lectura + 30 min de práctica

---

## Lo esencial

Vender una casa no termina cuando entregas las llaves. Termina cuando le mostraste al comprador dónde están los apagadores, cómo funciona el calentador de agua y con qué vecino es fácil tratar, y te aseguraste de que el nuevo dueño se sienta en casa. La entrega es un recorrido guiado por el sistema para tu cliente. Conservar al cliente es llamar un mes después y preguntar: "¿Cómo va el calentador?". Muchos freelancers entregan las llaves y desaparecen. Es un error.

---

## Conceptos clave

- **Protocolo de entrega**: una entrega ordenada: documentación, capacitación, accesos
- **Un SOP para el cliente**: instrucciones escritas para alguien que no es programador
- **Un recorrido en Loom**: un video de 5 minutos que recorre el sistema (mejor que 10 páginas de texto)
- **Un mes de soporte incluido**: el periodo en que el cliente se acostumbra al sistema
- **Venta adicional (upsell)**: "también podrías automatizar..." como el siguiente paso natural
- **Un reporte mensual**: cifras que muestran cada mes cuánto vale el sistema
- **Puntaje NPS**: una sola pregunta que muestra qué tan satisfecho está el cliente

---

## Teoría

### Por qué la entrega importa más que el producto mismo

Un buen sistema + una entrega pobre = un cliente insatisfecho.
Un sistema promedio + una gran entrega = un cliente contento que te recomienda.

El cliente no compra código ni Cloudflare Workers. Compra **la solución a un problema** y **la confianza de que funciona sin él**. Tu trabajo es construir esa confianza con la entrega.

🎨 **Imagínalo así:** vendes una casa amueblada. No dejas las llaves en la barra de la cocina y ya. Le das un recorrido al comprador: aquí están los apagadores, aquí está el filtro del calentador (cámbialo cada pocos meses), aquí tienes el número de un plomero de confianza. El comprador sale sintiéndose dueño del lugar, no invitado.

---

### El protocolo de entrega: 5 pasos

**Paso 1: Accesos y cuentas**

Dale al cliente todo lo que necesita para operar por su cuenta:

```
Lista de accesos:
□ Cloudflare Workers / Trigger.dev: agrega al cliente como miembro del equipo
□ Google Sheets / Notion: compártelos con permiso de edición
□ Bot de Slack (o donde el sistema mande sus avisos): el cliente debe ser administrador o tener acceso a la configuración del bot
□ Claves de API: entrega instrucciones para renovarlas si vencen
□ Repositorio de GitHub: agrega al cliente como colaborador (si hace falta)
□ Acceso a la facturación: quién paga la API (acordado de antemano)
```

Cuando entregues claves y contraseñas, usa el acceso de equipo del propio servicio o un gestor de contraseñas, no un correo o un mensaje de chat común.

**Paso 2: Un video de recorrido en Loom (de hasta 5 minutos)**

Graba tu pantalla mientras muestras:
1. Cómo correr el flujo principal (cada paso)
2. Dónde ver los registros y las estadísticas (señala las celdas exactas en Sheets)
3. Cómo agregar un usuario nuevo o cambiar la configuración
4. Qué hacer si el sistema deja de responder (3 pasos para resolver problemas)
5. Cómo contactarte si necesitan ayuda

Súbelo a Loom y mándale el enlace al cliente. En el plan gratis de Loom un video puede durar hasta 5 minutos; si no te alcanza, graba dos cortos. La mayoría de la gente ve un video corto antes que leer instrucciones en PDF.

**Paso 3: Un documento SOP (1-2 páginas)**

Un SOP (Standard Operating Procedure, procedimiento estándar de operación) está escrito para que alguien sin conocimientos técnicos pueda manejar las cosas:

```markdown
# Cómo usar [Nombre del sistema]

## El día a día
1. El sistema funciona solo; no tienes que hacer nada
2. Cada [día/semana] te llega un aviso en Slack (o por correo) con una vista previa
3. Haz clic en "Enviar" para aprobarlo, o en "Editar" para hacer cambios

## Cómo cambiar la configuración
Si necesitas cambiar [ajuste], escríbeme por Slack o por correo: [contacto]
Normalmente toma 1-2 horas.

## ¿Y si algo falla?
1. Revisa [paso concreto]: la mayoría de los problemas empiezan aquí
2. Reinícialo con [botón/comando concreto]
3. Si no se arregla, escríbeme: [contacto] + una captura de pantalla del error

## Calendario de mantenimiento
- Cada 90 días: renovar las claves de API (te aviso con tiempo)
- Una vez al mes: revisar el registro de errores en [Sheets/Notion]
```

🎨 **Imagínalo así:** la demostración final es como arrancar el motor después de una reparación en el taller. Puedes decir "ya quedó" todas las veces que quieras. Hasta que gira la llave y el motor arranca, el cliente no lo cree. Arránquenlo juntos y verá que el carro camina.

**Paso 4: Una demostración final antes de cerrar**

Corre el sistema una vez junto con el cliente, para que vea todo el proceso con sus propios ojos. Responde sus preguntas. Asegúrate de que entiende las operaciones básicas.

**Paso 5: El cierre oficial del proyecto**

Un correo, o un mensaje en Slack o en tu portal de clientes:

```
[Nombre], ¡el proyecto está terminado!

Esto es lo que recibes:
✅ [Lista de funciones]
✅ Recorrido en Loom: [enlace]
✅ Documento SOP: [enlace]
✅ Acceso a [lista]

Tienes un mes de soporte incluido, así que si surge cualquier duda, escríbeme.
El segundo pago ($X): aquí está la factura [enlace].

¡Gracias por trabajar conmigo!
```

---

### Un mes de soporte: por qué es lo estándar

🎨 **Imagínalo así:** un mes de soporte es como el primer mes de alguien recién contratado. Ya hace el trabajo y ya cobra, pero Recursos Humanos le pregunta seguido cómo va durante ese primer mes. El cliente se acostumbra al sistema, hace preguntas y ve que es confiable. Después lo opera por su cuenta y confía en él.

Un mes de soporte incluido no es caridad. Es una inversión:

**Para el cliente:** baja el riesgo de "¿y si no puedo con esto?". Sabe que estás ahí.

**Para ti:**
- Ves cómo funciona el sistema en condiciones reales
- Recibes comentarios que mejoran tu plantilla
- Construyes confianza para el siguiente contrato
- Los clientes que recibieron buena ayuda el primer mes están más dispuestos a firmar un contrato de mantenimiento

**Cómo dar el soporte:**
- Un canal aparte solo para este cliente: un canal compartido de Slack (invita a todos los de su lado que lo necesiten), un portal de clientes o un hilo de correo dedicado
- Tiempo de respuesta: dentro de un día hábil para dudas no críticas
- Problemas críticos (el sistema está caído): 4 horas como máximo
- Al terminar el mes: ofrece un contrato de mantenimiento, o simplemente explica que el periodo de soporte terminó

---

### Venta adicional: "también podrías automatizar..."

Cada conversación con el cliente durante el soporte es una oportunidad para saber qué más le está causando problemas.

**Cómo hacer una venta adicional de forma natural:**

No "tengo un producto nuevo, cómpralo". Mejor, una observación más una pregunta:

```
Cliente durante la demostración: "Lástima que no pueda pasar esto a nuestro CRM automáticamente..."
Tú: "Técnicamente se puede. Una integración con tu CRM tomaría como una semana.
¿Quieres que te arme un presupuesto?"
```

**Oportunidades típicas de venta adicional:**
- Agregar una integración nueva (un CRM, un sistema de pagos, otra app de mensajería)
- Extenderlo a otro proceso del negocio
- Una versión para el celular (una app de Slack o alertas por mensaje de texto en lugar de solo un panel web)
- Un panel de análisis para la dirección
- Capacitación para el equipo

Lleva una lista de pendientes (backlog) por cliente: lo que mencionó como "estaría bien que...". Cada 2-3 meses, vuelve a ella: "¿Te acuerdas de que mencionaste X? Justo lo hice para otro cliente. ¿Quieres que te lo enseñe?"

---

### Un reporte mensual: haz visible el valor

🎨 **Imagínalo así:** un reporte mensual es como la pantalla de una caminadora. Ya estás corriendo y no te fijas en cuántas calorías quemaste. La pantalla te lo muestra y recuerdas por qué sigues. El cliente "corre" todos los días sin notar el ahorro. El reporte se lo recuerda.

El problema: el cliente se acostumbra a la automatización y olvida cuánto le ahorra. Tres meses después piensa: "Bueno, funciona. ¿Para qué pago soporte?".

La solución: un reporte mensual que muestre las cifras.

**Plantilla de reporte (sencilla, 1 página):**

```markdown
# Reporte de [Mes]: [Nombre del sistema]

## Qué hizo el sistema este mes
- Solicitudes atendidas: [X]
- Correos enviados: [X]
- Reportes generados: [X]

## Tu ahorro
- Horas ahorradas: [X horas] (a $[Y]/hora = $[Z])
- Errores evitados: [X] (errores manuales en X operaciones)

## Estado del sistema
- Tiempo en funcionamiento este mes: [99%+]
- Errores: [0 / descripción si hubo]
- Costo de API: $[X] (dentro del plan)

## El próximo mes
- [Cambios planeados, si los hay]
```

Armar este reporte toma 15 minutos (¡o automatízalo!). Le recuerda al cliente por qué paga el soporte. Pon en él solo cifras reales.

---

### NPS: una pregunta que te dice mucho

🎨 **Imagínalo así:** el NPS es como un termómetro. Un instrumento, una escala, y sabes de inmediato: fiebre (0-6), normal (7-8), de maravilla (9-10). No necesitas encuestas complicadas. Un número muestra cómo está el cliente y qué hacer después.

El NPS (Net Promoter Score, índice de recomendación) es la forma más sencilla de medir la satisfacción:

**Dos o tres semanas después del lanzamiento, pregunta:**

```
"[Nombre], el sistema ya lleva unas semanas funcionando.
En una escala del 0 al 10, ¿qué tan probable es que me recomiendes
con tus colegas o socios de negocio?"
```

- **9-10** → Promotor (un cliente contento: pídele una recomendación ahora mismo)
- **7-8** → Pasivo (neutral: averigua qué podría mejorar)
- **0-6** → Detractor (hay un problema: arréglalo de inmediato)

**Con los promotores (9-10), de inmediato:**

```
"¡Qué gusto! Por cierto, mencionaste que conoces a otros dueños de negocio
que tienen tareas parecidas. ¿Hay alguien a quien le pueda servir esto?
Con gusto platico con ellos."
```

---

### Conservar clientes con relaciones de largo plazo

El mejor cliente es el que paga cada mes, así no tienes que salir a buscar uno nuevo.

**Tres herramientas para conservar clientes:**

1. **Un reporte mensual**: hace visible el valor (ver arriba)

2. **Actualizaciones proactivas**: cuéntales tú de las nuevas opciones, no esperes a que pregunten:
   ```
   "Anthropic sacó una nueva versión de Claude y el sistema podría ir más rápido.
   ¿Quieres que lo actualice? Toma 30 minutos, sin interrupciones del servicio."
   ```

3. **Una revisión anual**: una vez al año, ofrece una auditoría del sistema:
   ```
   "Ya pasó un año desde el lanzamiento. Te propongo una auditoría:
   veríamos qué se puede optimizar y qué procesos nuevos
   vale la pena automatizar. La auditoría cuesta $[X] y te deja
   una lista de tareas para el año que viene."
   ```

---

## Práctica

**Ejercicio: Arma un paquete de entrega para tu proyecto**

Toma cualquier trabajo que hayas hecho con IA: para un cliente, para ti o para alguien que conoces. Si todavía no tienes uno, inventa un ejemplo de práctica, como "responder los correos de rutina de un consultorio dental", y arma el paquete para ese caso.

1. Escribe una lista de accesos: todo lo que el cliente debe recibir:
   ```
   □ [Servicio 1]: [cómo entregarlo]
   □ [Servicio 2]: [cómo entregarlo]
   ```

2. Graba un recorrido en Loom (de hasta 5 minutos):
   - Muestra el sistema funcionando
   - Explica cada paso con palabras sencillas

3. Escribe un documento SOP: 1 página para alguien sin conocimientos técnicos

4. Escribe una plantilla para tu correo final al cliente (el cierre del proyecto)

5. Escribe una plantilla de reporte mensual para este proyecto:
   - ¿Qué métricas va a incluir?
   - ¿Cómo las vas a reunir (automáticamente con Sheets, o a mano)?

**Meta:** un paquete de entrega completo, listo para usar. Cualquier cliente puede recibirlo al terminar su proyecto.

---

## Errores comunes

- **No dar seguimiento después de la entrega.** Entregas el proyecto y desapareces. Un mes después el cliente ya se olvidó de ti. Una llamada de "¿Cómo va el calentador?" a las 2-3 semanas mantiene viva la relación y te da una oportunidad de venta adicional.
- **No pedir recomendaciones.** Los clientes contentos muchas veces están dispuestos a recomendarte, si se lo pides. Muchos freelancers nunca lo hacen. El mejor momento es justo después de un NPS de 9-10.
- **Loom en lugar de instrucciones escritas, no además de ellas.** La gente ve videos y se salta los PDF. Pero algunos clientes quieren una guía escrita donde puedan buscar rápido. Haz LAS DOS cosas: Loom para aprender, el SOP para consultar.
- **No llevar una lista de oportunidades de venta adicional.** Cada "sería genial que..." de un cliente es un contrato futuro. Anótalo en una hoja de cálculo aparte y vuelve a ella cada 2-3 meses.
- **No automatizar el reporte mensual.** Un reporte para el cliente es el candidato perfecto para automatizar. Invierte 2 horas en configurar la recolección automática de métricas y te ahorras 15 minutos × 12 meses × N clientes.

---

## Lecciones relacionadas

- **→ [Portafolio y casos de estudio](41-portfolio-case-studies.md)**: ya la viste: cada proyecto entregado es un nuevo caso para tu portafolio, y cada testimonio es prueba social
- **→ [Empaquetado](42-packaging.md)**: ya la viste: los niveles de documentación (README / Loom / SOP) corresponden a los paquetes Básico, Pro y Empresarial
- **→ [El modelo de fábrica](48-factory-model.md)**: viene más adelante, en el módulo "Tu plan de 90 días": tu paquete de entrega se vuelve la plantilla para tus siguientes proyectos

---

## Herramientas y recursos

- **Loom**: [loom.com](https://www.loom.com/). Grabación de pantalla para recorridos; a octubre de 2026, el plan gratis está limitado a 5 minutos por video y 25 videos por persona. Revisa el sitio para ver las condiciones vigentes
- **Notion**: [notion.com](https://www.notion.com/templates). Práctico para documentos SOP (los puedes compartir con un enlace); una página compartida de Notion también puede funcionar como un portal de clientes sencillo
- **Google Sheets**: para reunir automáticamente las métricas del reporte mensual
- **Slack**: canales compartidos para dar soporte a clientes (muchas empresas ya lo usan a diario)
- **Tally**: [tally.so](https://tally.so/). Un formulario para reunir puntajes NPS y comentarios de clientes (tiene plan gratis)
- **Calendly**: [calendly.com](https://calendly.com/). Para agendar la revisión anual con el cliente
- **Stripe**: [stripe.com](https://stripe.com/). Para el cobro recurrente automático de un contrato de mantenimiento. No está disponible en todos los países (en América Latina, a octubre de 2026, solo en México y Brasil): la lista está en stripe.com/global

---

## Ideas clave

> El cliente compra la confianza de que el sistema funciona sin él. La entrega es como creas esa confianza. La documentación y el video importan más que un código bonito.

> Un mes de soporte incluido es una inversión. Ves el uso real, construyes confianza y obtienes datos para tu siguiente proyecto.

> Un reporte mensual hace visible el valor invisible. El cliente se acostumbra a la automatización y olvida por qué paga, así que recuérdaselo con cifras.

> NPS de 9-10 → pide una recomendación de inmediato. Los clientes contentos muchas veces la dan si se la pides. Mucha gente nunca la pide.

---

## Siguiente lección

→ [Cómo construir una marca personal con IA](67c-personal-brand-ai.md): la primera lección del módulo "Que te encuentren: contenido, anuncios y ventas"

Ya viste proyectos analizados con cifras en la lección [Casos de monetización](47-monetization-cases.md).
