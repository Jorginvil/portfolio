# API Catalogo BackOffice MXPv2

API REST para gestion y consulta del catalogo de productos del sistema BackOffice MXPv2.

## Problema que resuelve

Multiples herramientas internas necesitan acceder al catalogo de productos: el navegador de imagenes, el comparador de menus, reportes. Esta API centraliza el acceso a los datos del catalogo con filtros avanzados y exportacion, evitando consultas SQL directas desde cada aplicacion.

## Funcionalidades

- **Consulta de productos**: Por cadena con filtros avanzados (clasificacion, menu, categoria)
- **Filtros dinamicos en cascada**: Los filtros se ajustan segun la seleccion previa
- **Preguntas sugeridas**: Consulta de preguntas frecuentes asociadas a cada producto
- **Exportacion Excel**: Generacion de catalogos en Excel con formato personalizado, estilos y cabeceras
- **Health check**: Endpoint de monitoreo para verificar estado del servicio y conexion a BD
- **Manejo de errores centralizado**: Middleware de errores con respuestas consistentes
- **Pool de conexiones**: Conexiones optimizadas a SQL Server

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
Clientes (Frontend, otras APIs)
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
| Runtime | Node.js |
| Framework | Express |
| Base de datos | SQL Server (Azure), mssql driver |
| Exportacion | ExcelJS |
| Infraestructura | Docker, CORS |
