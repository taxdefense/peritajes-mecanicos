# Peritajes mecánicos forenses · Claudio Durán Alvial

Sitio estático del Dr. Claudio Durán Alvial, ingeniero civil mecánico y perito judicial nombrado por la Excma. Corte Suprema de Chile (Mecánica Automotriz, Maquinaria Industrial e Investigación de Accidentes de Tránsito, jurisdicción nacional).

- Dominio definitivo: **https://perito-mecanico.cl** (Vercel)
- Copia de trabajo: https://taxdefense.github.io/peritajes-mecanicos/ (GitHub Pages)

HTML, CSS y JS puros, sin dependencias ni paso de compilación. Los enlaces internos son relativos y terminan en `.html`, así que el mismo código funciona en GitHub Pages (subcarpeta) y en Vercel (raíz).

## Estructura

| Archivo / carpeta | Contenido |
|---|---|
| `index.html` | Portada de una página: hero con video, credenciales, servicios, la diferencia forense, cómo trabajamos, el perito, innovación (carrusel de videos), blog, contacto (formulario que abre WhatsApp) y pie. CSS y JS embebidos. |
| `blog/*.html` | 7 artículos. Comparten la misma plantilla de CSS embebido: si cambias el estilo de uno, aplica el mismo cambio a los 7. |
| `assets/` | Video y póster del hero, fotos de servicios, del perito y del blog, videos de innovación. |
| `assets/og/` | Imágenes para redes sociales (1200×630): `portada.jpg` y una por artículo, con el mismo nombre que su archivo. |
| `assets/favicon.svg`, `favicon-32.png`, `apple-touch-icon.png`, `/favicon.ico` | Íconos a partir del monograma "CD". |
| `404.html` | Página de error con la marca. Funciona en ambos hostings. |
| `robots.txt`, `sitemap.xml` | Apuntan a `https://perito-mecanico.cl/`. |
| `vercel.json` | `cleanUrls: false`, `trailingSlash: false`, cabeceras de seguridad (HSTS, X-Frame-Options, etc.) y caché larga e inmutable para `/assets/`. |

### Datos que se usan en el sitio (verificados)

Dr. Claudio Durán Alvial · Ingeniero Civil Mecánico · Doctor (PhD) por la Universitat de Lleida · perito judicial Corte Suprema, bienios sucesivos 2018–2026 · jurisdicción nacional · 35 años liderando Automotriz Durán (1975–2010) · docente de Ingeniería Mecánica UBB · WhatsApp +56 9 8743 8047 · peritojudicialmecanico@gmail.com.

No agregues cifras de casos, testimonios ni dirección física sin que Claudio los confirme.

## Publicar en Vercel

1. En vercel.com: **Add New → Project**.
2. Importa el repositorio `taxdefense/peritajes-mecanicos`.
3. Framework Preset: **Other**. Sin comando de build. Output Directory: la raíz (déjalo vacío o `.`). Sin Install Command.
4. **Deploy**. Cada `git push` a `main` vuelve a publicar solo.

## Conectar el dominio perito-mecanico.cl

El dominio ya está delegado a los nameservers de Vercel; falta asociarlo al proyecto:

1. Proyecto → **Settings → Domains → Add** → `perito-mecanico.cl`.
2. Agrega también `www.perito-mecanico.cl` y elige **Redirect to perito-mecanico.cl** (301), para que haya una sola versión canónica.
3. Espera a que ambos aparezcan como **Valid Configuration** y a que se emita el certificado SSL (minutos).
4. Revisa `https://perito-mecanico.cl/robots.txt` y `https://perito-mecanico.cl/sitemap.xml`, y envía el sitemap en Google Search Console (propiedad de dominio).

## Mantenimiento

- **Nuevo artículo:** copia uno de `blog/`, cambia título, descripción, `canonical`, `og:url`, `og:image`, fechas y JSON-LD; agrega la tarjeta en la sección blog de `index.html`, la URL en `sitemap.xml` y su imagen en `assets/og/`.
- **Imágenes:** JPG de 1200 px de ancho como máximo y bajo 200 KB; siempre con `alt`, `width` y `height`, y `loading="lazy"` salvo la imagen principal visible al cargar.
- **Caché:** los archivos de `assets/` se sirven como inmutables por un año. Si reemplazas una imagen o video, súbelo con **otro nombre** y actualiza la referencia.
