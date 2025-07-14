
# 🌐 HTB Academy - Web Requests (Parte 5)

## 📥 Métodos HTTP

| Método   | Descripción |
|----------|-------------|
| `GET`    | Solicita un recurso. Parámetros se pueden enviar en la URL. |
| `POST`   | Envía datos al servidor. Utilizado para formularios, archivos, etc. El contenido va en el body. |
| `HEAD`   | Igual que `GET` pero sin el cuerpo de la respuesta. Se usa para verificar metadatos antes de descargar. |
| `PUT`    | Crea recursos en el servidor. Puede usarse para cargar archivos o datos. |
| `DELETE` | Elimina un recurso. Puede ser peligroso si no se controla. |
| `OPTIONS`| Devuelve información sobre los métodos permitidos por el servidor. |
| `PATCH`  | Modifica parcialmente un recurso. |

> 📌 En aplicaciones modernas con APIs REST es común ver `PUT`, `DELETE` y `PATCH`.

---

## 📤 Códigos de Respuesta HTTP

| Categoría | Código | Descripción |
|-----------|--------|-------------|
| 1xx       |        | Información (no afecta el procesamiento) |
| 2xx       | 200 OK | Éxito en la solicitud. |
| 3xx       | 302    | Redirección temporal. |
| 4xx       | 400    | Petición mal formada. |
|           | 403    | Prohibido: sin acceso o intento malicioso. |
|           | 404    | No encontrado. |
| 5xx       | 500    | Error interno del servidor. |

> 🔐 Los códigos ayudan a entender si una solicitud fue exitosa, fallida, o requiere redirección/autenticación.

---

## 📚 Referencias

- [MDN - HTTP Methods](https://developer.mozilla.org/en-US/docs/Web/HTTP/Methods)
- [MDN - HTTP Status Codes](https://developer.mozilla.org/en-US/docs/Web/HTTP/Status)
- [HTB Academy - Module 35 (Parte 5)](https://academy.hackthebox.com/module/35)
