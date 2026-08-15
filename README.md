# Docs legales de Stickea — publicación en GitHub Pages

Esta carpeta contiene el sitio legal de Stickea, listo para servirse como sitio estático:

| Archivo | Qué es |
|---|---|
| `index.html` | Landing (sirve como "sitio del desarrollador" en el listing de Play) |
| `privacy.html` | Política de privacidad (ES + EN) — la URL que pide Play Console |
| `terms.html` | Términos de uso (ES + EN) |
| `CNAME` | Dominio personalizado para GitHub Pages (`lookerdevelopers.com`) |

## Antes de publicar — placeholders a confirmar

1. **Email de contacto**: los tres HTML usan `contact@lookerdevelopers.com`. Crear ese buzón
   (o alias/redirección) en el dominio, o sustituirlo por el que se vaya a usar de verdad.
   Buscar y reemplazar en los tres archivos.
2. **Ley aplicable** (`terms.html` §10): puesta como España. Cambiar si no corresponde.
3. **Fecha de vigencia**: 15 de agosto de 2026. Actualizar si se publica más tarde o se edita.

## Publicar en GitHub Pages con el dominio propio

1. Crear un repo **público** nuevo (p. ej. `stickea-legal`) — solo estos archivos, **no** el
   código de la app.
2. Subir el contenido de esta carpeta a la raíz del repo (incluido `CNAME`).
3. En el repo: Settings → Pages → Source: `Deploy from a branch` → rama `main`, carpeta `/ (root)`.
4. En Settings → Pages → Custom domain debería aparecer ya `lookerdevelopers.com` (lo lee del
   `CNAME`). Activar **Enforce HTTPS** cuando el certificado esté emitido (tarda unos minutos).
5. En el DNS del dominio (apex `lookerdevelopers.com`):
   - 4 registros `A` apuntando a GitHub Pages:
     `185.199.108.153`, `185.199.109.153`, `185.199.110.153`, `185.199.111.153`
   - (Opcional) `AAAA`: `2606:50c0:8000::153`, `:8001::153`, `:8002::153`, `:8003::153`
   - (Opcional) `www` como `CNAME` → `<usuario>.github.io`
6. Verificar el dominio en GitHub (Settings de la cuenta → Pages → Verified domains) para que
   nadie más pueda apuntárselo.

## URLs resultantes (las que se pegan en Play Console)

- Política de privacidad: `https://lookerdevelopers.com/privacy.html`
- Términos: `https://lookerdevelopers.com/terms.html`
- Sitio del desarrollador: `https://lookerdevelopers.com/`

> Con dominio personalizado, la URL NO lleva el nombre del repo: el dominio mapea a la raíz del
> sitio del repo. Sin dominio, las URLs serían `https://<usuario>.github.io/stickea-legal/...`
> (también válidas para Play si el DNS se retrasa).

## Comprobación final

Abrir `https://lookerdevelopers.com/privacy.html` en una ventana de incógnito: debe cargar por
HTTPS sin avisos. Play Console valida que la URL sea pública y accesible sin login.
