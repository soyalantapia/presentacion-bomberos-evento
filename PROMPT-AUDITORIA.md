# 🔍 PROMPT MAESTRO DE AUDITORÍA — Presentación "IA para Bomberos" (Federación Bonaerense)

## 0. ROL Y MISIÓN

Sos un **director creativo senior + auditor experto** que combina cinco disciplinas en una sola cabeza:
- **Diseño de presentaciones** (decks de keynote, proyección en aula, jerarquía visual a distancia).
- **UX / UI** (layout, espaciado, consistencia de componentes, estados, navegación).
- **Copywriting en español rioplatense** (claridad, voseo, tono, ortografía y gramática impecables).
- **Accesibilidad WCAG** (contraste, alt text, foco, tamaños de target, daltonismo, motion).
- **Storytelling y dirección escénica** (arco narrativo, ritmo, picos emocionales, CTA).

**Tu orden es absoluta:** auditar **ABSOLUTAMENTE TODO** esta presentación al máximo detalle posible —cada slide, cada palabra, cada color, cada componente, cada decisión narrativa— y devolver un **plan de acción priorizado, concreto y accionable**, con copy y valores exactos propuestos (nunca vaguedades).

No es una revisión cosmética. Es una auditoría de combate: esta charla se da **una sola vez, en vivo, frente a bomberos voluntarios mayores y escépticos**, y de cómo salga depende que un proyecto de tecnología para la Federación arranque o muera. Pensá como el director que tiene que dejar el deck listo para que el orador la rompa, y como el auditor que no deja pasar ni una tilde.

**Tenés TODO el contexto embebido abajo.** No necesitás abrir ningún archivo para entender dónde estamos parados. Si tenés acceso al `index.html` real, usalo para verificar al detalle; si no, auditá íntegramente sobre el contexto provisto, que es exhaustivo.

---

## 1. CONTEXTO ENORME (todo lo que necesitás saber)

### 1.1 Qué es el proyecto

Una **presentación web single-file** (`index.html`, HTML/CSS/JS en un solo archivo, **zero-deps, 100% offline**), pensada para proyectarse en un aula. Se llama informalmente **"IA para Bomberos"**. Stack:
- **HTML único** con todo embebido (estilos en `<style>`, lógica en un único `<script>` con la clase `SlidePresentation`).
- **Poppins self-hosted** en `assets/fonts/` (woff2, pesos 400/600/700/800/900), cero Google Fonts → funciona sin internet (clave: el aula puede no tener wifi).
- **QRs en SVG** y fotos en `assets/`.
- Deploy en **GitHub Pages** (export estático).
- Navegación por **scroll-snap + teclado + swipe + dots** (las flechas existen pero están ocultas por CSS).

### 1.2 Evento, Federación, orador

- **Evento:** Taller "IA para Bomberos" de la **Federación de Asociaciones de Bomberos Voluntarios de la Provincia de Buenos Aires**. Formato: intro corta + taller (~1h). Es la antesala de una posible gira regional.
- **Orador:** **Alan Tapia** — empresario tecnológico, CEO de Deenex (gastronomía) y de Xnod (IA para empresas), conferencista, +350 clientes en el país.
- **Stakeholder político:** el presidente de la Federación dio luz verde condicionada. **Reglas sensibles de framing (respetar SIEMPRE):** la IA es **INVERSIÓN, no gasto**; el wedge es **finanzas del cuartel**; **NO** decir nunca "veo todo" / "te vigila"; el tono debe ser de **respeto y dignidad** al bombero, jamás condescendiente.

### 1.3 OBJETIVO de la charla (triple, jerarquizado)

1. **Desmitificar** — sacar el miedo, mostrar que la IA es **gratis, fácil y útil**.
2. **Acción inmediata** — que prueben "algo este lunes" (slide 31).
3. **Retención** — que se sumen al **grupo de WhatsApp de la Federación** (slides 34/35/37), respaldado con valor ("un consejo por semana").

Embudo: bajar ansiedad → dar la victoria fácil → capturar el contacto.

### 1.4 AUDIENCIA (lo más importante de todo)

**Bomberos voluntarios de la Provincia de Buenos Aires, muchos mayores (60–75+), baja alfabetización digital, profundo orgullo de servicio, fuerte escepticismo tecnológico.**
- **No están ahí por curiosidad sobre IA** — están por la institución, por respeto a la Federación. Hay que ganárselos **emocionalmente antes que intelectualmente**.
- El miedo dominante **no es "no entiendo"**, es **"esto me va a hacer sentir tonto / inútil / viejo / reemplazable"**.
- El orador tiene un **problema de credibilidad inverso**: ante esta sala, "empresario tech de la IA" puede leerse como "el que viene a vendernos humo". Hay que tender un **puente humano** antes que exhibir credenciales.
- **Regla de oro de la auditoría:** ante cada decisión, preguntate **"¿esto lo entiende y lo disfruta un bombero de 75 años sentado en la última fila del aula?"**.

### 1.5 SISTEMA DE DISEÑO COMPLETO (valores exactos)

#### 1.5.1 Tokens de color (`:root`, líneas 24–43) — paleta rojo bombero + neutros

**Rojo bombero (escala):**

| Variable | HEX | Uso documentado |
|---|---|---|
| `--red-900` | `#7F1D1D` | Fin de gradientes 140° (block-slide, title-slide) |
| `--red-800` | `#991B1B` | Texto en `.demo-tag.good` |
| `--red-700` | `#B91C1C` | **Rojo para TEXTO sobre blanco (AA, ~5.9:1)**: `.eyebrow`, `.formula .key`, `.about-text strong`, hover `.nav-arrow`, inicio de gradientes |
| `--red-600` | `#DC2626` | **Rojo principal / acento (dominante)**: progress-bar, nav-dots activos, nav-arrow, focus outline, `.title .accent`, `.eyebrow::before`, illust, bordes/numeritos. Sobre blanco da **~4.4:1 (JUSTO en el borde de AA texto normal)** |
| `--red-500` | `#EF4444` | `.emphasis-phrase .accent`, color del tachado `.mito-false` |
| `--red-100` | `#FEE2E2` | Fondo círculo de icono en `.feature-card .illust`, fondo `.demo-tag.good` |
| `--red-50` | `#FEF2F2` | Fondo círculo emoji en `.reason .r-emoji` |

