# 🎵 Prisma reproductor (v1.0)

[![Versión](https://img.shields.io/badge/versión-1.0-blue.svg)](https://prisma.ankel05.site)
[![Licencia](https://img.shields.io/badge/licencia-MIT-green.svg)](LICENSE)

**Prisma (v1.0)** es un reproductor de música **local** pensado para pantalla completa y modo horizontal. Funciona como aplicación web instalable (PWA): tu música nunca sale de tu dispositivo.

👉 **[Abrir Prisma en vivo (prisma.ankel05.site)](https://prisma.ankel05.site)**

<!-- Agrega una captura en docs/screenshot.png -->
<!-- ![Captura del reproductor](docs/screenshot.png) -->

> **Nota:** Las canciones, artistas y carátulas mostrados en las capturas de pantalla tienen fines meramente ilustrativos y demostrativos. Prisma no incluye, no almacena ni distribuye ningún tipo de música o contenido multimedia; todos los archivos reproducidos son locales y pertenecen al usuario.

## Características de la versión 1.0

- **Tu música, tus carpetas:** da acceso a una carpeta y la app la recorre con todas sus subcarpetas.
- **Biblioteca por artista y álbum**, con búsqueda. Cada artista y álbum tiene botones de *Reproducir* y *Mezclar*.
- **Cola bajo demanda:** empieza vacía y solo se crea cuando eliges un álbum, una canción o una mezcla.
- **Portada protagonista** y diseño *glass* con reflejos, fondo en movimiento y grano, cuyos colores salen de la portada de cada canción.
- **Letras** sincronizadas (`.lrc`) o incrustadas en las etiquetas.
- **Pantalla completa** sin distracciones, orientación horizontal y pantalla siempre encendida mientras suena.
- **Controles del sistema** (pantalla de bloqueo, teclas multimedia) mediante Media Session.
- **Funciona sin conexión** una vez instalada.

## Formatos y etiquetas

| Formato | Título / artista / álbum | Portada | Letra |
|---|---|---|---|
| MP3 (ID3v2.3/2.4) | ✅ | ✅ | ✅ |
| FLAC | ✅ | ✅ | ✅ |
| M4A / AAC (MP4) | ✅ | ✅ | ✅ |
| OGG, OPUS, WAV | Solo nombre del archivo | Carátula de carpeta | `.lrc` |

- Si un archivo no trae portada, se usa una imagen de su carpeta (`cover.jpg`, `folder.jpg`, `front.jpg`, `album.png`…).
- Si no hay etiquetas, el artista y el álbum se deducen de la estructura `Artista/Álbum/canción` o del nombre `Artista - Título`.
- Para letras sincronizadas guarda un `.lrc` con el mismo nombre que el audio.

## Uso e instalación

Puedes usar Prisma directamente desde el navegador: **[prisma.ankel05.site](https://prisma.ankel05.site)**.

### Instalar como aplicación (PWA)

Para la mejor experiencia (modo inmersivo a pantalla completa y funcionamiento sin conexión):

- **Chrome / Edge (escritorio y Android):** pulsa en el icono de instalación de la barra de direcciones o ve al menú (⋮) → *Instalar app*.
- **iPhone / iPad (Safari):** toca el botón *Compartir* → *Añadir a pantalla de inicio*.

### Despliegue propio (GitHub Pages)

Si quieres alojar tu propia copia independiente:

1. Sube `index.html`, `manifest.webmanifest`, `sw.js`, `icon-192.png` e `icon-512.png` a la raíz de tu repositorio.
2. En **Settings → Pages**, elige *Deploy from a branch* → `main` → `/ (root)`.
3. Abre la URL generada por GitHub Pages (debe ser HTTPS para que el navegador permita acceder a carpetas).

## Compatibilidad

| Navegador | Carpetas con memoria | Selector de carpeta o archivos | Pantalla completa |
|---|---|---|---|
| Chrome / Edge (escritorio) | ✅ | ✅ | ✅ |
| Chrome (Android) | Según versión | ✅ | ✅ |
| Firefox / Safari | ❌ | ✅ (no se recuerda al cerrar) | Firefox ✅ · iPhone: instalar la app |

Cuando el navegador no permite guardar el acceso a carpetas, tendrás que volver a elegir tu música en cada sesión. En Chrome y Edge, si el permiso caduca aparece el botón **Reconectar biblioteca**.

## Atajos de teclado

| Tecla | Acción |
|---|---|
| `Espacio` | Reproducir / pausar |
| `←` `→` | Retroceder / avanzar 5 s |
| `N` / `P` | Siguiente / anterior |
| `F` | Pantalla completa |
| `L` | Letras |
| `Esc` | Cerrar ventana |

## Estructura del proyecto

```
index.html            App completa (HTML, CSS y JS en un solo archivo)
manifest.webmanifest  Datos de instalación (pantalla completa, horizontal)
sw.js                 Service worker: caché para uso sin conexión
icon-192.png / icon-512.png
```

Sin dependencias externas ni proceso de compilación. La única petición externa es la fuente tipográfica de iconos *Material Symbols Rounded* (almacenada en caché tras la primera carga).

## Privacidad y aviso legal

- **Sin servidores:** No hay servidores, cuentas ni analíticas. Los archivos se leen localmente en tu navegador y nunca se suben a ningún sitio. Solo se guardan en el dispositivo el acceso a las carpetas (IndexedDB) y tus preferencias de reproducción.
- **Sin distribución de contenido:** Prisma es únicamente una herramienta de software para reproducir archivos locales. No provee, hospeda ni distribuye pistas de audio, álbumes ni ningún material sujeto a derechos de autor. Cada usuario gestiona exclusivamente sus propios archivos.

## Próximamente (Roadmap)

- Soporte de etiquetas y portada en archivos OGG/OPUS.
- Control de volumen integrado, temporizador de apagado y lista de favoritos.

## Licencia

Este proyecto está bajo la Licencia [MIT](LICENSE).