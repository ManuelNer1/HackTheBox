
# 🌐 HTB Academy - Web Requests

## 🧠 Cookies

Las **cookies** son pares `clave=valor` que el servidor envía al cliente mediante el header `Set-Cookie`. El navegador las guarda y las reenvía automáticamente en futuras peticiones al mismo dominio.

### Header de respuesta:
```
Set-Cookie: token=admin; Path=/; Domain=inlanefreight.com
```

### En futuras peticiones:
```
Cookie: token=admin
```

> 🛡️ Muy usado para manejar sesiones de usuario.

---

## 🔐 Autenticación Básica

HTTP permite usar **Autenticación Básica** (`Basic Auth`) enviando usuario y contraseña codificados en Base64.

### Header:
```
Authorization: Basic YWRtaW46cGFzc3dvcmQ=
```

- `admin:password` codificado en Base64 → `YWRtaW46cGFzc3dvcmQ=`

### Usando `curl`:
```bash
curl -u admin:password http://inlanefreight.com
```

> ⚠️ No seguro si no se usa con HTTPS (envía credenciales en texto claro).

---

## 📤 Métodos HTTP

| Método | Descripción |
|--------|-------------|
| `GET`  | Solicita datos (query string) |
| `POST` | Envía datos (formulario, JSON, etc.) |
| `PUT`  | Crea o reemplaza un recurso |
| `DELETE` | Elimina un recurso |
| `HEAD` | Igual que `GET` pero solo devuelve headers |
| `OPTIONS` | Lista los métodos permitidos por el servidor |

### `POST` con `curl`:
```bash
curl -X POST -d "username=admin&password=password" http://URL/login
```

---

## 🧾 Headers comunes

| Header         | Función                                 |
|----------------|------------------------------------------|
| `Host`         | Especifica el dominio                    |
| `User-Agent`   | Identifica al cliente                    |
| `Referer`      | De dónde proviene la solicitud           |
| `Cookie`       | Envía cookies al servidor                |
| `Authorization`| Enviar credenciales                      |
| `Content-Type` | Tipo de datos enviados (`application/json`, `x-www-form-urlencoded`, etc.) |

### Usar headers personalizados con `curl`:
```bash
curl -H "User-Agent: 4li3n" http://inlanefreight.com
```

---

## 📌 Tip: Capturar tráfico HTTP

- Puedes usar **Burp Suite**, **Wireshark** o extensiones del navegador (DevTools).
- Si usas un proxy (como Burp), puedes ver todo lo que se envía y se recibe.

---

## ✅ Flag del módulo (ejemplo final)

```bash
curl -u admin:admin http://<IP>:<PORT>/flag
# Flag: HTB{w3b_r3qu3sts_m4st3r}
```

---

## 📚 Referencia

- [RFC HTTP Authentication](https://datatracker.ietf.org/doc/html/rfc7617)
- [HTB Academy - Module 35 (Parte 2)](https://academy.hackthebox.com/module/35)