**Neutros:**

| Variable | HEX | Uso |
|---|---|---|
| `--ink` | `#1A1A1A` | Texto principal (contraste altísimo) |
| `--ink-soft` | `#57534E` | Texto secundario (AA): subtítulos, descripciones, slide-number, tags neutros |
| `--paper` | `#FFFFFF` | Fondo `.content-slide` |
| `--paper-2` | `#FAF7F5` | "Blanco cálido": fondo `body`, `.content-slide.warm`, demo-ask, io-frame, cam-steps, placeholders dark |
| `--paper-3` | `#F0EBE8` | Fondo `.demo-tag.bad` |
| `--line` | `#E7E0DC` | Bordes/divisores |
| `--charcoal` | `#1C1917` | Fondo oscuro (slides de frase): `.emphasis-slide`, inicio gradiente `.thanks-slide` |
| `--ok` | `#15803D` | Verde sobrio, solo para el ✓ de "verdad" (uso muy puntual) |
| `--white` | `#FFFFFF` | Alias de blanco |

**Literales NO tokenizados (hardcodeados):** `#fff`/`#FFFFFF` (texto sobre oscuros, fondos de tarjetas, bordes de fotos); `#2b1414` (fin gradiente `.thanks-slide`); sombras/overlays con alfa: `rgba(0,0,0,0.18/0.22/0.28)`, `rgba(255,255,255,0.06/0.10/0.14/0.35/0.6/0.9/0.95)`, glow rojo emphasis `rgba(220,38,38,0.22)`, nav-dot inactivo `rgba(185,28,28,0.25)`, sombras rojizas de tarjetas `rgba(180,30,30,0.10/0.12/0.18)`.

#### 1.5.2 Tokens de tipografía

- **Familia:** `--font: "Poppins", system-ui, -apple-system, "Segoe UI", Roboto, sans-serif;` (línea 47).
- **Poppins self-hosted** vía `@font-face` (L14–18), todas `font-display:swap`, woff2, en `assets/fonts/poppins-{peso}.woff2`. Pesos: **400, 600, 700, 800, 900** (⚠️ **NO existe 500 self-hosted**; lo que use `font-weight:500` cae al fallback del navegador).
- Filosofía declarada: *"Escala GRANDE: audiencia 60+ y proyección en aula"*.

**Escala (todas en `clamp()`, L49–56):**

| Token | `clamp()` literal | Propósito |
|---|---|---|
| `--size-hero` | `clamp(3rem, 8vw, 7rem)` | títulos portada/sección |
| `--size-huge` | `clamp(4rem, 12vw, 11rem)` | números gigantes |
| `--size-title` | `clamp(2.2rem, 5.5vw, 4.5rem)` | título de slide (`.title`, `.mito-true`) |
| `--size-h2` | `clamp(1.6rem, 3.5vw, 2.8rem)` | `.lead`, `.name`, `.r-head`, `.bl-tag`, `.q-foot` |
| `--size-h3` | `clamp(1.3rem, 2.4vw, 2rem)` | `.subtitle`, labels, formula li, about-role |
| `--size-body` | `clamp(1.15rem, 1.8vw, 1.6rem)` | `.body-text`, demo, cam-steps, about-bio |
| `--size-small` | `clamp(1rem, 1.4vw, 1.3rem)` | `.eyebrow`, `.tiny-note`, tags, placeholders |
| `--size-tiny` | `clamp(0.8rem, 1vw, 1rem)` | `.slide-number` |

**Hardcodeados (no usan tokens):** `.block-label` `clamp(1rem,1.6vw,1.4rem)`; `.block-title` `clamp(2.75rem,8vw,7rem)` peso 900; `.emphasis-footnote` `clamp(1.1rem,1.8vw,1.5rem)`; `.age-line .num` `clamp(3.5rem,11vh,7rem)` peso 900 lh 0.9 rojo; `.io-ph small` `0.78em`; `.reason .r-emoji` `clamp(1.7rem,4vh,2.6rem)`, `.r-num` `0.62em`; `.lunes .num` `0.85em`.

**Pesos/tracking:** negrita 900 en números/labels enfáticos; `letter-spacing` títulos negativos (`-0.02em` a `-0.03em`), eyebrow `0.14em`, block-label `0.3em`, q-eyebrow `0.18em`, slide-number `0.1em`. `line-height`: títulos 1.04–1.2; cuerpo 1.4–1.55; números gigantes 0.9–1.1.

#### 1.5.3 Espaciado, radios, sombras, easing, z-index

**Espaciado (`:root`, L59–61):** `--slide-padding: clamp(1.75rem,4.5vw,4.5rem)`; `--gap: clamp(0.9rem,1.8vw,1.75rem)`; `--gap-lg: clamp(1.5rem,3vw,3rem)`. `--slide-padding` se redefine a `clamp(1.25rem,3.5vw,3rem)` (≤760px alto) y `clamp(1rem,3vw,2rem)` (≤600px alto).

**Easing (L64–65):** `--ease: cubic-bezier(0.22,1,0.36,1)` (out suave, "sobrio, nada que maree"); `--dur: 0.5s`.

**Radios (literales):** circulares `50%` (dots, nav-arrow, círculos de icono/número); pill `999px` (io-tag, demo-tag, guess-bubble, cam-steps); tarjetas: feature-card `26px`, reason `22px`, chess-photo `18px`, qr `18px`, placeholder `16px`, io-frame `16px`, lunes `14px`, qr-card `14px`, demo-answer `12px`, demo-ask `10px`, tool-tile badge `26%`, formula val `8px`, bl-img `10px`.

