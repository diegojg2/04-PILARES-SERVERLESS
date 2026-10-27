# Bloque 05

## Resultado
- Qué añadí al proyecto: la carpeta `mobile/` con una app Expo en React Native (`App.tsx`, `types.ts`, `package.json`, `app.json` y `tsconfig.json`).
- Ruta o pantalla comprobada: `npm run web`, que abre Festival Control en el navegador.
- Estado y respuesta observados: salen las dos tarjetas; al pulsar el botón pone `Selección: EVT-101` y al recargar vuelve a `ninguna`.

## Comprensión
- Recorrido del dato, explicado con mis palabras: los eventos están en un array local y se pintan con `map`. El botón cambia el estado con `useState` y React actualiza el texto. Como el estado está en memoria, se pierde al recargar. Todavía no hay HTTP.
- Cambio guiado y resultado: cambié el botón a `EVT-102` y salió `Selección: EVT-102`; después lo dejé otra vez en `EVT-101`.
- Error encontrado y cómo lo resolví: `npm install` fallaba por la caché de npm de `C:` y lo arreglé con `npm install --cache /d/DJ/npm-cache`.

## Evidencias
- Captura o transcripción breve, sin credenciales: pantalla con las dos tarjetas y `Selección: EVT-102`.
- Limitaciones del ejercicio: los datos son locales, la selección no se guarda y la app todavía no usa el backend.