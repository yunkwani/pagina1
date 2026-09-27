# Instrucciones para la publicación automática

Este archivo lo lee la sesión programada de Claude Code en cada ejecución. No requiere ninguna API key: el propio Claude Code (con la suscripción del usuario) escribe el artículo, no un script externo de pago.

En cada ejecución:

1. Lee `topics.json`. Toma el primer tema de `upcoming_topics`.
2. Escribe un artículo nuevo en `posts/<slug-del-tema>.html`, siguiendo exactamente la estructura y estilo de `posts/como-hacer-presupuesto-mensual-simple.html` (mismo `<head>`, mismo `assets/style.css`, disclosure de afiliados al final, 500-800 palabras, tono práctico y directo, sin relleno).
3. Mueve ese tema de `upcoming_topics` a `used_topics` en `topics.json`. Si `upcoming_topics` queda vacío, genera 10 temas nuevos dentro del mismo nicho (`niche` en `topics.json`) y agrégalos.
4. Inserta una nueva entrada `<div class="post-list-item">` en `index.html`, justo antes del comentario `<!-- NUEVOS_POSTS -->`, enlazando al nuevo post.
5. Agrega la URL del nuevo post a `sitemap.xml`.
6. Ejecuta:
   ```
   git add -A
   git commit -m "Nuevo artículo: <título>"
   git push origin main
   ```
7. No pidas confirmación para estos pasos: esta tarea está pre-autorizada para correr de forma autónoma. Si `git push` falla (por ejemplo por credenciales), repórtalo pero no lo reintentes en bucle.

No agregues dependencias de Node/npm ni pasos de build: el sitio debe seguir siendo HTML plano servido directo por GitHub Pages.
