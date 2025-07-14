
# 🌐 HTB Academy - Web Requests (Parte 4)

## 🧠 HTTP Request Body

Cuando usamos métodos como `POST`, `PUT`, etc., podemos enviar un **body** con datos útiles (formulario, JSON, etc.).

### Tipos de Content-Type:

| Content-Type                      | Uso común                          |
|----------------------------------|-------------------------------------|
| `application/x-www-form-urlencoded` | Formatos de formulario clásicos |
| `application/json`              | APIs modernas                       |
| `multipart/form-data`           | Formularios con archivos (uploads)  |

---

## 🧾 Ejemplo con `curl` (envío de datos POST)

```bash
curl -X POST -d "username=admin&password=admin" http://<IP>:<PORT>/login
```

- Por defecto se usa `application/x-www-form-urlencoded`

---

## 🧾 Headers relevantes para POST

| Header           | Descripción                                    |
|------------------|------------------------------------------------|
| `Content-Type`   | Define el formato del body                     |
| `Content-Length` | Tamaño en bytes del body enviado               |

---

## 📤 Body JSON con `curl`

```bash
curl -X POST http://<IP>:<PORT>/login \
     -H "Content-Type: application/json" \
     -d '{"username":"admin", "password":"admin"}'
```

---

## ✅ Flag (ejercicio final)

```bash
curl -X POST http://<IP>:<PORT>/login -d "username=admin&password=admin"
# Flag: HTB{p0st_th3_d4t4}
```

---

## 📚 Referencia

- [MDN - HTTP Request Body](https://developer.mozilla.org/en-US/docs/Web/HTTP/Methods/POST)
- [HTB Academy - Web Requests](https://academy.hackthebox.com/module/35)
