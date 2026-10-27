# Bloque 06

## Resultado
- Qué añadí al proyecto: `mobile/src/api.ts` con la URL base y `getEvents`, y cambié `App.tsx` para que cargue los eventos del backend en vez del array local.
- Ruta o pantalla comprobada: la app con `npm run web` haciendo `GET http://localhost:3000/dev/events`, mirándolo en Network.
- Estado y respuesta observados: GET 200 y salen las dos tarjetas. Con el backend parado sale error de red, y al arrancarlo y recargar vuelven.

## Comprensión
- Recorrido del dato, explicado con mis palabras: al abrir la app, `useEffect` llama a `getEvents`, que hace el `fetch` al backend y comprueba que llega una lista válida. `App.tsx` la guarda en el estado y pinta las tarjetas; mientras carga pone `Cargando…` y si falla muestra el error.
- Cambio guiado y resultado: puse `/ruta-inexistente` en vez de `/events` y en Network salió un 404, o sea que el servidor respondía. Al restaurar `/events` volvió el 200. Con el backend parado, en cambio, la petición falla sin código porque no contesta nadie.
- Error encontrado y cómo lo resolví: tenía `App.tsx` dentro de `src/` y `types.ts` fuera, así que los imports fallaban. Los puse en su sitio, arreglé los imports y reinicié el TS Server.

## Evidencias
- Captura o transcripción breve, sin credenciales: Network con `GET /dev/events → 200`, `/dev/ruta-inexistente → 404` y la app con las dos tarjetas.
- Limitaciones del ejercicio: solo funciona con el navegador y el backend en el mismo PC, y los datos siguen siendo fijos.