# social-nexus-site

Sitio web estático de **Social Nexus E.I.R.L.** — *¡Conectando realidades!*
Empresa peruana de soluciones integrales para la fase de exploración minera,
con enfoque en gestión social, seguridad y cuidado del medio ambiente.

## Estructura

```
site/                 # todo lo que se publica (HTML/CSS estático, sin build)
├── index.html        # Propuesta A · "Corporativa industrial" (publicada en la raíz)
├── style.css         # sistema de diseño de A (tokens en :root) + estilos
├── v2/               # Propuesta B · "Territorio y comunidad" (editorial, noindex)
├── v3/               # Propuesta C · "Operaciones en campo" (oscura y técnica, noindex)
├── comparar/         # página interna para comparar A, B y C (noindex)
├── v1/               # versión inicial de A, solo como referencia (noindex)
├── assets/fonts/     # fuentes auto-alojadas (woff2, latin, OFL): Archivo, Public Sans,
│                     #   Newsreader (B), IBM Plex Sans y Plex Mono (C)
├── assets/icons.svg  # sprite de iconos SVG compartido
└── assets/img/       # fotos (webp, con variantes -960 para srcset), logo, imagen OG
.github/workflows/pages.yml   # despliegue a GitHub Pages
```

### Sistema de diseño (resumen)

- **Tipografía**: Archivo (titulares, etiquetas, botones) + Public Sans (texto).
- **Color**: navy `#112038` / azul institucional `#36538A` como base; papel `#F7F5F0`
  y grafito para superficies y texto; dorado `#E8A814` solo para la acción principal
  y marcadores; verde `#3A7F2A` para sostenibilidad y comunidad. Los colores del
  logo aparecen solo como firma (línea segmentada del footer y el hero).
- **Componentes**: `.label`, `.btn` (`-primary`, `-accent`, `-ghost`, `-ghost-light`),
  `.link-arrow`, `.service` (`--feature`, `--compact`), `.field` con estados de validación.
- **Breakpoints**: 600 · 700 · 768 · 960/1024 · 1080 (navegación de escritorio) · 1440.

Para comparar las tres propuestas abrir `/comparar/` (p. ej.
`https://hneyra.github.io/social-nexus-site/comparar/`). B y C enlazan a esa página
desde su pie; A (producción) no muestra ningún selector de versiones.

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
