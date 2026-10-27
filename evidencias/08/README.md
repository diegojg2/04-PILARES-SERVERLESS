# Bloque 08

## Resultado
- Qué añadí al proyecto: cambié `serverless.yml` para desplegar en AWS Academy con la región, el rol `LabRole` y mi código de alumno en el nombre del servicio. Los `.ts` no los toqué.
- Ruta o pantalla comprobada: servicio `festival-control-api-diegoj`, stage `dev`, región `us-east-1`, con endpoint `https://4w1rm2dvp0.execute-api.us-east-1.amazonaws.com/dev`.
- Estado y respuesta observados: el deploy creó las 7 Lambdas. `GET /events` → 200 con los dos eventos y en los logs sale `LIST eventos: GET`.

## Comprensión
- Recorrido del dato, explicado con mis palabras: compilo con `npm run build`, `serverless deploy` sube el código de `dist` y crea las Lambdas y el API Gateway. Ahora la petición va a AWS en vez de a mi PC, y el `console.log` sale en CloudWatch, que veo con `serverless logs`.
- Cambio guiado y resultado: con el endpoint real pedí `EVT-101` → 200 y `NO-EXISTE` → 404, y en los logs de `getEvent` aparecían los dos ids.
- Error encontrado y cómo lo resolví: al pedir la URL base pegué una de ejemplo y curl daba `Could not resolve host`. Lo arreglé con `export API_BASE=` y la URL real que salía en el deploy. También volví a lanzar npm desde la raíz y tuve que entrar en `backend/`.

## Evidencias
- Captura o transcripción breve, sin credenciales: salida del deploy con los endpoints, `curl` con 200 y 404, y los logs con `GET evento: EVT-101` y `GET evento: NO-EXISTE`.
- Limitaciones del ejercicio: depende del lab de Academy activo y sus credenciales caducan. Los datos siguen siendo fijos y las escrituras no se guardan.