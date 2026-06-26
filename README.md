# invitacion-mijo-soficita 💌

Una mini web app interactiva con estética **nerd / geek** para invitar a
**Soficita** a una **cena** — escrita en español con humor de programador.

> _"Soficita, declaro un bug crítico: me he enamorado. El único fix conocido
> es una cena contigo."_

🚀 **Live demo** → [https://invitacion-mijo-soficita.vercel.app](https://invitacion-mijo-soficita.vercel.app)

---

## ✨ Qué tiene de especial

- **Un solo archivo `index.html`** — HTML + CSS + JS inline, cero build, cero dependencias npm.
- **Diseño _responsive_ mobile-first** — se ve bien en 375 px hasta desktop.
- **Modo oscuro / claro** con toggle animado sol/luna — variables CSS `oklch`.
- **Estrellas titilando** en el fondo, animadas puramente con CSS.
- **Botón "No, gracias"** que huye del cursor en escritorio y se teletransporta
  en móvil (con `@media (hover: none)`). Después de 3 intentos, se vuelve
  diminuto y desaparece en móvil.
- **Botón "Sí, acepto"** que pulsa con animación CSS y abre una pantalla de
  celebración con confeti (CSS puro) + botón "Compartir" que copia la URL.
- **Accesible**: `aria-label`s, touch targets ≥ 44 px, contraste WCAG AA,
  `prefers-reduced-motion` respetado, `<html lang="es">`.
- **Sin `localStorage`**: compatible con sandboxes y iframes restrictivos.

## 🛠 Stack

| Capa       | Tecnología                                 |
| ---------- | ------------------------------------------ |
| Markup     | HTML5                                      |
| Estilos    | CSS3 + variables `oklch` + `@keyframes`     |
| Tipografía | [Space Grotesk](https://fonts.google.com/specimen/Space+Grotesk) + [Inter](https://fonts.google.com/specimen/Inter) (Google Fonts) |
| Scripting  | Vanilla JS (sin frameworks, sin build)     |
| Hosting    | [Vercel](https://vercel.com) (static)      |

## 📁 Estructura

```
.
├── index.html   ← toda la app está aquí dentro
└── README.md
```

## 🚀 Deploy local

No necesita build. Para previsualizarla basta con servir el directorio:

```bash
# opción 1: python
python3 -m http.server 8080

# opción 2: node
npx serve .
```

Luego abre `http://localhost:8080`.

## ✏️ Personalizar

Abre `index.html` y edita:

1. **El mensaje** — busca `<h1>` en `<section class="invitation">`.
2. **El lugar / detalles** — el bloque `subtitle` debajo del `<h1>`.
3. **Los textos de celebración** — busca `<aside class="celebration">`.
4. **Colores** — bloque `:root[data-theme="dark"]` y `[data-theme="light"]`
   (paleta `oklch`).
5. **El countdown inicial** — variable `seconds = 99` en el `<script>`.

## 🧰 Detalles técnicos

- **Fluid type** con `clamp()` (`--fs-display`, `--fs-h2`, `--fs-body`).
- **Sistema de espaciado** en múltiplos de 4 px (`--space-1` … `--space-16`).
- **Detección móvil** vía `@media (hover: none)` para diferenciar `mouseover`
  de `touchstart`.
- **Conteo regresivo cosmético**: llega a 0 y muestra `0` sin redirigir.
- **Persistencia de tema**: solo en el `<html data-theme="…">` actual, no en
  `localStorage` (cumple requisito de sandbox).

## 📜 Licencia

MIT — úsala, modifícala, hazla tuya. Solo no la uses para acosar a nadie. 💚

---

_Hecho con cariño (y algo de azúcar sintáctica) por **Mijo**._