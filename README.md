# Inteligencia Artificial para Bomberos

Presentación HTML para el **taller de 1 hora sobre IA dado a bomberos voluntarios**
(Federación de Bomberos de la Provincia de Buenos Aires).

**Orador:** Alan Tapia
**Audiencia:** bomberos voluntarios, mayoritariamente +60 años. Diseño de alto contraste,
tipografía grande, una idea por slide, cero inglés en pantalla.

## Ver online

👉 **https://soyalantapia.github.io/presentacion-bomberos-evento/**

## Navegación

- `← →` · `Espacio` · `Re Pág / Av Pág` — moverse entre slides
- `Inicio` / `Fin` — primera / última slide
- Flechas grandes en las esquinas (mouse, pantalla táctil o control remoto)
- Swipe en celular · click en los puntos laterales para saltar

## Cómo editar el texto de una slide

Todo vive en un único archivo: **`index.html`**. No hay que compilar nada.

1. Abrí `index.html`.
2. Buscá (Ctrl-F / Cmd-F) el **ancla** de la slide, por ejemplo `S07` o `S17`.
   Cada slide arranca con un comentario como `<!-- ===== S07 · MITO 1 ===== -->`.
3. Cambiá el texto que está entre las etiquetas. Lo importante:
   - El **título** está en `<h2 class="title">…</h2>`.
   - Para resaltar una palabra en rojo, envolvela en `<span class="accent">…</span>`.
   - Un salto de línea es `<br>`.
4. Guardá y recargá el navegador.

**Los números de slide se calculan solos** (no hay que renumerar al agregar o quitar slides).

### Cosas que vas a querer reemplazar antes del evento

| Qué | Dónde | Cómo |
|---|---|---|
| **Logo de la federación** (S1) | ancla `S01` | reemplazá el recuadro `<div class="placeholder">…</div>` por `<img src="assets/logo-federacion.png" alt="Federación" style="max-height:18vh">` y poné el archivo en `assets/`. |
| **Fotos de medios** (slide 2 "Sobre mí") | `assets/` | dejá en `assets/` los archivos `medio-1.jpg` … `medio-4.jpg`. **Aparecen solos** cuando existen; mientras no estén se ve el recuadro "MEDIO N". Tu foto del retrato es `assets/alan-tapia.jpg`. |
| **Contacto de Alan** (S29) | ancla `S29` | editá el bloque `.contact-lines` (nombre, rol y la línea de contacto). La foto es `assets/alan-tapia.jpg`. |
| **Códigos QR** (S26) | `assets/qr-*.svg` | ya apuntan a `meta.ai`, `chatgpt.com` y `claude.ai`. Si querés otros destinos, regenerá los SVG (ver abajo) o reemplazá los archivos. |

## Cambiar colores y tamaños

Todo el diseño sale de unas pocas variables al principio de `index.html`, en el bloque
`:root` (buscá `TOKENS`). Cambiás una variable y cambia toda la presentación:

- `--red-600`, `--red-700`… → la paleta rojo bombero.
- `--ink`, `--paper`, `--charcoal`… → los neutros.
- `--size-title`, `--size-body`, `--size-huge`… → la escala tipográfica (ya está grande
  para gente mayor y para proyectar).

## Funciona 100% offline

Una vez que carga, **no necesita internet**:

- La fuente (**Poppins**) está incluida en `assets/fonts/` (no se baja de Google).
- Todos los íconos son **SVG dibujados a mano** dentro del HTML.
- Los **QR son SVG locales** en `assets/`.

Ideal para un aula con wifi flojo: abrís la página una vez y ya está.

## Stack

- HTML + CSS + JavaScript **vanilla**, en un solo archivo. **Cero dependencias.**
- 28 slides, formato 16:9 optimizado para proyector, responsive.
- Accesible: alto contraste (AA), foco visible, navegación por teclado, respeta
  `prefers-reduced-motion`.

## Correr en local

Cualquier servidor estático sirve. Por ejemplo:

```bash
python3 -m http.server 8099
# abrí http://localhost:8099
```

## Regenerar los QR (opcional)

Si cambiás los destinos de los QR:

```bash
python3 -m venv /tmp/qrvenv && /tmp/qrvenv/bin/pip install qrcode
/tmp/qrvenv/bin/python - <<'PY'
import qrcode
from qrcode.image.svg import SvgPathImage
targets = {"qr-meta":"https://meta.ai","qr-chatgpt":"https://chatgpt.com","qr-claude":"https://claude.ai"}
for name,url in targets.items():
    qr = qrcode.QRCode(error_correction=qrcode.constants.ERROR_CORRECT_M, border=2)
    qr.add_data(url); qr.make(fit=True)
    qr.make_image(image_factory=SvgPathImage).save(f"assets/{name}.svg")
PY
```

## Deploy (GitHub Pages)

El sitio se publica desde la rama `main` (carpeta raíz). Cada `git push` a `main`
actualiza la web automáticamente en
**https://soyalantapia.github.io/presentacion-bomberos-evento/**.

## Estructura

```
index.html          ← toda la presentación (slides + estilos + navegación)
BRIEF.md            ← contenido: el guion slide por slide (fuente de verdad)
assets/
  fonts/            ← Poppins (offline)
  qr-*.svg          ← códigos QR
  alan-tapia.jpg    ← foto del cierre
```

## Licencia

Contenido: © 2026 Alan Tapia. Código: uso libre con atribución.
