# Bloque 02

## Resultado
- Qué añadí al proyecto: la función `getEvent` (`src/getEvent.ts`) y la ruta `GET /events/{id}` en `serverless.yml`, manteniendo `hello`.
- Ruta o pantalla comprobada: `http://localhost:3000/dev/events/EVT-104`, `EVT-205` y `EVT-330`, con curl y Thunder.
- Estado y respuesta observados: 200 y un JSON con el id que puse en la URL y los mismos datos de ejemplo.

## Comprensión
- Recorrido del dato, explicado con mis palabras: el `{id}` del YAML hace que el final de la URL sea variable. Offline lo mete en `event.pathParameters.id`, la función lo lee con `?.` (puede venir vacío y entonces da 400), lo saca por consola y lo devuelve en el JSON.
- Cambio guiado y resultado: pedí `EVT-330` sin tocar el código, predije que el id sería ese y acerté. En la terminal salió `GET evento: EVT-330`.
- Error encontrado y cómo lo resolví: `npm run typecheck` me daba `ENOENT` porque estaba en la raíz y el `package.json` está en `backend/`. Lo arreglé con `cd backend`.

## Evidencias
- Captura o transcripción breve, sin credenciales: `curl -i .../dev/events/EVT-330` → `200 OK` con `{"id":"EVT-330", ...}` y en el log `GET evento: EVT-330`.
- Limitaciones del ejercicio: los datos son inventados y cualquier id devuelve 200; no hay base de datos y todo es en local.