**Sombras:** rojizas de marca `0 10px 44px rgba(180,30,30,0.12)` (feature-card), `0 10px 34px rgba(180,30,30,0.10)` (reason), `0 10px 36px rgba(180,30,30,0.18)` (grupo qr); neutras `0 3px 12px rgba(0,0,0,0.05)` (lunes); fotos `0 16px 48px rgba(0,0,0,0.22)` (chess/io), `0 10px 36px rgba(0,0,0,0.28)` (pf-item); UI `0 6px 20px rgba(0,0,0,0.18)` (nav-arrow).

**z-index:** progress-bar `100` (lo más alto), nav-arrow `60`, nav-dots `50`, slide-inner sobre overlays `1`, fotos solapadas `.pf-item` `1–4`.

#### 1.5.4 Componentes (clases) — propósito + claves

**Layout base:** `.slide` (full-screen `100vw×100dvh` con fallback 100vh, `overflow:hidden`, scroll-snap-align:start, flex column, padding `--slide-padding`); `.slide-inner` (centrado, gap `--gap`, max-width 1200px); `img` global (`max-width:100%`, `max-height:min(50vh,420px)`, `object-fit:contain`).

**5 TIPOS de slide (plantillas):**
1. **`.block-slide`** (separador): gradiente `linear-gradient(140deg, --red-700 0%, --red-900 100%)`, texto blanco, `::before` con dos radial-gradients. Internos: `.block-label` (tracking 0.3em, opacity .85), `.block-title` (900), `.block-decor` (barra 4px blanca).
2. **`.content-slide`** (contenido): `--paper`; variante `.warm` → `--paper-2`.
3. **`.emphasis-slide`** (frase, oscuro): `--charcoal`, `::after` glow rojo radial `rgba(220,38,38,0.22)`. `.emphasis-phrase` (800), `.accent` → `--red-500`, `.emphasis-footnote` (opacity .75).
4. **`.title-slide`** (portada): gradiente rojo 140°, `::before` luz+sombra; `.hero` (900), `.by` (500, opacity .9).
5. **`.thanks-slide`** (cierre): gradiente `140deg, --charcoal 0%, #2b1414 100%`; `.contact-card`, img círculo borde 4px rojo.

**Tipografía/encabezados:** `.eyebrow` (700, tracking 0.14em, uppercase, `--red-700`, `::before` barra roja; variante `.light` para oscuros); `.title` (800, tracking -0.02em) + `.title .accent` (rojo 600); `.lead` (700, h2); `.subtitle` (400, h3, ink-soft); `.body-text` (400, lh 1.55); `.tiny-note` (500, small, ink-soft).

**Ilustración SVG:** `.illust` (flex centrado, color `--red-600`; svg `clamp(130px,26vh,300px)`; variante `.sm` → `clamp(90px,16vh,170px)`). En slides oscuros pasa a `#fff`.

**Grillas:** `.two-col`/`.three-col` (gap-lg), `.four-col` (gap). `.feature-card`: tarjeta blanca premium, radius 26px, `border-top:8px solid --red-600`, sombra rojiza, `min-height:clamp(320px,58vh,460px)`; `.illust` círculo `--red-100`; `.label` (900); `.desc` (h3, ink-soft, max 24ch).

**Específicos:** `.q-eyebrow/.q-foot/.guess-bubble` (pill blancas translúcidas rotadas -4°/3°/-2°/4°); `.chess-layout/.chess-photo` (foto borde 6px blanco, aspect 4/3) `.chess-cap` `.age-line .num` (rojo 900); `.io-layout/.io-card/.io-tag/.io-frame/.io-ph/.io-arrow` (demo prompt→salida, io-frame aspect 16/10 borde 6px blanco, io-arrow rota 90° en mobile); `.mito/.mito-false/.arrow-down/.mito-true` (false tachado con comillas «» vía `::before/::after`, true 800 + accent rojo); `.demo/.demo-tag(.bad/.good)/.demo-ask/.demo-answer`; `.formula/.key/.val` (key 800 rojo-700 nowrap, val pill suave); `.secrets/.secret/.secret-num` (círculo rojo 900); `.reasons/.reason` (tarjeta blanca radius 22px `border-left:9px solid --red-600`, `.r-emoji` círculo `--red-50` con `.r-num` badge); `.brand-lockup/.bl-sigla/.bl-tag`; `.init-points/.init-point` + `.qr-join`; `.lunes/.lunes li/.num` (items blancos `border-left:6px solid --red-600`); `.tool-tiles/.tool-tile/.badge` (squircle 26% SVG blanco); `.qr-grid/.qr-card/.qr-ph` + `.cam-steps/.step/.sep`; `.about-layout` (grid 1.2fr 1fr) + `.about-text/.about-role/.about-bio` + `.photo-fan/.pf-item` (4 fotos solapadas borde 5px blanco rotadas -7°/6°/5°/-8°); `.placeholder` (dashed, variante `.dark`).

**Nav/UI fija:** `.progress-bar` (top, 5px, rojo-600, z 100); `.nav-dots` (derecha, 9×9px, inactivo `rgba(185,28,28,0.25)`, activo rojo-600 `scale(1.7)`); `.nav-arrow` (`clamp(54px,7vh,72px)`, **`display:none` por defecto, NUNCA se ven**); `.slide-number` (abajo-der, tabular-nums); `.keyboard-hint` (`display:none`, nunca aparece).

#### 1.5.5 Animación + navegación + responsive

- **Reveal/stagger:** `.reveal` (opacity 0 → translateY 22px→0, `--dur` 0.5s, cascada `:nth-of-type` delays .05/.15/.25/.35/.45/.55s); `.stagger > *` (translateY 16px, delays .20/.32/.44/.56/.68s). Ambos dependen de `.visible`.
- **IntersectionObserver** threshold 0.5 → agrega `.visible`, actualiza currentIndex/progress/dots/flechas. Slide 0 recibe `.visible` al iniciar.
- **Scroll-snap nativo** `y mandatory` + `scroll-behavior:smooth`. Nav: teclado (↓/→/Espacio/PageDown=next; ↑/←/PageUp=prev; Home/End), swipe vertical (>60px), rueda (|deltaY|>30, lock 700ms), dots.
- **Accesibilidad motion:** `:focus-visible` outline 4px rojo-600 offset 3px; `@media (prefers-reduced-motion: reduce)` anula animaciones y scroll smooth.
- **Responsive altura:** `≤760px` redefine padding/title/huge; `≤600px` achica y **oculta** nav-dots+keyboard-hint.
- **Responsive ancho (`≤760px`, todo `!important`):** grillas colapsan a `1fr`, `.io-layout` → column, `.io-arrow` rota 90°.

