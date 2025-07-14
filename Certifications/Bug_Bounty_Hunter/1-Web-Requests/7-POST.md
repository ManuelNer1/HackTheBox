
# 🌐 HTB Academy - Web Requests (Parte 7)

## 🟧 Método HTTP: POST

- Se utiliza para enviar datos al servidor.
- Los datos no se colocan en la URL, sino en el **cuerpo (body)** de la solicitud.
- Es el método preferido para:
  - Formularios de inicio de sesión.
  - Registro de usuarios.
  - Subida de archivos.
  - Envío de datos sensibles.
- Puede usar distintos formatos (`Content-Type`):
  - `application/x-www-form-urlencoded`
  - `application/json`
  - `multipart/form-data`

---

## 🔐 Ejemplos con `curl`

### Formato clásico (`x-www-form-urlencoded`)
```bash
curl -X POST -d "username=admin&password=admin" http://<IP>:<PORT>/login
```

### Formato JSON
```bash
curl -X POST http://<IP>:<PORT>/login \
     -H "Content-Type: application/json" \
     -d '{"username":"admin","password":"admin"}'
```

> ⚠️ Algunos servidores solo aceptan cierto `Content-Type`.

---

## 🚫 Visibilidad de los datos

- A diferencia de `GET`, los parámetros **no son visibles en la URL**.
- POST es **más seguro para datos sensibles** (pero siempre debe usarse con HTTPS).

---

## ✅ Flag (ejercicio final)

```bash
curl -X POST -d "username=admin&password=admin" http://<IP>:<PORT>/login
# HTB{post_th3_d4t4}
```

---

## 📚 Referencias

- [MDN - POST](https://developer.mozilla.org/en-US/docs/Web/HTTP/Methods/POST)
- [HTB Academy - Module 35 (Parte 7)](https://academy.hackthebox.com/module/35)
