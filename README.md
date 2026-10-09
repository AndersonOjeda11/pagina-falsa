# Demo educativa: página de error 404

Demo educativa de una interfaz de error 404 genérica. No es una página oficial de Vercel ni informa el estado real de otro proyecto.

## Despliegue en Vercel

Al desplegar como sitio estático en Vercel, `public/404.html` se incluye en el directorio de salida. `vercel.json` hace que tanto la portada `/` como las rutas inexistentes muestren esta página con estado HTTP `404`, sin redirigir a `/error`.

Los archivos existentes (JavaScript, CSS e imágenes) continúan respondiendo `200`. Esta demo marca la portada `/` como `404` intencionalmente; no es el comportamiento habitual de una página de inicio. La configuración usa una regla de enrutamiento de Vercel para responder con el código `404` real.

Configura Vercel para construir con `npm run build` y usar `dist/pagina-error/browser` como directorio de salida. Después del despliegue puedes comprobar el estado de una ruta inexistente con:

```bash
curl -I https://TU-DOMINIO/ruta-que-no-existe
```

También puedes probar la portada con `curl -I https://TU-DOMINIO/`. Ambas solicitudes deben responder `404 Not Found`; los recursos estáticos existentes deben responder `200 OK`.

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
