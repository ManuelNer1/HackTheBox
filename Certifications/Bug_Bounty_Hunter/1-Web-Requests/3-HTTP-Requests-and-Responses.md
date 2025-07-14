
# 🌐 HTB Academy - Web Requests (Parte 3)

## 🧠 HTTP Response

Una **respuesta HTTP** tiene tres partes:

1. **Línea de estado**
2. **Headers**
3. **Body (opcional)**

### Ejemplo:
```
HTTP/1.1 200 OK
Content-Type: text/html
Content-Length: 349

<html>...</html>
```

---

## ✅ Códigos de estado HTTP

| Código | Categoría      | Significado general             |
|--------|----------------|---------------------------------|
| 1xx    | Informativo    | Procesando                      |
| 2xx    | Éxito          | Petición correcta               |
| 3xx    | Redirección    | Requiere otra acción            |
| 4xx    | Error cliente  | Petición incorrecta del cliente |
| 5xx    | Error servidor | Falla del servidor              |

### Códigos comunes:

| Código | Significado               |
|--------|---------------------------|
| 200    | OK                        |
| 301    | Redirección permanente    |
| 302    | Redirección temporal      |
| 401    | No autorizado             |
| 403    | Prohibido (Forbidden)     |
| 404    | No encontrado             |
| 500    | Error interno del servidor|

---

## 🧾 Headers de respuesta comunes

| Header            | Función                                             |
|-------------------|-----------------------------------------------------|
| `Server`          | Software del servidor web                           |
| `Content-Type`    | Tipo MIME del contenido (`text/html`, `application/json`, etc.) |
| `Content-Length`  | Tamaño en bytes del body                            |
| `Set-Cookie`      | Define cookies que el cliente debe guardar          |
| `Location`        | Usado en redirecciones (`3xx`)                      |

---

## 🔀 Redirecciones

Cuando un servidor responde con `301` o `302`, indica al cliente que debe ir a otra URL. Esto se comunica con el header `Location`.

### Ejemplo:
```
HTTP/1.1 302 Found
Location: http://newsite.com
```

### Con `curl`:

Por defecto **no sigue redirecciones**. Usa `-L` para seguirlas.

```bash
curl -L http://example.com
```

---

## ✅ Flag (ejercicio final del módulo)

```bash
curl -L http://<IP>:<PORT>/flag
# Flag: HTB{f0ll0w_th3_r3d1r3ct}
```

---

## 📚 Referencia

- [RFC HTTP Status Codes](https://www.rfc-editor.org/rfc/rfc9110.html#name-status-codes)
- [HTB Academy - Web Requests](https://academy.hackthebox.com/module/35)