### 1.6 INVENTARIO DE LOS 37 SLIDES

| # | Bloque | Tipo | Título | Textos clave | Ícono/Asset | Placeholder |
|---|---|---|---|---|---|---|
| 1 | B1 Conectar | title-slide | **La IA ya está en tu bolsillo** | Subtítulo «Inteligencia Artificial para Bomberos» · by «Alan Tapia» | `logo-federacion.png` | No |
| 2 | B1 (Sobre mí) | content | **Alan Tapia** | eyebrow «Sobre mí»; role «Empresario tecnológico · Conferencista en IA»; bio (Deenex, Xnod, +350 clientes en negrita rojo) | photo-fan `medio-1..4.jpg` | No |
| 3 | B1 (¿Por qué acá?) | content warm | **¿Por qué estoy [acá]?** | 3 razones: «Es un gran momento»/«Y están justo a tiempo» · «No hay que ser experto»/«Si manejás el teléfono, podés» · «Los hace más fuertes»/«Más tiempo para lo que importa» | emojis 🚀📱💪 | No |
| 4 | B1 (S02) | content | **¿Quién ya usó la [inteligencia artificial]?** | Solo título (salto de línea) | SVG mano levantada | No |
| 5 | B1 (S03) | content | **Es como chatear por [WhatsApp].** | Subtítulo «Solo que del otro lado hay algo que sabe de casi todo y te responde al instante» | SVG burbuja chat | No |
| 6 | B1 (S04) | content warm | **Tres cosas a su favor.** | 3 feature-cards: «Sabe de todo»/«Medicina, leyes, cocina, técnica…» · «Nunca se cansa»/«24 horas, 365 días» · «Habla tu idioma»/«Sin comandos ni claves…» | 3 SVG (libro, reloj, chat) | No |
| 7 | B1 (S05) | emphasis | **¿Cuántos años tiene la inteligencia artificial?** | q-eyebrow «Una pregunta»; burbujas «¿5 años?»«¿15?»«¿30?»«¿50?»; q-foot «Tírenme un número» | burbujas mockup | No |
| 8 | B1 (S05b) | content | **No es nueva.** | body «La idea nació en 1956. Y para 1997 ya le ganaba al ajedrez al mejor del mundo»; age-line «70 años con nosotros»; cap «1997 · Kasparov vs. Deep Blue (IBM)» | `ajedrez.jpg` (con fallback) | **Sí** |
| 9 | B1 (S06) | block | **5 mitos para tirar a la basura** | Solo block-title (3 saltos) | SVG tacho basura | No |
| 10 | B1 (S07·Mito 1) | content | **Es una herramienta más. [Como la autobomba.]** | false «Me va a reemplazar»; note «La máquina la manejás vos» | SVG llama + arrow-down | No |
| 11 | B1 (S08·Mito 2) | content | **Si sabés mandar un audio, [ya sabés usarla].** | false «Es para los que saben de tecnología» | SVG micrófono + arrow | No |
| 12 | B1 (S09·Mito 3) | content | **Existen [opciones gratuitas].** | false «Es cara» | SVG $ tachado + arrow | No |
| 13 | B1 (S10·Mito 4) | content | **Lo mismo decían del [internet en el 95].** | false «Es una moda» | SVG monitor viejo + arrow | No |
| 14 | B1 (S11·Mito 5) | content | **A veces sí. Revisala, como a un [empleado nuevo].** | false «Inventa cosas» | SVG lupa + arrow | No |
| 15 | B1 (S12) | content warm | **¿Cómo sabe tanto?** | body «Se leyó casi todo lo que se escribió: libros, manuales, enciclopedias, diarios. Millones. Y no se olvida de nada»; note «Como el bibliotecario más sabio del mundo, en tu teléfono» | SVG pila de libros | No |
| 16 | B2 Hablarle (S13) | content | **Pedile como un [mandado].** | Solo título | SVG bolsa/changuito | No |
| 17 | B2 (S14) | content warm | **La estructura de un [buen mandado].** | 4 features: «Quién querés que sea» · «Qué querés» · «Para quién» · «Cómo lo querés» | 4 SVG (persona, doc, dos personas, lista) | No |
| 18 | B2 (S14b) | content | **Se arma así.** | fórmula: «Portate como»→«un jefe de cuartel» · «Necesito que»→«escribas un comunicado» · «Es para»→«los bomberos del cuartel» · «Que sea»→«corto y firme»; note «Las cuatro cositas, en una sola frase» | SVG grilla 2×2 | No |
| 19 | B2 (DEMO) | content | **Esto pedí... [y esto me dio.]** | io-tag «Lo que escribí» / «Lo que respondió»; note «En segundos. Sin saber nada de computación» | `demo-prompt.jpg` + `demo-salida.jpg` (con fallback) | **Sí** |
| 20 | B2 (Secretos) | content warm | **Tres secretos.** | «Sé específico»/«Pedí con detalle…» · «Dale contexto»/«Contale la situación…» · «Corregí sin miedo»/«¿No te gustó? Decile qué cambiar…» | secret-num 1·2·3 | No |
| 21 | B2 (Casa mal) | content | **Es como mandar a limpiar la casa.** | ask «Limpiá la casa»; answer «…la mesa sin tocar, los vidrios sucios, el piso a medias»; lead «¿La culpa? Tuya: no fuiste específico» | bloques demo | No |
| 22 | B2 (Casa bien) | content | **Ahora pedilo [bien.]** | tag «Así sí»; ask largo detallado; answer «…está todo hecho…»; lead «La diferencia no es la IA. Es cómo lo pedís» | bloques demo | No |
| 23 | B2 (S16·mal) | content | **(sin título — solo demo)** | tag «Pedir mal»; ask «Escribime un comunicado»; answer genérico burocrático | bloque demo | No |
| 24 | B2 (S17·bien) | content | **(sin título — solo demo)** | tag «Pedir bien»; ask «Portate como jefe de cuartel… capacitación obligatoria… firme pero respetuoso, cortito»; answer firmado «Jefe de Cuartel» | bloque demo | No |
| 25 | B2 (S18) | content warm | **Con [versiones gratis].** | tool-tiles «Asistente de WhatsApp» · «ChatGPT» · «Claude»; note «No hace falta acordarse los nombres» | 3 logos SVG (WhatsApp #25D366, ChatGPT #10A37F, Claude #D97706) | No |
| 26 | B3 Cuartel (intro) | content | **¿Cómo lo usamos en el [cuartel]?** | eyebrow «Manos a la obra»; subtítulo «Casos reales, del día a día» | SVG cuartel | No |
| 27 | B3 (Caso 1) | content | **¿Cuánta plata tiene tu cuartel [ahora mismo]?** | subtítulo «¿Cuánto gasté?»·«¿Me alcanza?»·«¿Cuándo vence el subsidio?»; note «Vos le das la info; ella la ordena» | SVG calculadora | No |
| 28 | B3 (S22) | content | **Protocolos y planes de entrenamiento, [en minutos].** | Solo título | SVG checklist | No |
| 29 | B3 (S23) | content warm | **Sacale una foto a un operativo.** | subtítulo «Te cuida como el veterano más sabio» | SVG cámara | No |
| 30 | B4 En vivo (S24) | content | **¿Quién trae un [dolor de cabeza] de su cuartel?** | Solo título | SVG bombilla idea | No |
| 31 | B5 Cierre (S25) | content warm | **5 cosas para [este lunes].** | eyebrow «Tu plan de acción»; lista: «Hacele una pregunta» · «Pedile un mensaje para el grupo del cuartel» · «Pedile una lista de tareas para la guardia» · «Sacale una foto a algo y preguntale qué ve» · «Preguntale cualquier duda» | num 1–5 | No |
| 32 | B5 (S26·QR) | content | **Entrá a las herramientas** | qr-cards «Asistente de WhatsApp»·«ChatGPT»·«Claude»; cam-steps «Abrí la cámara»→«apuntá»→«esperá 2 segundos» | `qr-meta.svg`, `qr-chatgpt.svg`, `qr-claude.svg` | No |
| 33 | B5 (S27·Orgullo) | emphasis | **En esta sala hay [miles de años] de experiencia.** | footnote «Eso no lo reemplaza ninguna máquina» | glow rojo | No |
| 34 | B5 (Iniciativa 1) | content | **El grupo oficial de la [Federación], enfocado en [tecnología].** | lockup «Bomberos PBA» + tag «Tecnología»; subtítulo «Un solo canal de WhatsApp para todos los cuarteles» | `logo-federacion.png` + `qr-grupo.svg` | No |
| 35 | B5 (Iniciativa 2) | content warm | **Un consejo de tecnología, [todas las semanas].** | eyebrow «Lo que vas a recibir»; init-points «Práctico y al grano»·«Una vez por semana»·«En texto o en video»; note «Cosas que podés aplicar ese mismo día» | 3 SVG (bombilla, calendario, play) | No |
| 36 | B5 (S28·Preguntas) | emphasis | **¿Qué preguntas tienen?** | footnote «Este es el momento. Los escucho» | SVG mano levantada | No |
| 37 | B5 (Sumate) | content | **Sumate al grupo.** | cam-steps «Abrí la cámara»→«apuntá»→«entrás al grupo»; cierre grande rojo «¡Gracias!» | `qr-grupo.svg` | No |

### 1.7 ESTADO DE ASSETS + PENDIENTES

**Presentes:** `ajedrez.jpg` (70KB), `alan-tapia.jpg` (62KB, **NO referenciada en `<img src>`** — verificar uso CSS), `logo-federacion.jpg` (46KB, **NO usada**, solo se usa el .png), `logo-federacion.png` (384KB, usada 2×: L554 y L1127), `medio-1..4.jpg` (318–385KB c/u), `qr-chatgpt.svg` (4.9KB, L1104), `qr-claude.svg` (4.9KB, L1105), `qr-meta.svg` (4.9KB, L1103), `qr-grupo.svg` (5.0KB, usado 2×: L1139 y L1188), fonts Poppins 400/600/700/800/900 woff2 (~8KB c/u).

**FALTANTES (críticos):**
- `assets/demo-prompt.jpg` — referenciada L883, **NO existe**. Tiene fallback onerror («FOTO DEL PEDIDO / assets/demo-prompt.jpg»), pero **la demo se ve incompleta**.
- `assets/demo-salida.jpg` — referenciada L893, **NO existe**. Mismo fallback. **Son el corazón del "wow moment" de la demo.**

**QRs:** los 4 son SVG path de módulos; **no se puede leer el destino desde el path**. Por contexto: `qr-meta`→meta.ai, `qr-chatgpt`→chatgpt.com, `qr-claude`→claude.ai (presumiblemente válidos). **`qr-grupo.svg` es el SOSPECHOSO/placeholder**: comentario L1187 dice literal *"reemplazá assets/qr-grupo.svg con el link real de invitación de WhatsApp"* → hoy apunta a un link genérico/no-real. **ACCIÓN: regenerar con el invite real (chat.whatsapp.com/…) y escanear los 4 con un celular para confirmar.**

**Fuentes:** 100% offline (clave para aula sin internet). Observaciones: (1) **sin `<link rel=preload>`** → posible flash de fuente de sistema al abrir; conviene preload de 800/900 (títulos). (2) **Verificar que el subset incluya á é í ó ú ñ ¿ ¡** (la presentación los usa por todos lados); si el subset es latin básico, esos glifos caen al fallback.

**JS:** numeración automática «NN · TT» (hoy «01 · 37», recalculada sola); nav-dots con aria-label; **flechas con JS cableado pero `display:none` permanente = código muerto**; IntersectionObserver; teclado/touch/wheel; progress-bar; `keyboard-hint` nunca aparece (la regla `:has` solo cambia opacity, no display).

**Accesibilidad (estado actual):** alt text **excelente (14/14 img)**; SVG decorativos `aria-hidden`; nav con roles correctos; `:focus-visible` rojo visible; contraste mayormente AA/AAA (ojo `--red-600` como texto en cuerpo chico); **nav-dots 9px < 44px mínimo touch**; flechas grandes (54–72px, buen target) desperdiciadas por estar ocultas; `prefers-reduced-motion` respetado.

**Pendientes declarados:** (1) crear `demo-prompt.jpg`/`demo-salida.jpg`; (2) regenerar `qr-grupo.svg` con invite real; (3) confirmar sigla oficial («Bomberos PBA» parece provisional); (4) confirmar conteo 37 slides (el BRIEF numeraba ~S28); (5) decidir flechas muertas (eliminar o reactivar); (6) escanear los 4 QR; (7) verificar subset de fuentes + preload; (8) tap targets de dots; (9) limpiar assets no usados (`logo-federacion.jpg`, posiblemente `alan-tapia.jpg`); (10) optimizar peso de imágenes (medios ~2MB, logo PNG 384KB → considerar webp / usar el .jpg 46KB).

### 1.8 ANÁLISIS DE ARCO NARRATIVO (diagnóstico de partida — verificalo, no lo des por cierto)

- **Idea central:** *"La IA no te reemplaza, te hace más fuerte — y vos ya sabés usarla"*. Herramienta más, como la autobomba: gratis, fácil, la manejás vos. Riesgo: la **tesis emocional real** ("ustedes son irreemplazables y esto los potencia") **recién aparece explícita en la slide 33, demasiado tarde** — debería ser el hilo conductor desde el minuto cero.
- **Bloques:** A Conexión y permiso (1–3); B Desmitificar qué es (4–8, 15); C Los 5 mitos (9–14); D Cómo hablarle (16–24); E Aplicar en el cuartel (25–30); F Cierre y conversión (31–37).
- **Joyas que YA funcionan (no romper):** «Es como chatear por WhatsApp» (5, la mejor analogía); reveal «70 años / 1997 ajedrez» (8, gran pico de sorpresa); «Si sabés mandar un audio, ya sabés usarla» (11, alivio); «Pedile como un mandado» (16, metáfora culturalmente perfecta); caso «plata del cuartel» (27, wedge financiero perfecto); «5 cosas para este lunes» (31, accionable); «miles de años de experiencia» (33, clímax emocional).
- **Problemas de ritmo:**
  - **#1 — Meseta de los 5 mitos (9–14, seis slides idénticas):** mismo layout/cadencia tachado→flecha→verdad seis veces. Para audiencia mayor = lista que no termina. Recomendación: dar aire a Mito 1 y 2 (los que importan), comprimir 3+4+5. Bajar de 6 a 4 slides levanta toda la charla.
  - **#2 — Cuádruple repetición "específico vs. vago" (18–24, siete slides para una idea):** fórmula (18), demo fotos (19), tres secretos (20), casa mal/bien (21–22), comunicado mal/bien (23–24). Ya entendieron en la 19. Elegir UN ejemplo y soltar el otro.
  - **#3 — Doble cierre de grupo + Q&A intercalado (33–37):** el pico (33) debería ser casi el final, pero después viene logística (34, 35), Q&A (36) y OTRA VEZ grupo (37). La energía sube y serpentea. Reordenar: Q&A → pico orgullo → CTA único → gracias.
- **Faltantes propuestos:** (1) slide de empatía/permiso al inicio ("Sé lo que están pensando: esto no es para mí — yo también pensaba eso"); (2) reframe del orador que lo conecte al servicio/voluntariado, no solo "+350 clientes"; (3) slide de PAYOFF del momento en vivo ("Miren lo que acaba de hacer en 20 segundos"); (4) slide de seguridad/privacidad ("no le des datos sensibles de personas; para lo demás, tranquilo") tras el caso de la plata; (5) slide de límite ("tres cosas que la IA NO reemplaza: tu criterio, tu experiencia, tu decisión final"); (6) prueba social local (un cuartel/bombero que ya la usa).
- **Redundancias:** fusionar casa (21–22) con comunicado (23–24) → quedarse con UNA (sugerido: el comunicado, por ser de su mundo); fusionar "Tres secretos" (20) con fórmula (17–18); comprimir Mitos 3+4+5; Mito 4 ("moda → internet 95") **pisa** el reveal de los 70 años (8); doble QR del grupo (34 y 37). **Neto: recortar 4–6 slides (de 37 a ~31–33) sin perder un solo argumento.**

---

## 2. DIMENSIONES A AUDITAR

Auditá **las diez dimensiones**. Para cada una: corré los checks, citá número de slide y proponé el fix exacto.

### (a) Ortografía y gramática
- Tildes correctas en todo (incl. mayúsculas y palabras como «más», «está», «día», «acá», «cómo», «qué», «sé»).
- Signos de apertura `¿` `¡` presentes y bien cerrados.
- Comillas latinas «» consistentes (el deck las usa en mito-false, demo-ask). Que no se mezclen con `"` rectas o `"" "`.
- Concordancia género/número; tiempos verbales coherentes.
- **Voseo rioplatense consistente** ("pedile", "sabés", "manejás", "tírenme") — que ninguna slide caiga en tuteo ("pídele", "sabes") por error.
- Puntos finales: definir regla (¿títulos con punto sí/no?) y que sea uniforme dentro de cada tipo de slide.
- Espacios, dobles espacios, guiones vs. rayas (—), uso de `·` separador.
- **Reportar:** lista de cada error con slide, texto actual y texto corregido exacto.

### (b) Tipografía
- Jerarquía clara por slide (eyebrow → título → cuerpo → nota): que el ojo sepa qué leer primero.
- **Legibilidad a 10 metros en proyector** para el bombero de la última fila: ¿algún cuerpo/nota queda chico? ¿Algún `clamp()` da un mínimo (`1rem`, `0.8rem`) insuficiente para aula?
- **Peso 500 inexistente self-hosted** (`.by`, `.subtitle`?, `.tiny-note` usan 500/400) → ¿hay textos que esperan 500 y caen al fallback con look distinto? Reportar dónde y proponer usar 400 o 600.
- Viudas/huérfanas y **saltos `<br>` forzados** (muchos títulos los tienen): ¿el salto manual rompe mal en proyector/responsive? ¿conviene dejar que fluya o fijar el salto?
- Líneas demasiado largas (`measure` > ~40–45 caracteres en cuerpo).
- Tracking negativo en títulos: ¿afecta legibilidad de palabras largas como «inteligencia artificial»?
- **Reportar:** por slide, problema tipográfico + valor/clase exacta a tocar.

### (c) Color y contraste
- **WCAG AA/AAA** en cada combinación texto/fondo. Verificá especialmente: `--red-600` (#DC2626) usado como **texto de acento** (~4.4:1) — OK en títulos grandes (>3:1 AA grande), **prohibido en cuerpo chico**. Reportar cualquier `.accent` o `inline` rojo sobre texto pequeño.
- Texto blanco/atenuado (opacity .7–.9) sobre gradiente rojo (red-700→red-900) y sobre charcoal: confirmar AA.
- Uso coherente de los dos rojos: **`--red-700` para texto sobre blanco**, **`--red-600` para acentos/bordes/fondos**. Marcar cualquier inversión.
- Verde `--ok` reservado solo al ✓ de verdad: que no se filtre a otro lado.
- **Daltonismo (protanopia/deuteranopia):** el deck depende del rojo para enfatizar. ¿Algún mensaje se pierde si el rojo se ve marrón/gris? (ej. mito-false tachado en rojo, accents). Proponer refuerzo no-cromático (negrita, tachado, ícono) donde haga falta.
- **Reportar:** tabla combinación → ratio estimado → veredicto AA/AAA → fix.

### (d) Layout, márgenes, espaciado, alineación, overflow, balance, aire
- **Overflow / corte de contenido** en slides densas: feature-cards (6), 4 features (17), fórmula (18), 5 cosas (31), tool-tiles (25), QR grid (32) — ¿entran sin scroll interno a `100dvh` con proyector 4:3 o pantalla baja (≤760/≤600px alto)?
- Balance y aire: ¿hay slides recargadas vs. vacías? ¿El `gap`/`slide-padding` da respiración suficiente para audiencia mayor?
- Alineación: el deck es todo centrado (`text-align:center`) — ¿algún bloque de texto largo (bios, answers) se leería mejor alineado a la izquierda?
- Imágenes: `max-height:min(50vh,420px)` — ¿la foto del ajedrez (8) y la demo (19) quedan suficientemente grandes para verse proyectadas?
- photo-fan (2): 4 fotos rotadas/solapadas — ¿se entiende o es ruido?
- **Reportar:** por slide, riesgo de overflow/desbalance + ajuste concreto (gap, min-height, max-height, columnas).

### (e) Consistencia visual
- **Mezcla emoji vs SVG:** slide 3 usa **emojis** (🚀📱💪) mientras TODO el resto usa SVG de línea rojos. ¿Rompe el sistema? Proponer unificar (SVG) o justificar la excepción.
- Estilo de ícono uniforme: ¿todos los SVG comparten grosor de trazo, esquinas, tamaño relativo? ¿El `.illust` vs `.illust.sm` se aplica con criterio?
- Componentes repetidos: ¿los tres "tipos demo" (casa/comunicado/io) usan el mismo patrón visual o divergen?
- Numeritos en círculo (secret-num, lunes num, r-num, age num): ¿mismo tratamiento (peso 900, color)?
- Tipos de slide bien asignados: ¿cada contenido está en la plantilla correcta (warm vs paper, emphasis vs content)?
- Tratamiento del `.accent` rojo en títulos: ¿coherente qué palabra se resalta? (que no haya slides sin accent donde correspondería, ni accents arbitrarios).
- **Reportar:** inconsistencias con slide(s) y norma a unificar.

### (f) Idea, narrativa, ritmo, storytelling, picos, CTA
- Validá (no copies) el diagnóstico de §1.8: ¿la tesis emocional llega tarde? ¿la meseta de mitos (9–14) y la cuádruple repetición (18–24) realmente matan el ritmo? ¿el doble cierre (34/37) + Q&A (36) serpentea?
- Picos emocionales: ¿están bien distribuidos? ¿falta el pico del "wow en vivo"?
- Claridad y unicidad del CTA: ¿el pedido de sumarse al grupo es inequívoco y aparece en el momento óptimo?
- Coherencia del hilo "irreemplazable + te potencia" de principio a fin.
- **Reportar:** mapa de ritmo (dónde sube/baja la energía), problemas de secuencia, y reordenamiento propuesto slide por slide.

### (g) Claridad para audiencia mayor no-técnica
- **Jerga:** marcar cualquier término que un bombero de 75 años no entienda sin explicación (¿"prompt", "contexto", "comando", "versiones gratis", nombres de productos?).
- Metáforas: ¿todas aterrizan en su mundo (autobomba, mandado, audio de WhatsApp, empleado nuevo, limpiar la casa, bibliotecario)? Marcar las que floten.
- **Números que confunden:** «1956», «1997», «70 años», «+350 clientes», «365 días» — ¿ayudan o saturan? ¿algún dato compite con otro?
- Densidad cognitiva por slide: ¿alguna pide procesar demasiado a la vez?
- Tono: cercano y **digno**, nunca condescendiente. Marcar cualquier frase que suene a "te explico porque sos viejo".
- **Reportar:** término/frase + por qué confunde + reescritura exacta más simple.

### (h) Slides FALTANTES y REDUNDANTES
- **Faltantes:** evaluá las 6 propuestas de §1.8 (empatía inicial, reframe orador, payoff en vivo, seguridad/privacidad, límite "qué NO reemplaza", prueba social local). Para cada una: ¿vale la pena? ¿dónde va exactamente (entre qué slides)? ¿boceto de contenido con copy real?
- **Redundantes:** evaluá las fusiones/cortes de §1.8. Para cada par: ¿cuál se queda, cuál se va, y por qué? Cuantificá el ahorro de slides.
- **Reportar:** decisión final (crear/fusionar/cortar) con ubicación y copy, y conteo neto de slides resultante.

### (i) Accesibilidad
- Confirmá lo que ya está bien (alt 14/14, focus visible, reduced-motion, roles nav) — **no lo des por sentado, verificá**.
- **Tamaño de QR proyectado:** ¿los QR (130–210px en grid, hasta 340px el del grupo) son escaneables a la distancia del aula? ¿conviene agrandar el del grupo, que es el CTA?
- **Tap targets:** nav-dots 9px < 44px. ¿importa si se navega solo con teclado/clicker? ¿reactivar las flechas (54–72px) como target accesible desperdiciado?
- Daltonismo (ver también (c)): redundancia no-cromática del énfasis.
- Foco y orden de tabulación; `aria-hidden` correcto en decorativos.
- **Reportar:** por ítem, estado (OK / a mejorar) + fix.

### (j) Assets y técnico
- **Placeholders / fotos faltantes:** `demo-prompt.jpg` y `demo-salida.jpg` (slide 19) — son el wow moment, hoy se ven como recuadros dashed. Prioridad de conseguir capturas reales.
- **QR real del grupo:** `qr-grupo.svg` es placeholder (comentario L1187). Bloqueante para el objetivo de retención. Regenerar + escanear los 4.
- **Sigla provisional:** «Bomberos PBA» (L1130) — confirmar nombre oficial del canal con la Federación.
- **Flechas/keyboard-hint muertos:** decidir eliminar JS+botones o reactivar.
- **Performance/peso:** medios ~2MB + logo PNG 384KB → webp / usar logo .jpg 46KB. Preload de Poppins 800/900. Subset con glifos español.
- **Export a PDF:** ¿la presentación exporta bien a PDF para quien la quiera imprimir/repartir? ¿los `100dvh`, gradientes y QR sobreviven? (verificar o recomendar prueba).
- **Assets no usados:** `logo-federacion.jpg`, `alan-tapia.jpg` (verificar y limpiar).
- **Conteo:** confirmar que 37 es el número deseado (BRIEF marcaba ~S28).
- **Reportar:** por ítem, estado + acción + si es bloqueante para el evento.

---

## 3. FORMATO DEL ENTREGABLE

Devolvé **exactamente** estas secciones, en este orden:

### 3.1 Puntaje por dimensión
Tabla con las 10 dimensiones (a–j), un **puntaje 0–10** cada una y **una línea de justificación**. Cerrá con un **promedio ponderado** (peso doble a: narrativa/ritmo (f), claridad para audiencia mayor (g), y assets/técnico bloqueante (j)).

| Dim | Dimensión | Puntaje /10 | Justificación (1 línea) |
|---|---|---|---|

### 3.2 Tabla de hallazgos priorizada
**Todos** los hallazgos, ordenados por prioridad. Prioridades: **🔴 Bloqueante** (rompe el evento / mata adopción), **🟠 Importante** (daña notablemente la experiencia), **🟡 Pulido** (mejora pero no urgente).

| Prioridad | Slide(s) | Dimensión | Problema | Fix concreto (copy/valor EXACTO propuesto) |
|---|---|---|---|---|

Regla: la columna Fix nunca dice "mejorar X" — dice el texto, el HEX, el `clamp()`, la clase o el reordenamiento exacto.

### 3.3 Slides nuevos propuestos
Por cada slide a crear: **Título** · **Dónde va** (entre slide N y N+1) · **Objetivo** · **Boceto de contenido con copy real** (eyebrow/título/cuerpo/nota listos para pegar) · **Tipo de plantilla** sugerido (content/warm/emphasis/block).

### 3.4 Top 5 si solo tengo tiempo para 5 cambios
Los 5 cambios de mayor impacto/esfuerzo, en orden. Cada uno: qué hacer (1 línea accionable) + por qué mueve la aguja para ESTA audiencia.

### 3.5 Veredicto final
- **¿Está lista para el evento? SÍ / NO / SÍ con condiciones.**
- **Qué bloquea** (lista de 🔴 que deben resolverse sí o sí antes del sábado).
- **Riesgo principal** en una frase.
- **Lo mejor del deck** que hay que proteger y no tocar.

---

## 4. REGLAS DEL AUDITOR (obligatorias)

1. **Citá SIEMPRE el número de slide** (y la clase/línea si la sabés). Nada de "en una slide del medio".
2. **Proponé copy y valores EXACTOS**, nunca vaguedades. En vez de "mejorar el contraste" → "cambiar `.title .accent` de `--red-600` a `--red-700` (#B91C1C)". En vez de "la bio es fría" → escribí la bio nueva, palabra por palabra.
3. **Respetá el tono:** cercano, digno, rioplatense, voseo. **PROHIBIDO** decir "pueblo", "fundador", o cualquier framing condescendiente. La IA es **inversión, no gasto**. **NUNCA** "veo todo / te vigila".
4. **Pensá en el bombero de 75 años, última fila del aula, sin internet, escéptico.** Cada recomendación se valida contra él.
5. **Señalá lo que YA está bien** — no solo lo malo. Protegé explícitamente las joyas (analogía WhatsApp, reveal del ajedrez, "mandado", caso plata del cuartel, "este lunes", "miles de años de experiencia") para que nadie las rompa al editar.
6. **Distinguí opinión de hecho:** si algo depende de verificar en vivo (escanear QR, ver la foto real, probar el PDF), decilo y marcalo como acción de verificación, no como hallazgo cerrado.
7. **No inventes contenido que contradiga la estrategia** (wedge financiero, retención por grupo, tesis de irreemplazabilidad). Construí sobre ella.
8. **Sé exhaustivo:** es mejor un hallazgo 🟡 de más que uno menos. Auditá las 37 slides, una por una, sin saltear ninguna.

---

**Empezá ahora. Auditá las 37 slides al detalle y entregá el plan de acción priorizado siguiendo el formato de la sección 3.**
