# PLAN-DE-CALIBRACIÓN
Mantener el orden de los equipos e instrumentos activos dentro de la planta, estar pendiente de aquellos equipos/instrumentos que requieran servicios de calibración y tener el control de fechas preventivas y reales para estas calibraciones.

## Página web

`index.html` es un dashboard de una sola página (datos embebidos, sin backend propio) con el listado de los 318 equipos e instrumentos de planta, generado a partir de `Listado de Equipos e instrumentos_Plan de calibración.xlsx` (hoja "LISTADO DE EQUIPOS").

Incluye:
- Acceso protegido por usuario/contraseña (cortina simple del lado del cliente, no es seguridad real).
- KPIs: cumplimiento de calibración, equipos críticos en riesgo, cobertura de datos, categorías con más pendientes.
- Equipos agrupados por tipo en desplegables (con semáforo de estados por categoría).
- Búsqueda (sin distinguir tildes), filtros por área/criticidad/clasificación/estado.
- **Edición en línea**: botón "✎ Editar" en cada fila para modificar cualquier dato (marca, modelo, serie, área, ubicación, criticidad, clasificación, fechas, proveedor, certificado, categoría). El estado de calibración se recalcula automáticamente al guardar.

### Persistencia de las ediciones

- **Versión publicada como Artifact de Claude** (`claude.ai/code/artifact/...`): los cambios se guardan de verdad y quedan visibles para cualquiera que abra ese link, usando la capacidad `artifact` de Claude (la página se re-publica a sí misma).
- **Versión en GitHub Pages** (sitio estático puro, sin esa capacidad): los cambios se guardan solo en `localStorage` del navegador de quien edita — no se sincronizan con GitHub ni con otros dispositivos/usuarios.

Para publicarla en GitHub Pages: activar **Settings → Pages**, rama `main`, carpeta `/ (root)`.

Para regenerar el archivo desde el Excel: usar el script de build (arma `index.html` combinando la plantilla con los datos del .xlsx, columnas A–O de "LISTADO DE EQUIPOS", encabezados en la fila 8).
