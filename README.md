# Festival Control · Bloque 01

## Qué he construido
He hecho una función Serverless en TypeScript (`src/hello.ts`) que se ejecuta en local con serverless-offline. En `serverless.yml` la conecto a la ruta `GET /hello`, y Offline la sirve en `http://localhost:3000/dev/hello`. Devuelve un 200 con un JSON.

## Qué he comprendido
El handler usa `APIGatewayProxyEvent` para tipar la petición que llega y `APIGatewayProxyResult` para la respuesta (`statusCode` y `body`). Como es async, devuelve una `Promise` de ese tipo. Yo escribo el `.ts`, y `tsc` lo compila a `dist/hello.js`, que es lo que ejecuta Offline (`handler: dist/hello.handler`). El `EVENT RECIBIDO` del `console.log` no sale en la respuesta, sino en la terminal donde está corriendo Offline.

## Qué he modificado
He cambiado el `message` a "Festival Control · equipo preparado" y he añadido `service: "hello"` al JSON. La URL sigue siendo la misma porque la ruta está en `serverless.yml` y ese archivo no lo he tocado; solo cambié lo que devuelve la función.

## Cómo lo he comprobado
Con Thunder y con `curl -i` hice la misma petición a `/dev/hello` y en los dos casos me dio 200 y el mismo JSON. En la terminal de Offline aparecía un `EVENT RECIBIDO` nuevo con cada petición.