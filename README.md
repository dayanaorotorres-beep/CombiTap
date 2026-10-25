# RutaTap — Tapachula (PWA de prueba)

Aplicación web instalable en iPhone con mapa interactivo, marcadores azul/rojo arrastrables, GPS con autorización, seguimiento mientras Safari está activo, modo claro/oscuro/automático, distancias y tiempos **aproximados** en cinco modos, y catálogo de 43 denominaciones aportadas por la usuaria.

## Publicación sin programar en GitHub
1. Crea cuenta en https://github.com y entra en https://github.com/new.
2. Nombre del repositorio: `rutatap`; visibilidad **Public**; crea el repositorio.
3. Pulsa **Add file → Upload files** y sube **el contenido descomprimido** de este ZIP, manteniendo `index.html`, `manifest.webmanifest`, `sw.js`, `README.md`, y las carpetas `assets` y `data` en la raíz. No subas el ZIP como único archivo ni metas todo dentro de una carpeta extra.
4. Confirma los cambios con **Commit changes**.
5. En **Settings → Pages**, selecciona **Deploy from a branch**, rama `main`, carpeta `/(root)` y **Save**.
6. Espera a que GitHub publique. Entra en `https://TU_USUARIO.github.io/rutatap/` (sustituye TU_USUARIO). La primera publicación puede tardar varios minutos.
7. En iPhone abre ese enlace con **Safari**, pulsa **Compartir → Añadir a pantalla de inicio → Añadir**. Abre RutaTap desde el icono.
8. Permite el acceso a la ubicación si deseas utilizar el GPS. Para probar el recorrido, toca **Inicio**, selecciona punto en mapa, toca **Destino**, selecciona otro punto y pulsa **Calcular recorrido**.

## Qué funciona y qué NO
- El mapa requiere internet. El modo offline **no** descarga mapas; el service worker solo almacena la interfaz y el catálogo una vez visitados.
- El catálogo de 43 nombres no contiene geometrías GPS, paradas, tarifas u horarios verificados. **No calcula qué combi tomar**.
- La API pública de demostración OSRM devuelve recorridos viales de automóvil, incluso cuando se selecciona miniván, caminata o bicicleta; NO es un motor de transporte colectivo. Si falla, se muestra distancia en línea recta, no una ruta transitable.
- El tiempo estimado se calcula con velocidades orientativas, no tráfico real ni esperas. No debe usarse como indicación fiable para un viaje.
- El GPS requiere HTTPS y permiso; el seguimiento se limita al uso activo de la web. No se garantiza en segundo plano con el iPhone bloqueado.
- GitHub Pages sirve para **probar la demostración**; no lo uses como hosting de un SaaS comercial ni dependas del servicio OSRM de prueba para producción.
- Los iconos PNG se basan en las imágenes proporcionadas por la usuaria. Antes de uso comercial verifica derechos de reproducción de esos diseños; para producción conviene crear iconos originales.

## Siguientes pasos para producto real
Verificar las 43 rutas, dibujar recorridos y sentidos en GeoJSON/GTFS, paradas con coordenadas, tarifas y frecuencia, motor de transporte público, proveedor de rutas y mapas con condiciones adecuadas, política de privacidad, pruebas iOS y accesibilidad.
