# Bloque 07

## Resultado
- Qué añadí al proyecto: en `api.ts` las funciones `createEvent`, `replaceEvent`, `updateEvent` y `deleteEvent`, y en `App.tsx` cuatro botones que las usan y muestran la respuesta.
- Ruta o pantalla comprobada: la app con `npm run web`, pulsando POST, PUT, PATCH y DELETE y mirándolo en Network.
- Estado y respuesta observados: POST → 201 con `EVT-NEW`, PUT → 200 `REPLACED`, PATCH → 200 `UPDATED` y DELETE → 200 `DELETED`. El resultado sale debajo de los botones y la lista sigue con dos eventos.

## Comprensión
- Recorrido del dato, explicado con mis palabras: cada botón llama a `run` con una función de `api.ts`, que hace el `fetch` con su método, ruta y body en JSON. Mientras espera pone `Enviando…`, y luego muestra la respuesta del servidor o el error. La lista no se cambia a mano porque el backend no guarda nada.
- Cambio guiado y resultado: en el PATCH cambié `CANCELLED` por `CONFIRMED`. En Network el payload era `{"status":"CONFIRMED"}`, dio 200 y la respuesta traía `changes.status: CONFIRMED`. Después lo dejé otra vez en `CANCELLED`.
- Error encontrado y cómo lo resolví: no tuve errores nuevos; me aseguré de tener el backend arrancado antes de pulsar los botones.

## Evidencias
- Captura o transcripción breve, sin credenciales: Network con `PATCH /dev/events/EVT-101 → 200` y la app mostrando el resultado con `changes.status`.
- Limitaciones del ejercicio: las escrituras no se guardan, así que las tarjetas no cambian. Todo es en local.