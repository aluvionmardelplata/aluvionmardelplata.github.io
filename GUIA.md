# Cómo publicar el sitio y subir textos

## 1. Publicarlo por primera vez (una sola vez)

1. Creá una cuenta de GitHub para Aluvión (no personal), por ejemplo `aluvion-mdp`. Sumá como administradora a una segunda persona del grupo.
2. Creá un repositorio nuevo, público, llamado **`aluvion-mdp.github.io`** (el nombre de la cuenta + `.github.io`). Así la dirección queda `https://aluvion-mdp.github.io` y no hay que tocar nada más.
   - Si preferís otro nombre de repositorio (por ejemplo `escritos`), la dirección será `https://aluvion-mdp.github.io/escritos` y tenés que poner `baseurl: "/escritos"` en `_config.yml`.
3. En el repositorio: **Add file → Upload files**, y arrastrá **todo el contenido** de esta carpeta (no la carpeta en sí: tienen que quedar `_config.yml`, `_posts`, `_layouts`, etc. en la raíz). Confirmá con **Commit changes**.
4. Andá a **Settings → Pages** y en *Source* elegí **Deploy from a branch**, rama `main`, carpeta `/ (root)`. Guardá.
5. Esperá uno o dos minutos. La dirección aparece arriba en esa misma pantalla.

No hay que instalar nada: GitHub arma el sitio solo cada vez que cambia un archivo.

## 2. La fuente Sun Zoom Spark

Ya está incluida en `assets/fonts/SunZoomSpark.woff2` y se usa en todos los títulos. No hay que tocar nada.

## 3. Subir un texto nuevo

1. Entrá a la carpeta `_posts` del repositorio y tocá **Add file → Create new file**.
2. El nombre del archivo tiene que ser: `AAAA-MM-DD-titulo-corto.md`
   Ejemplo: `2026-11-20-soberania-alimentaria.md`. Sin tildes, sin espacios, en minúscula.
3. Pegá arriba de todo este encabezado y completalo:

   ```
   ---
   title: "Título del texto"
   bajada: "Subtítulo opcional (si no hay, borrá esta línea)"
   categoria: "Historia y filosofía"
   ---
   ```

4. Debajo pegá el texto. Reglas mínimas:
   - Una línea en blanco entre párrafos.
   - Subtítulo de sección: `## Subtítulo`
   - Cita larga: empezá el párrafo con `> `
   - Cursiva: `*palabra*` · Negrita: `**palabra**`
5. **Commit changes**. En un par de minutos aparece en el sitio, ordenado por fecha.

### Categorías

Cada texto lleva una sola categoría en la línea `categoria:`. Escribila siempre igual, con las mismas mayúsculas y tildes: "Historia y filosofía" y "Historia y Filosofía" serían dos categorías distintas. Si escribís una nueva (por ejemplo `categoria: "Salud"`), aparece sola en la página de Categorías y en la barra lateral.

## Imágenes entre párrafos

1. Achicá la imagen antes de subirla: con 1200 px de ancho alcanza, en JPG. Más grande hace lenta la página.
2. Subila a la carpeta `assets/img/textos/` (Add file → Upload files). Nombre sin tildes ni espacios, por ejemplo `plaza-1945.jpg`.
3. En el texto, en el lugar donde va, dejá una línea en blanco arriba y abajo y pegá:

   ```
   {% include imagen.html archivo="plaza-1945.jpg" epigrafe="Plaza de Mayo, 17 de octubre de 1945." %}
   ```

   - `archivo`: el nombre exacto del archivo que subiste.
   - `epigrafe`: el texto que va debajo de la foto. Es opcional; si no lo querés, borrá esa parte entera.
   - Si la imagen no tiene epígrafe, agregá `descripcion="..."` contando qué se ve, para quien lee con lector de pantalla.

En el texto del 17 de octubre hay un ejemplo armado con la pieza gráfica del espacio; podés copiarlo o borrarlo.

Si la imagen no es de ustedes, poné el crédito en el epígrafe.

Si el texto está en Word o PDF y no querés convertirlo a mano, pasáselo a Claude y pedile el archivo `.md` listo.

## Comentarios

Usamos Cusdis: quien lee puede comentar sin registrarse y nada se publica hasta que ustedes lo aprueban. El plan gratuito alcanza para un sitio con hasta 100 comentarios aprobados por mes.

Para activarlo (una sola vez):

1. Entrá a cusdis.com y creá una cuenta para Aluvión.
2. Tocá **New website**, ponele "Aluvión" y entrá a sus ajustes (**Embed code**). Copiá el valor que aparece en `data-app-id` (una tira larga de letras y números).
3. En el repositorio abrí `_config.yml` y pegalo entre las comillas de `cusdis_app_id:`. **Commit changes**.
4. En los ajustes de Cusdis activá las notificaciones por correo para enterarse cuando llega un comentario nuevo.

Para moderar: cada comentario llega al panel de Cusdis (y al correo, si lo activaron) y ahí se aprueba o se borra. Se puede responder desde el mismo panel.

Para sacar los comentarios de un texto puntual, agregá `comentarios: false` en su encabezado.

## 4. Corregir o borrar un texto

Abrí el archivo en `_posts`, tocá el lápiz para editar, y **Commit changes**. Para borrarlo, menú `···` → **Delete file**.

## 5. Cambiar textos fijos

- Presentación de "Sobre Aluvión": `sobre.md`
- Frase de portada y párrafo de introducción: `index.html`
- Texto corto de la barra lateral: `_includes/lateral.html`
- Ciudad del pie de página: `lugar:` en `_config.yml`
- Redes: `redes:` en `_config.yml` (solo el nombre de usuario). Si borrás una línea, ese enlace desaparece del sitio.
