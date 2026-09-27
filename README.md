# Little Wins — blog autónomo (finanzas personales / productividad)

Sitio estático (HTML plano, sin build) publicado gratis en GitHub Pages. Un agente programado de Claude Code escribe y publica un artículo nuevo automáticamente, sin usar ninguna API de pago.

## Cómo funciona
- `topics.json` guarda el nicho y la lista de temas pendientes/usados.
- `AGENT_INSTRUCTIONS.md` es lo que sigue la sesión programada en cada ejecución.
- Cada ejecución agrega un post en `posts/`, actualiza `index.html` y `sitemap.xml`, y hace `git push`.

## Lo que falta por hacer tú (no puedo crear cuentas por ti)
1. **Activar GitHub Pages**: en el repo, ve a *Settings → Pages → Source: Deploy from a branch → main / (root)*. En unos minutos el sitio queda visible en `https://yunkwani.github.io/pagina1/`.
2. **Monetización con anuncios (opcional, cuando tengas tráfico)**: crea una cuenta gratuita en [Google AdSense](https://adsense.google.com), pide que aprueben el sitio, y agrega tu script de anuncios en `assets/` o directamente en el `<head>` de cada página.
3. **Monetización con afiliados (opcional)**: únete a un programa de afiliados relacionado con finanzas/productividad (ej. Amazon Afiliados) y reemplaza las menciones genéricas de producto en los artículos por tus enlaces reales.

## Costo
$0. Sin API keys, sin hosting de pago, sin dominio (usa el subdominio gratuito de GitHub Pages).
