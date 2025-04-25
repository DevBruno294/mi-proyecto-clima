# Corrección de Mala Práctica - ClimApp

## 1. Mala práctica identificada: **Enlace incorrecto al archivo CSS**

### ¿Qué identificamos?
- En el archivo `index.html`, la etiqueta `<link>` para cargar los estilos CSS no apunta al archivo correcto
- El código actual intenta cargar estilos desde una URL externa (CDN) en lugar de nuestro archivo local `index.css`
- Esto provoca que la página se muestre sin estilos personalizados

### ¿Por qué es una mala práctica?
- **Problema de funcionalidad**: La página no se visualiza como fue diseñada
- **Dependencia innecesaria**: Usar un CDN para estilos locales añade carga externa innecesaria
- **Mantenimiento difícil**: Los cambios en `index.css` no se reflejan porque no está siendo cargado
- **Rendimiento afectado**: Se fuerza al navegador a hacer una solicitud HTTP adicional fallida

### ¿Cómo lo solucionamos?
1. Reemplazamos el enlace incorrecto:
   <!-- Enlace INCORRECTO original -->
   <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/leaflet/1.9.4/leaflet.min.css" />
   
   <!-- Enlace CORREGIDO -->
   <link rel="stylesheet" href="index.css" />

   Beneficios de la solución:
La página ahora muestra todos los estilos diseñados
Eliminamos dependencia externa innecesaria
Los cambios en CSS se reflejan inmediatamente
Mejor rendimiento al cargar solo lo necesario
Mantenimiento más sencillo del código