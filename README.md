# PLAN-DE-CALIBRACIÓN
Mantener el orden de los equipos e instrumentos activos dentro de la planta, estar pendiente de aquellos equipos/instrumentos que requieran servicios de calibración y tener el control de fechas preventivas y reales para estas calibraciones.

## Página web

`index.html` es un dashboard estático (sin backend) con el listado de los 318 equipos e instrumentos de planta, generado a partir de `Listado de Equipos e instrumentos_Plan de calibración.xlsx` (hoja "LISTADO DE EQUIPOS"). Los datos viven en `data.js`.

Incluye:
- Tarjetas resumen (total, vigentes, próximos a vencer en 30 días, vencidos, no calibrados, no aplica).
- Búsqueda por ID, nombre, marca, modelo, serie o ubicación.
- Filtros por área, criticidad, clasificación y estado de calibración.
- Tabla ordenable con próxima calibración preventiva/real, proveedor y certificado.

Para publicarla: activar **GitHub Pages** en Settings → Pages, rama `main`, carpeta `/ (root)`.

Para actualizar los datos: reemplazar el .xlsx y regenerar `data.js` a partir de la hoja "LISTADO DE EQUIPOS" (columnas A–O, encabezados en la fila 8).
