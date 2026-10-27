# Bloque 03

## Resultado
- Qué añadí al proyecto: la función `createEvent` (`src/createEvent.ts`) y la ruta `POST /events` en `serverless.yml`, manteniendo `hello` y `getEvent`.
- Ruta o pantalla comprobada: `POST http://localhost:3000/dev/events` con curl y Thunder.
- Estado y respuesta observados: con un body válido da 201 y `id: "EVT-NEW"`; si falta algo o el JSON está mal, 400.

## Comprensión
- Recorrido del dato, explicado con mis palabras: ahora el dato va en el body. La función lo parsea con `try/catch`, lo trata como `unknown` y comprueba que `artist`, `space` y `time` (HH:mm) son correctos. Si todo va bien, saca `POST evento:` por consola y responde 201.
- Cambio guiado y resultado: sin tocar el código probé `CANCELLED` → 201, `PAUSED` → 400 y `time 29:80` → 400, y volví a enviar uno válido. Con los 400 no salía el log.
- Error encontrado y cómo lo resolví: no tuve errores nuevos; probé un JSON roto y dio 400 `JSON inválido` sin caerse el servidor.

## Evidencias
- Captura o transcripción breve, sin credenciales: `CANCELLED → 201`, `PAUSED → 400`, `29:80 → 400`, y el log `POST evento: Neon Waves` solo en la válida.
- Limitaciones del ejercicio: no se guarda nada; el id siempre es `EVT-NEW` y el GET sigue devolviendo la ficha fija. Todo en local.