# Plan de mantenimiento del universo web

## Regla principal
No renombrar ni borrar IDs de escenas. Cada clip, aunque cambie de video de YouTube, mantiene su `id` interno.

## Reemplazar un video publicado
1. Identificar el `id` de escena.
2. Cambiar solo `video`, `thumbnail` y, si hace falta, `descripcion`.
3. No tocar `orden`, `capitulo` ni `titulo` salvo que cambie la narrativa.
4. Probar localmente y luego publicar.

## Agregar un clip nuevo de una parte anterior
1. Crear una nueva escena con `id` único.
2. Asignar `orden` decimal o intermedio si va entre dos escenas existentes. Ejemplo: `orden: 2.5`.
3. Definir si es `escena`, `apendice`, `historieta` o `expansion`.
4. Vincularlo con el texto literal si existe, o marcarlo como expansión cinematográfica.

## Historieta
La historieta debe vivir en `assets/historieta/` y en un futuro archivo de datos separado, por ejemplo `data/historieta.json`, para no mezclar páginas de cómic con clips de video.

## Publicación
Primero se publica una versión estable. Luego cada cambio debe salir como versión nueva: v21, v22, v23, etc.


## Feedback de lectores

El widget flotante registra interacciones simples en Google Analytics: like_historia, dislike_historia, click_sugerencia, click_youtube_canal, unlock_attempt y unlock_success. Para cambiar la palabra semanal, editar ACCESS_CODE en script.js.

## v29 - Ajustes aplicados

- Botón flotante **Sugerencia** conectado al Google Form:
  https://docs.google.com/forms/d/e/1FAIpQLScy1i3MNMXtK9IlvR3hvCsLNIQb5Znpp0OoFuU4b7bfX7A_Jg/viewform?usp=publish-editor
- Tarjeta de **Madre de Teles / Reina del Mar** marcada como oculta hasta que tenga video propio.
- Ajustes responsive para que los botones no corten texto en móvil.

## v30 - Clip 25 agregado

- Se agregó **Ángeles: La Segunda Guerra – Clip 25 | La promesa de Azazel** al **Apéndice Azazel**, después de “El duelo y la ciudadela errante”.
- Link usado:
  https://youtube.com/shorts/q-otPuQbkH4?feature=share
- El “CONTINUARÁ” quedó ahora al final del Clip 25 para que el apéndice avance de forma natural.

## Pendiente para la siguiente tanda

- Revisar en GitHub Pages que la miniatura del Clip 25 cargue correctamente. Si YouTube no entrega `maxresdefault.jpg`, cambiarla por `hqdefault.jpg`.
- Cuando la Reina del Mar tenga video propio, quitar la marca de personaje oculto en `data/personajes.json`.


## v31 - Corrección puntual
- Se eliminó temporalmente la ficha `madre-teles` del JSON visible para que no se renderice la tarjeta de Madre de Teles/Reina del Mar.
- El botón Sugerencia ahora es un enlace directo al Google Form desde el HTML, sin depender del modal ni de JavaScript.
- Se agregó cache busting `?v=31` a `style.css` y `script.js` para evitar que GitHub Pages o el navegador sigan mostrando la versión anterior.
