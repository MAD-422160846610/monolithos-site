# LEEME-publicar · MonolithOS v1

> Este archivo **no se sube** al hosting. Es la guía interna para la fase 7.

---

## Tamaño total

**~150 KB** (carpeta `sitio-monolithos/web/v1/` completa)

---

## Lista de archivos a subir

```
web/v1/
├── index.html                    (46 KB)  — Página principal
├── 404.html                      (13 KB)  — Página 404
├── robots.txt                    (69 B)   — Permite todo, apunta a sitemap
├── sitemap.xml                   (363 B)  — Solo / y /404.html
├── marco/
│   └── index.html                (24 KB)  — CV (noindex, no en sitemap)
└── recursos/
    ├── favicon.svg               (8 KB)   — Copia de monolithos-micro.svg
    ├── apple-touch-icon.png      (4 KB)   — 180×180 desde avatar-512
    ├── monolithos-firma.svg      (12 KB)  — Firma horizontal
    ├── monolithos-firma-oscuro.svg (12 KB) — Firma horizontal oscura
    ├── monolithos-icono.svg      (8 KB)   — Icono
    └── monolithos-og-1200x630.png (1.6 KB) — **PLACEHOLDER HTML** (ver pendientes)
```

**Total: 12 archivos**

---

## Pendientes antes de subir

1. **Imagen OG real**: `recursos/monolithos-og-1200x630.png` es actualmente un archivo HTML (1.6 KB). Necesita renderizarse a PNG 1200×630. Requiere `npx playwright install` (aprobación de Marco).
2. **Firma de correo PNG**: `marca/identidad-monolithos-v1/kit/monolithos-firma-oscuro.png` pendiente (para `firma-correo.html`).
3. **Datos del CV**: 7 huecos `[DATO PENDIENTE: …]` en `cv-marco-aurelio.md` y `web/v1/marco/index.html`.
4. **Certificado IA Fluency**: nombre exacto pendiente de Marco.
5. **Cargo para firma de correo**: `[DATO PENDIENTE: cargo exacto que quiere Marco]`.
6. **Analítica**: ¿quiere Marco añadirla? (Decide en fase 7).

---

## Pasos de la fase 7 (Publicar)

1. **Hosting**: Marco elige y crea el repositorio/proyecto.
   - Recomendación: **GitHub Pages** (repo nuevo en MAD-422160846610).
   - Alternativa: Vercel (proyecto nuevo, nunca el de Sabueso).
2. **Seguridad**: Marco borra registro `piso1` (A 76.76.21.21, Vercel) y pausa proyecto Sabueso en Vercel. **No publicar mientras piso1 sirva ese panel.**
3. **DNS**: Marco cambia `@` y `www` en Namecheap a lo que pida el hosting. TXT `_dmarc` y `resend._domainkey` se quedan.
4. **Subida**: Subir solo el contenido de `web/v1/` (sin `LEEME-publicar.md`) al hosting elegido.
5. **Espera DNS + HTTPS**: Marco cambia DNS, espera resolución y activación de HTTPS en el hosting.
6. **Comprobaciones (las 5 deben pasar)**:
   - `https://monoglith.online/` abre con candado
   - `https://www.monoglith.online/` abre con candado
   - `http://` redirige a `https://`
   - `/una-ruta-que-no-existe` muestra el 404
   - Vista previa WhatsApp muestra imagen OG
   - `https://piso1.monoglith.online` **ya no** muestra panel de Sabueso
7. **Anotar fecha y resultado** en sección 10 del encargo y en tarjeta bitácora Trello.

---

## Instalaciones pendientes (si Marco aprueba)

- `npx playwright install` (para renderizar OG PNG y correr pruebas automáticas)
- `pip install fonttools` (en venv Hermes, para `fuentes.py`)

---

## Notas

- El CV (`marco/index.html`) tiene `noindex` y **no** está en `sitemap.xml`. Se enlaza desde la portada y entra al sitemap solo cuando no queden datos pendientes (fase 8).
- La imagen OG en producción será `https://monoglith.online/recursos/monolithos-og-1200x630.png` (definida en `og:image` y `sitemap.xml` no la incluye).
- No hay analítica, píxeles ni cookies (privacidad en pie de página).