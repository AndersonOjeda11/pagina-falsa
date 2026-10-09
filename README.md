# Demo educativa: página de error 404

Demo educativa de una interfaz de error 404 genérica. No es una página oficial de Vercel ni informa el estado real de otro proyecto.

## Despliegue en Vercel

Al desplegar como sitio estático en Vercel, `public/404.html` se incluye en el directorio de salida como página personalizada para rutas que no existen. Vercel puede responder esas solicitudes con el estado HTTP `404` y mostrar este contenido, sin redirigir a `/error`.

La portada `/` sirve la aplicación Angular y responde `200`; el estado `404` corresponde a una ruta inexistente. No agregues una regla de reescritura global a `index.html`, porque haría que las rutas desconocidas se sirvan como la SPA.

Configura Vercel para construir con `npm run build` y usar `dist/pagina-error/browser` como directorio de salida. Después del despliegue puedes comprobar el estado de una ruta inexistente con:

```bash
curl -I https://TU-DOMINIO/ruta-que-no-existe
```

La respuesta esperada es `404 Not Found`.

## Requisitos

- Node.js compatible con la versión de Angular CLI del proyecto
- npm

## Desarrollo local

```bash
npm install
npm start
```

Abre `http://localhost:4200/` en el navegador. Para generar la compilación de producción:

```bash
npm run build
```

El mensaje de la aplicación Angular está en `src/app/app.html`; la página estática personalizada de Vercel está en `public/404.html`. El favicon neutro está en `public/favicon.svg`.
