# Bloque 04

## Resultado
- Qué añadí al proyecto: la carpeta `src/events/` con un modelo común y una función por operación (list, get, create, replace, update y delete), con sus rutas en `serverless.yml`.
- Ruta o pantalla comprobada: GET, POST, PUT, PATCH, DELETE y OPTIONS en `/dev/events` y `/dev/events/{id}`, con curl y Thunder.
- Estado y respuesta observados: lista → 200 con 2 eventos, `EVT-101` → 200, `NO-EXISTE` → 404, POST → 201, PUT/PATCH/DELETE → 200 y escrituras inválidas → 400.

## Comprensión
- Recorrido del dato, explicado con mis palabras: cada método va a su propio handler. Hay un catálogo fijo con `EVT-101` y `EVT-102`; si el id no está, da 404. Las escrituras validan el body y responden, pero no cambian nada.
- Cambio guiado y resultado: mandé `{"status":"CANCELLED"}` a `EVT-101` con PUT y dio 400, porque PUT sustituye todo y pide todos los campos. Con PATCH dio 200 `UPDATED` porque es un cambio parcial. Después el GET seguía en `CONFIRMED` porque no se guarda.
- Error encontrado y cómo lo resolví: pegué el PATCH y el DELETE juntos y las respuestas salieron pegadas; los repetí por separado y los dos dieron 200.

## Evidencias
- Captura o transcripción breve, sin credenciales: `PUT {"status":"CANCELLED"}` → 400, `PATCH {"status":"CANCELLED"}` → 200 `UPDATED`, `GET EVT-101` → 200 `CONFIRMED`, `OPTIONS /events` → 200 permitiendo POST.
- Limitaciones del ejercicio: los eventos son fijos y no hay base de datos, así que ninguna escritura se guarda. Todo en local.