# TusInvitados.ar — sitio estático

Landing page en una sola página, preparada para GitHub Pages.

## Estructura
- `index.html` — toda la página, estilos y JavaScript.
- `assets/logo.svg` — logo editable en SVG.
- `assets/favicon.svg` — favicon.
- `assets/invitation-1.svg` a `invitation-6.svg` — imágenes de ejemplo del carrusel.

## Publicar en GitHub Pages
1. Subí todos los archivos manteniendo la carpeta `assets`.
2. En GitHub: **Settings → Pages**.
3. Elegí **Deploy from a branch**.
4. Seleccioná `main` y `/ (root)`.
5. Guardá y esperá la publicación.

## Próximos pasos recomendados
La versión entregada es una **demo frontend funcional**. El registro/login, creación con IA, contacto y donaciones todavía necesitan un servicio de backend.

### Login / registro
Recomiendo **Supabase Auth** para:
- registro por email/contraseña;
- login;
- recuperación de contraseña;
- guardar las invitaciones de cada usuario;
- almacenar datos de la invitación.

### Contacto
Podés conectar el formulario a Formspree, Netlify Forms o una función serverless.

### Donaciones
Reemplazá la función `donate()` del `index.html` por el link real de Mercado Pago, Cafecito o el medio que elijas.

### IA
El botón “Crear mi invitación” está preparado para llevar al generador. La llamada a un modelo de IA debe hacerse desde un backend/serverless, no exponiendo una API key directamente en `index.html`.

## Dominio
Cuando GitHub Pages esté funcionando, podés apuntar `tusinvitados.ar` a GitHub Pages mediante DNS. También conviene activar HTTPS.


## Modelo del proyecto

TusInvitados.ar está planteado como un proyecto gratuito sostenido por colaboraciones voluntarias. No se cobra por crear ni compartir invitaciones. La colaboración sirve para ayudar a cubrir infraestructura, almacenamiento y servicios de IA.

## Arquitectura prevista

- GitHub: repositorios y control de versiones.
- Cloudflare: dominio, CDN/hosting y Worker de enrutamiento.
- Supabase: autenticación, base de datos y almacenamiento.
- IA: generación de la estructura y personalización de invitaciones.

El Worker existente puede continuar ocultando/enrutando el repositorio real sin cambiar la URL pública `tusinvitados.ar`.
