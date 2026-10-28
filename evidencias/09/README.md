# Bloque 09

## Resultado
- Qué añadí al proyecto: solo cambié `API_URL` en `mobile/src/api.ts` para que apunte a AWS; lo demás sigue como en el 07.
- Ruta o pantalla comprobada: la app con `npm run web` contra `https://4w1rm2dvp0.execute-api.us-east-1.amazonaws.com/dev`, con Offline apagado.
- Estado y respuesta observados: GET → 200 con las dos tarjetas, POST → 201 y PUT, PATCH y DELETE → 200.

## Comprensión
- Recorrido del dato, explicado con mis palabras: la app hace el `fetch` por HTTPS al API Gateway, que llama a la Lambda de cada método, y el log queda en CloudWatch. Sé que es AWS porque no tenía el backend local encendido.
- Cambio guiado y resultado: antes usaba `http://localhost:3000/dev` con Offline y ahora el endpoint de AWS. Para volver a local solo cambiaría `API_URL` y arrancaría `npm start` en `backend/`. Lo he dejado en AWS.
- Error encontrado y cómo lo resolví: lancé `serverless logs` desde `mobile/` y sin las variables. Lo arreglé entrando en `backend/` y volviendo a hacer los `export`.

## Evidencias
- Captura o transcripción breve, sin credenciales: Network con GET y PATCH → 200 en la URL de AWS, y logs con `LIST eventos: GET` y `PATCH evento: EVT-101`.
- Limitaciones del ejercicio: los datos son fijos, no se guarda nada y depende del lab de Academy.