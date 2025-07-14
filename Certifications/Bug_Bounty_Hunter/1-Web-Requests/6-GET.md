
# 🌐 HTB Academy - Web Requests (Parte 6)

## 🟩 Método HTTP: GET

- Usado para solicitar recursos o información al servidor.
- Los datos se envían en la **URL** mediante **query strings** (`?param=valor`).
- NO debe usarse para enviar datos sensibles (visibles en la URL, historial, logs).
- Se considera un método **idempotente** y **seguro** (en teoría no cambia estado).

---

## 🔍 Ejemplo básico

```bash
curl "http://<IP>:<PORT>/search.php?search=admin"
```

- Aquí se hace una búsqueda con el parámetro `search=admin`.

---

## 🧠 Características

| Característica         | GET |
|------------------------|-----|
| Parámetros en URL      | ✅  |
| Visibles en navegador  | ✅  |
| Guardables en historial| ✅  |
| Límite de longitud     | ✅  |
| Afecta al servidor     | ❌  (en teoría) |
| Usado en formularios   | ✅  (búsqueda, filtros) |

---

## ✅ Flag (ejercicio parte 6)

```bash
curl "http://<IP>:<PORT>/search.php?search=flag"
# HTB{g3t_th3_d4t4}
```

---

## 📚 Referencias

- [MDN - GET](https://developer.mozilla.org/en-US/docs/Web/HTTP/Methods/GET)
- [HTB Academy - Web Requests](https://academy.hackthebox.com/module/35)
