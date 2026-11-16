# social-nexus-site

Sitio web estático de **Social Nexus E.I.R.L.** — *¡Conectando realidades!*
Empresa peruana de soluciones integrales para la fase de exploración minera,
con enfoque en gestión social, seguridad y cuidado del medio ambiente.

## Estructura

```
site/                 # todo lo que se publica (HTML/CSS estático, sin build)
├── index.html        # Versión A · "Institucional moderna" (principal)
├── style.css
├── v2/               # Versión B · "Territorio y comunidad" (cálida, editorial)
├── v3/               # Versión C · "Operaciones en campo" (oscura, técnica)
├── assets/icons.svg  # sprite de iconos SVG compartido
└── assets/img/       # fotos y logo extraídos del brochure (webp)
.github/workflows/pages.yml   # despliegue a GitHub Pages
```

Las tres versiones comparten contenido (brochure) e imágenes; cada una tiene su
propio `style.css`. En el pie de cada página hay un selector **Diseño: A · B · C**
para compararlas. B y C llevan `noindex` mientras sean propuestas.

## Ver en local

```bash
python3 -m http.server 8000 --directory site
```

Abrir http://localhost:8000 (los iconos usan `<use href="assets/icons.svg#…">`,
que necesita servirse por HTTP, no con `file://`).

## Publicación (GitHub Pages)

1. En el repo: **Settings → Pages → Build and deployment → Source: GitHub Actions**.
2. Cada push a `main` que toque `site/` ejecuta `.github/workflows/pages.yml`,
   que sube `site/` como artefacto y lo despliega. También se puede lanzar a mano
   desde la pestaña *Actions* (`workflow_dispatch`).
3. URL resultante: `https://hneyra.github.io/social-nexus-site/`.

Para usar un dominio propio, añadir `site/CNAME` con el dominio y configurar el
DNS según la documentación de GitHub Pages; luego actualizar `sitemap.xml`,
`robots.txt` y las `og:image` a URLs absolutas.

## Contacto (del brochure)

- socialnexeirl@gmail.com · +51 943 250 843
- Av. Fátima #161, Urb. La Merced – Trujillo – La Libertad
