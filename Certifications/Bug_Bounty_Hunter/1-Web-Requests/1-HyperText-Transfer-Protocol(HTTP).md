
# 🕸️ HTB Academy - Web Requests (Bug Bounty Path)

## 🌐 ¿Qué es HTTP?

- Protocolo de nivel de aplicación utilizado para acceder a recursos web.
- Comunicación entre **cliente y servidor**: el cliente solicita y el servidor responde.
- Puerto por defecto: `80` (`443` para HTTPS).
- Se usa un **FQDN** como `www.hackthebox.com`, que se resuelve mediante **DNS**.

---

## 🧩 Partes de una URL

**Ejemplo completo:**

```
http://admin:password@inlanefreight.com:80/dashboard.php?login=true#status
```

| Componente       | Descripción                                                                 |
|------------------|-----------------------------------------------------------------------------|
| `http://`        | Esquema o protocolo (`https://` para cifrado)                               |
| `admin:password@`| (Opcional) Autenticación: usuario y contraseña                              |
| `inlanefreight.com` | Host o dominio (también puede ser una IP)                             |
| `:80`            | Puerto (por defecto 80 en HTTP, 443 en HTTPS)                               |
| `/dashboard.php` | Ruta o recurso en el servidor                                               |
| `?login=true`    | Query string (parámetros en formato clave=valor)                            |
| `#status`        | Fragmento (solo interpretado por el navegador, no enviado al servidor)      |

> ✅ **Obligatorios:** `esquema` y `host`.

---

## ⚙️ HTTP Flow (Flujo de solicitud HTTP)

1. El navegador busca el dominio en `/etc/hosts`. Si no lo encuentra, consulta un servidor DNS.
2. DNS responde con una dirección IP.
3. El navegador envía un `GET /` al servidor.
4. El servidor responde con `index.html` y un código (ej. `200 OK`).
5. El navegador renderiza el contenido.

> 💡 Puedes usar `/etc/hosts` para resolver dominios de forma local.

---

## 🧪 Uso de `cURL`

**¿Qué es?**  
Herramienta CLI para enviar peticiones HTTP (y otros protocolos). Muy útil para scripting y pruebas rápidas.

### Comandos básicos:

```bash
curl inlanefreight.com
curl -O inlanefreight.com/index.html   # Guarda con el nombre original
curl -o salida.html URL                # Guarda con nombre definido
curl -s -O URL                         # Modo silencioso
curl -h                                # Ayuda
```

### Flags comunes:

| Flag | Uso                                                  |
|------|------------------------------------------------------|
| `-i` | Muestra headers de respuesta                         |
| `-v` | Verbose (ver detalles de la solicitud/respuesta)     |
| `-A` | Define un `User-Agent` personalizado                 |
| `-u user:pass` | Autenticación básica HTTP                  |
| `-H` | Agrega headers personalizados                        |
| `-X POST -d` | Enviar datos en un POST                      |
| `-b` | Enviar cookies                                        |
| `-k` | Ignorar validación SSL (útil en entornos de prueba)  |

> 📘 Usa `man curl` o `curl --help all` para más detalles.

---

## 🧠 Tip útil:

Si usas DevTools del navegador:

| Comando                  | Acción                          |
|--------------------------|----------------------------------|
| `Ctrl+Shift+I` / `F12`   | Abre herramientas de desarrollo |
| `Ctrl+Shift+E`           | Abre pestaña de red (Network)   |
| `Ctrl+Shift+K`           | Abre consola (Console)          |

---

## 🏁 Flag del ejercicio (ejemplo):

```bash
curl -O http://<IP>:<PORT>/download.php
cat download.php
# Flag: HTB{64$!c_cURL_u$3r}
```

---

## 📌 Cheatsheet rápido (cURL)

```bash
curl -s -O http://example.com/index.html        # Descargar silenciosamente
curl -I http://example.com                      # Solo headers (HEAD)
curl http://example.com -v                      # Verbose
curl -u admin:admin http://IP:PORT/             # Autenticación básica
curl -X POST -d 'a=1&b=2' http://IP:PORT/login  # Enviar datos POST
curl -b 'PHPSESSID=xxxx' http://IP:PORT/        # Enviar cookies
```

---

## 📚 Referencia

- [RFC HTTP](https://tools.ietf.org/html/rfc2616)
- [HTB Academy - Module 35](https://academy.hackthebox.com/module/35)
