# Portafolio — Fernando Acuña

Portafolio personal de un solo archivo. Desarrollador de software full-stack, Ciudad de México.

**En vivo:** https://facu100201.github.io/Portfolio/

## Qué hay aquí

| Archivo | Qué es |
|---|---|
| `index.html` | El sitio completo: HTML, CSS y JS en un solo archivo, con las tipografías y sin dependencias externas |
| `perfil.jpg` | Retrato recortado (400×500) |
| `CV_FernandoAcuna_ESP.pdf` | CV en PDF, enlazado desde el sitio |
| `fotoperfilCV.jpeg` | Foto original sin recortar (fuente) |
| `.nojekyll` | Le dice a GitHub Pages que sirva los archivos tal cual, sin procesarlos con Jekyll |

## Decisiones técnicas

- **Cero peticiones externas.** Las tipografías (Archivo y Martian Mono) van incrustadas como data URI. Es obligatorio: el navegador bloquea las fuentes por CORS cuando el archivo se abre con doble clic sobre `file://`.
- **Subset de fuentes.** Reducidas a los 122 caracteres que la página usa y a instancias estáticas de peso 400 y 600: 57 KB → 30 KB.
- **`content-visibility: auto`** en las secciones bajo el pliegue, para que no se maqueten hasta acercarse al viewport.
- **`prefers-reduced-motion`.** Cuando está activo no se engancha ningún listener de scroll; el hilo principal queda libre.
- **Temas claro y oscuro** vía tokens CSS, con los tres estados: preferencia del sistema y elección explícita en ambos sentidos.

Medido sin throttling: FCP 376 ms, 418 nodos, 77 KB transferidos con gzip.

## Publicar los cambios

El sitio se sirve desde la raíz de la rama `main`.

```bash
git add -A
git commit -m "Actualiza el portafolio"
git push
```

GitHub Pages redespliega solo en un par de minutos.

## Si cambias el nombre del repositorio

Hay 6 URLs absolutas apuntando a `https://facu100201.github.io/Portfolio/` dentro de `index.html`
(canonical, `og:url`, `og:image`, `twitter:image` y dos en el JSON-LD).
Búscalas y ajústalas, o los previews en redes y el SEO apuntarán a la dirección equivocada.
