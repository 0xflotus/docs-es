# Exportando

## PDF

> La exportación a PDF o PNG se basa en [Playwright](https://playwright.dev) para la renderización. Por lo tanto, tendras que instalar [`playwright-chromium`](https://playwright.dev/docs/installation#download-single-browser-binary) para utilizar esta función.
> Si estás haciendo la exportación en un entorno CI, [la guía CI de playwright](https://playwright.dev/docs/ci) puede ser útil.

Instala `playwright-chromium`

```bash
$ npm i -D playwright-chromium
```

Ahora exporta sus diapositivas a PDF utilizando el siguiente comando:

```bash
$ slidev export
```

Después de unos segundos, tus diapositivas estarán listas en `./slides-exports.pdf`.

## PNGs

Al pasar la opción `--format png`, Slidev exportará imágenes PNG para cada diapositiva en lugar de un PDF.

```bash
$ slidev export --format png
```

## Single-Page Application (SPA)

También puedes compilar las diapositivas en un SPA auto-alojable:

```bash
$ slidev build
```

La aplicación generada estará disponible en `dist/` y luego puedes alojarla en [GitHub Pages](https://pages.github.com/), [Netlify](https://netlify.app/), [Vercel](https://vercel.com/), o lo que quieras. Ahora puedes compartir tus diapositivas con el resto del mundo con un solo enlace.

### Ruta base

Para desplegar sus diapositivas bajo sub-rutas, necesitarás pasar la opción `--base`. Por ejemplo:

```bash
$ slidev build --base /talks/my-cool-talk/
```

Revisa la [documentación de Vite](https://vitejs.dev/guide/build.html#public-base-path) para más detalles.

### Proporcionar un PDF descargable

Puedes proporcionar un PDF descargable a los espectadores de su SPA. Puedes habilitarlo mediante la siguiente configuración:

```md
---
download: true
---
```

Ahora, Slidev generará un archivo pdf junto con la construcción y un botón de descarga aparecerá en el SPA.

También puede proporcionar una url personalizada para el PDF. En ese caso, se omitirá el proceso de renderización.

```md
---
download: 'https://myside.com/my-talk.pdf'
---
```

### Ejemplos

A continuación se muestran algunos ejemplos de la SPA exportada:

- [Starter Template](https://sli.dev/demo/starter)
- [Composable Vue](https://talks.antfu.me/2021/composable-vue) by [Anthony Fu](https://github.com/antfu)
