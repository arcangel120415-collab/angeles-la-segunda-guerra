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
