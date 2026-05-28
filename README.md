# docsify-local-cdn

Lokalny CDN z zasobami (CSS/JS) używanymi przez projekty `*-guide`, pozwalający pracować offline.

## Uruchomienie lokalnego serwera

```bash
# konwersja do PDF
npx docsify-pdf-converter

# uruchomienie serwera (port 3002)
npx docsify serve .
npx serve .
npx http-server -c-1 .
npx browser-sync start --server --no-ui --no-open --directory --serveStatic .
```

## Podmiana ścieżek w `index.html`

W każdym projekcie `*-guide` zamień ścieżki CDN na lokalne:

| CDN                          | Local                                          |
| ---------------------------- | ---------------------------------------------- |
| `//unpkg.com/...`            | `//localhost:3002/...`                         |
| `//cdn.jsdelivr.net/npm/...` | `//localhost:3002/...` (patrz mapowania niżej) |

### Style

```html
<link rel="stylesheet" href="//localhost:3002/docsify/lib/themes/vue.css" />
<link
  rel="stylesheet"
  href="//localhost:3002/docsify-dark-mode-toggle/index.css"
/>
<link
  rel="stylesheet"
  href="//localhost:3002/docsify-sidebar-collapse/dist/sidebar.min.css"
/>
```

### Skrypty

```html
<script src="//localhost:3002/docsify/lib/docsify.min.js"></script>
<script src="//localhost:3002/docsify/lib/plugins/search.min.js"></script>
<script src="//localhost:3002/docsify/lib/plugins/emoji.min.js"></script>
<script src="//localhost:3002/docsify/lib/plugins/zoom-image.min.js"></script>
<script src="//localhost:3002/docsify-copy-code/dist/docsify-copy-code.min.js"></script>
<script src="//localhost:3002/docsify-updated/src/time-updater.js"></script>
<script src="//localhost:3002/docsify-pagination/dist/docsify-pagination.min.js"></script>
<script src="//localhost:3002/docsify-dark-mode-toggle/index.js"></script>
<script src="//localhost:3002/docsify-sidebar-scroll-to-active/index.js"></script>
<script src="//localhost:3002/docsify-sidebar-collapse/dist/docsify-sidebar-collapse.min.js"></script>
<script src="//localhost:3002/docsify-latex/dist/docsify-latex.js"></script>
<script src="//localhost:3002/mathjax/es5/tex-mml-chtml.js"></script>
<script src="//localhost:3002/prismjs/components/prism-json.min.js"></script>
<script src="//localhost:3002/prismjs/components/prism-bash.min.js"></script>
<script src="//localhost:3002/prismjs/components/prism-typescript.min.js"></script>
<script src="//localhost:3002/prismjs/components/prism-jsx.min.js"></script>
<script src="//localhost:3002/prismjs/components/prism-diff.min.js"></script>
```

## Mapowania CDN → local

### unpkg.com

