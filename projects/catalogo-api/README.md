# Catalogo de Productos - API y Navegador Visual

API REST y frontend interactivo para gestion, consulta y visualizacion del catalogo de productos BackOffice MXPv2.

## Problema que resuelve

El equipo de operaciones y marketing necesita consultar rapidamente el catalogo de productos: ver imagenes, precios, clasificaciones y menus asignados. Antes esto requeria consultas SQL manuales. Este proyecto centraliza el acceso con una API robusta y un frontend visual con filtros intuitivos. Evoluciono desde un visor de imagenes PLU hasta una solucion completa con API, filtros en cascada y exportacion.

## Funcionalidades

### API Backend
- **Consulta de productos**: Por cadena con filtros avanzados (clasificacion, menu, categoria)
- **Filtros dinamicos en cascada**: Los filtros se ajustan segun la seleccion previa
- **Preguntas sugeridas**: Consulta de preguntas frecuentes asociadas a cada producto
- **Exportacion Excel**: Generacion de catalogos en Excel con formato personalizado, estilos y cabeceras
- **Health check**: Endpoint de monitoreo para verificar estado del servicio y conexion a BD
- **Pool de conexiones**: Conexiones optimizadas a SQL Server

### Frontend Visual
- **Navegacion por cadena**: Selector de cadena con carga dinamica de productos
- **Filtrado jerarquico**: Clasificacion > Menu > Categoria de precio > Categoria de boton
- **Busqueda con debounce**: Busqueda en tiempo real sin sobrecargar el servidor
- **Imagenes con zoom**: Vista previa de imagenes de producto con modal de zoom
- **Cache inteligente**: Cache de 5 minutos en el cliente para consultas repetidas

## Endpoints principales

```
GET  /api/health              - Estado del servicio
GET  /api/cadenas             - Lista de cadenas disponibles
GET  /api/productos           - Productos con filtros
GET  /api/filtros             - Filtros dinamicos
GET  /api/preguntas/:id       - Preguntas sugeridas por producto
GET  /api/export/excel        - Exportacion a Excel
```

## Arquitectura

```
Frontend (React 18 + Vite + Tailwind)
    |
    | HTTP / JSON
    v
API (Node.js + Express)
    |
    | mssql (pool)
    v
SQL Server (Azure)
```

## Stack

| Componente | Tecnologia |
|------------|-----------|
| Backend | Node.js, Express, mssql |
| Frontend | React 18, Vite, Tailwind CSS |
| Base de datos | SQL Server (Azure) |
| Exportacion | ExcelJS, PDFKit |
| Infraestructura | Docker Compose, Nginx |
