
# 🌐 HTB Academy - Web Requests (Parte 8)

## 🧱 CRUD en APIs

Las APIs modernas utilizan los métodos HTTP para representar acciones sobre recursos. Es el modelo **CRUD**:

| Acción | Método HTTP | Ejemplo                       |
|--------|-------------|-------------------------------|
| Create | `POST`      | Crear nuevo recurso           |
| Read   | `GET`       | Leer uno o más recursos       |
| Update | `PUT` / `PATCH` | Modificar un recurso      |
| Delete | `DELETE`    | Eliminar un recurso           |

---

## 🧠 Ejemplos con `curl`

### Crear (POST)
```bash
curl -X POST http://<IP>:<PORT>/api.php/city/ \
  -d '{"city_name":"HTB_City","country_name":"HTB"}' \
  -H "Content-Type: application/json"
```

### Leer (GET)
```bash
curl http://<IP>:<PORT>/api.php/city/london
curl -s http://<IP>:<PORT>/api.php/city/ | jq
```

### Modificar (PUT)
```bash
curl -X PUT http://<IP>:<PORT>/api.php/city/london \
  -d '{"city_name":"New_HTB_City","country_name":"HTB"}' \
  -H "Content-Type: application/json"
```

### Eliminar (DELETE)
```bash
curl -X DELETE http://<IP>:<PORT>/api.php/city/New_HTB_City
```

---

## 📌 Tips

- Asegúrate de que el servidor acepte el método HTTP usado.
- Muchas APIs modernas siguen este modelo para endpoints `/resource` o `/api/resource`.

---

## ✅ Flag (ejercicio final)

```bash
curl -X DELETE http://<IP>:<PORT>/api.php/city/New_HTB_City
# HTB{r3st_1s_c00l}
```

---

## 📚 Referencias

- [MDN - HTTP Methods](https://developer.mozilla.org/en-US/docs/Web/HTTP/Methods)
- [HTB Academy - Web Requests](https://academy.hackthebox.com/module/35)
