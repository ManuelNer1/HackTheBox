# Métodos de solicitud

| Método | Descripción |
|--------|:------------|
|GET     | Solicita un recurso en especifico. Se pueden pasar datos adicionales al servicio a traves de cadenas de consulta en la URL (param=value) |
|POST    | Envia datos al servidor. Puede manejar multiples tipos de entrada, como texto, PDF y otras formas de datos binarios. El método POST se utiliza comúnmente al enviar información como forumularios/inicios de sesión o hasta cargar datos a un sitio web, como imágenes y documentos |
| HEAD   | Solicita los encabezados que se devolverian si se realizara una solicitud GET al servidor. No devuelve al cuerpo la solicitud y generalmente se realiza para verificar la longitud de la respuesta antes de descargar los recursos |
| PUT    | Crea neuvos recursos en el servidor. Permitir este metodo sin los controles adecuados puede provocar la carga de resursos maliciosos |
| DELETE | Elimina un recurso existente en el servidor web. Si no se protege adecuadamente, puede provocar una denegacion de servicio (DoS) al eliminar archivos criticos en el servidor web |
| OPTIONS | Devuelve informacion sobre el servidor, como los metodos aceptados por este |
| PATCH | Aplica modificaciones parciales al recurso en la ubicacion especificada |

# Codigos de respuesta

Estos codigos se utilizan para indicar al cliente el estado de su solicitud.

| Tipo  | Descripcion |
|-------|:------------|
| 1xx   | Proporciona informacion y no afecta la transmicion de la solicitud |
| 2xx   | Devuelto cuando la solicitud tiene exito|
| 3xx   | Devuelto cuandfo el servidor redirige el origen|
| 4xx   | Significa solicitudes inadecuadas. Por ejemplo, solicitar un recurso que no existe o solicitar un formato incorrecto |
| 5xx   | Devuelto cuando hay algun problema con HTTP server |