| Z                                                               | Na                                                                   |
| --------------------------------------------------------------- | -------------------------------------------------------------------- |
| `//unpkg.com/docsify/lib/themes/vue.css`                        | `//localhost:3002/docsify/lib/themes/vue.css`                        |
| `//unpkg.com/docsify/lib/docsify.min.js`                        | `//localhost:3002/docsify/lib/docsify.min.js`                        |
| `//unpkg.com/docsify/lib/plugins/search.min.js`                 | `//localhost:3002/docsify/lib/plugins/search.min.js`                 |
| `//unpkg.com/docsify/lib/plugins/emoji.min.js`                  | `//localhost:3002/docsify/lib/plugins/emoji.min.js`                  |
| `//unpkg.com/docsify/lib/plugins/zoom-image.min.js`             | `//localhost:3002/docsify/lib/plugins/zoom-image.min.js`             |
| `//unpkg.com/docsify-copy-code`                                 | `//localhost:3002/docsify-copy-code/dist/docsify-copy-code.min.js`   |
| `//unpkg.com/docsify-copy-code/dist/docsify-copy-code.min.js`   | `//localhost:3002/docsify-copy-code/dist/docsify-copy-code.min.js`   |
| `//unpkg.com/docsify-updated`                                   | `//localhost:3002/docsify-updated/src/time-updater.js`               |
| `//unpkg.com/docsify-updated/src/time-updater.js`               | `//localhost:3002/docsify-updated/src/time-updater.js`               |
| `//unpkg.com/docsify-pagination/dist/docsify-pagination.min.js` | `//localhost:3002/docsify-pagination/dist/docsify-pagination.min.js` |
| `//unpkg.com/docsify-dark-mode-toggle/index.css`                | `//localhost:3002/docsify-dark-mode-toggle/index.css`                |
| `//unpkg.com/docsify-dark-mode-toggle/index.js`                 | `//localhost:3002/docsify-dark-mode-toggle/index.js`                 |
| `//unpkg.com/docsify-sidebar-scroll-to-active/index.js`         | `//localhost:3002/docsify-sidebar-scroll-to-active/index.js`         |
| `//unpkg.com/prismjs/components/prism-json.min.js`              | `//localhost:3002/prismjs/components/prism-json.min.js`              |
| `//unpkg.com/prismjs/components/prism-bash.min.js`              | `//localhost:3002/prismjs/components/prism-bash.min.js`              |
| `//unpkg.com/prismjs/components/prism-typescript.min.js`        | `//localhost:3002/prismjs/components/prism-typescript.min.js`        |
| `//unpkg.com/prismjs/components/prism-jsx.min.js`               | `//localhost:3002/prismjs/components/prism-jsx.min.js`               |
| `//unpkg.com/prismjs/components/prism-diff.min.js`              | `//localhost:3002/prismjs/components/prism-diff.min.js`              |

### cdn.jsdelivr.net

| Z                                                                                      | Na                                                                               |
| -------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------- |
| `//cdn.jsdelivr.net/npm/docsify-sidebar-collapse/dist/docsify-sidebar-collapse.min.js` | `//localhost:3002/docsify-sidebar-collapse/dist/docsify-sidebar-collapse.min.js` |
| `//cdn.jsdelivr.net/npm/docsify-sidebar-collapse/dist/sidebar.min.css`                 | `//localhost:3002/docsify-sidebar-collapse/dist/sidebar.min.css`                 |
| `//cdn.jsdelivr.net/npm/docsify-latex@0`                                               | `//localhost:3002/docsify-latex/dist/docsify-latex.js`                           |
| `//cdn.jsdelivr.net/npm/mathjax@3/es5/tex-mml-chtml.js`                                | `//localhost:3002/mathjax/es5/tex-mml-chtml.js`                                  |

## Aktualizacja zasobów

```bash
# proste pliki – pojedyncze curl-e
curl -fLo docsify-dark-mode-toggle/index.css       https://unpkg.com/docsify-dark-mode-toggle/index.css
curl -fLo docsify-dark-mode-toggle/index.js        https://unpkg.com/docsify-dark-mode-toggle/index.js
curl -fLo docsify-sidebar-scroll-to-active/index.js https://unpkg.com/docsify-sidebar-scroll-to-active/index.js
curl -fLo docsify-sidebar-collapse/dist/docsify-sidebar-collapse.min.js https://cdn.jsdelivr.net/npm/docsify-sidebar-collapse/dist/docsify-sidebar-collapse.min.js
curl -fLo docsify-sidebar-collapse/dist/sidebar.min.css                 https://cdn.jsdelivr.net/npm/docsify-sidebar-collapse/dist/sidebar.min.css
curl -fLo docsify-latex/dist/docsify-latex.js      https://cdn.jsdelivr.net/npm/docsify-latex@0/dist/docsify-latex.js
curl -fLo prismjs/components/prism-diff.min.js     https://unpkg.com/prismjs/components/prism-diff.min.js
curl -fLo prismjs/components/prism-jsx.min.js      https://unpkg.com/prismjs/components/prism-jsx.min.js

# mathjax – cały es5/ (23 MB), bo tex-mml-chtml.js doładowuje fonty i komponenty
mkdir -p tmp && cd tmp && npm pack mathjax@3 && tar -xzf mathjax-*.tgz \
  && rm -rf ../mathjax/es5 && cp -R package/es5 ../mathjax/ && cd .. && rm -rf tmp
```
