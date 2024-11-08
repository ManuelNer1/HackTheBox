# Cross-Site Scripting (XSS)

Cross-Site Scripting es una de las vulnerabilidades mas comunes en aplicaciones web, dicha vulnerabilidad consta de aprovechar una falla en la desinfeccion de la entrada(input) del usuario para **"escribir"** codigo JavaScript en la pagina y ejecutarlo en el lado del cliente, generando varios tipos de ataques.

- El ataque se ejecuta en el navegador

## Tipos de XSS

- **Stored (Persistent) XSS :** El tipo de XSS mas critico, que ocurre cuando la entrada del usuario se almacena en la base de datops de back-end y luego se muestra al recuperarla
    - Publicaciones o comentarios 

- **Reflected (Non-Persistent) XSS :** Ocurre cuando la entrada del usuario se muestra en la pagina despues de ser procesada por el servidor backend, pero sin ser almacenada
    - resultados de busqueda o mensaje de error 

- **DOM-based XSS :** Otro tipo de XSS no persiste que ocurre cuando la entrada del usuario se muestra directamente en el navegador y se procesa completamente en el lado del cliente, sin llegar al servidor back-end
    - A traves de parametros HTTP del lado del cliente o etiquetas de anclaje