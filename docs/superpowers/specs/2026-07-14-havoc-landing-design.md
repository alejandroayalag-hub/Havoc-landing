# HAVOC — Landing de servicios · Diseño

**Fecha:** 2026-07-14
**Proyecto:** havoc-landing
**Dominio:** havocdev.mx
**Puerto nginx (prod):** 8094 · Hetzner 62.238.3.136
**Tipo:** Sitio estático (sin backend, sin base de datos)

## Objetivo

Landing de una sola página para HAVOC — Soluciones Integradas, empresa de
desarrollo de software propiedad del usuario. Presenta los servicios, la
propuesta de valor y una vía de contacto. Primer entregable de la marca; el
correo de dominio y el número de WhatsApp se conectan cuando existan.

## Marca (fuente: manual de marca v2)

- **Nombre:** HAVOC — Soluciones Integradas
- **Ubicación:** Uruapan, Michoacán
- **Posicionamiento:** "Control sobre el caos operativo." El báculo representa
  energía contenida y dirigida, no destrucción.
- **Valores:** Cumplimiento · Claridad · Cercanía
- **Voz:** clara (no clínico-fría), segura (nunca alarmista), cercana (no
  casual), precisa (datos exactos, no hype). Prohibido lenguaje tipo
  "revolucionamos con IA de última generación".

### Paleta

| Rol | Nombre | Hex |
|-----|--------|-----|
| Base / fondo primario | Ciruela | `#1E1533` |
| Acento / acciones | Violeta | `#8B5CF6` |
| Acento fuerte | Violeta profundo | `#5B21B6` |
| Texto | Tinta | `#1B1424` |
| Texto secundario | Gris | `#7C748B` |
| Fondo claro | Niebla | `#F5F2FA` |
| Base clara | Blanco | `#FFFFFF` |

**Regla de uso:** el violeta se reserva para acciones, énfasis y datos —
nunca como color de fondo dominante. Ciruela sostiene, violeta activa.

### Tipografía (Google Fonts)

- **Space Grotesk** (700, 600) — títulos, wordmark, cifras destacadas
- **Inter** (400/500/600/700) — cuerpo de texto e interfaz
- **IBM Plex Mono** — datos, cifras técnicas, etiquetas tipo `01 — SERVICIOS`

### Logo

Báculo. Versiones disponibles: primaria, solo ícono, monocromático, invertido.
Favicon e ícono de app = báculo. Los archivos de logo se colocan en
`assets/` (pendiente exportarlos del manual/diseñador).

## Arquitectura

- Página única `index.html` + `styles.css` + `main.js` mínimo.
- `main.js` solo para: toggle de menú móvil y scroll suave a anclas.
- Sin framework, sin build step, sin backend, sin base de datos.
- Fuentes vía Google Fonts (`<link>` en `<head>`).
- Servido por nginx en el puerto 8094 sobre `havocdev.mx`.
- Carpeta del proyecto: `~/havoc-landing/`.

Mismo patrón que gioval-landing y pedraza-landing (estáticos ya en producción).

## Secciones

1. **Hero** — fondo ciruela. Báculo + wordmark HAVOC. Headline "Control sobre
   el caos operativo." Subtítulo de una línea. CTA violeta → WhatsApp.
2. **Qué hacemos** — párrafo corto de posicionamiento: ordenamos la operación
   que hoy vive en papel, Excel o cuadernos.
3. **Servicios** — 5 cards:
   - Apps web a medida (RH, escolar, jurídico, field-service, etc.)
   - Apps móviles (iOS / Android, Expo)
   - Landings y sitios
   - Integraciones (pagos, GPS, QR, biométrico)
   - Deploy, hosting y mantenimiento — *solo de lo que desarrollamos nosotros*
4. **Cómo trabajamos** — 3 columnas: Cumplimiento · Claridad · Cercanía.
5. **Proyectos** — prueba social anonimizada por sector, sin nombres de
   cliente:
   - Clínica estética — expediente NOM-004, farmacia, app iOS
   - Field-service HVAC — assessment con fotos, roles, app móvil
   - Control escolar — cobranza, RH, notificaciones a padres
   - (más cards según sectores atendidos)
6. **Contacto** — botón WhatsApp (placeholder `wa.me/52XXXXXXXXXX`) + email
   `contacto@havocdev.mx`. Ubicación: Uruapan, Michoacán.
7. **Footer** — logo invertido, © 2026 HAVOC, links a secciones.

## Responsive y meta

- Móvil primero. Menú hamburguesa en móvil.
- Favicon = báculo.
- Meta Open Graph (título, descripción, imagen) para que el link se vea bien
  al compartir por WhatsApp.

## Placeholders a resolver (fuera de este entregable)

- **Número de WhatsApp:** `wa.me/52XXXXXXXXXX` → cambiar a una sola línea
  cuando exista el número.
- **Email:** `contacto@havocdev.mx` funciona cuando se monte el correo de
  dominio (tarea aparte: Google Workspace + DNS, como Gioval).
- **Archivos de logo/báculo:** exportar del manual a `assets/` (SVG/PNG).

## Fuera de alcance (v1)

- Formulario que guarde leads (requeriría backend + DB — no en v1).
- Blog / CMS.
- Multi-idioma.
- Analítica (se puede agregar después con un snippet).
