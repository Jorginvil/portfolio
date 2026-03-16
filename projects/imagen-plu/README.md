# Catalogo de Productos - Imagen PLU

Navegador visual del catalogo de productos MAXPOINT con imagenes, filtros avanzados y exportacion.

## Problema que resuelve

El equipo de operaciones y marketing necesita consultar rapidamente el catalogo de productos: ver imagenes, precios, clasificaciones y menus asignados. Antes esto requeria consultas SQL manuales. Esta herramienta lo convierte en una interfaz visual con filtros intuitivos.

## Funcionalidades

- **Navegacion por cadena**: Selector de cadena con carga dinamica de productos
- **Filtrado jerarquico**: Clasificacion > Menu > Categoria de precio > Categoria de boton (filtros en cascada)
- **Busqueda con debounce**: Busqueda en tiempo real sin sobrecargar el servidor
- **Imagenes con zoom**: Vista previa de imagenes de producto con modal de zoom
- **Exportacion Excel**: Descarga del catalogo filtrado con formato y estilos personalizados
- **Preguntas sugeridas**: Modal con preguntas frecuentes asociadas a cada producto
- **Cache inteligente**: Cache de 5 minutos en el cliente para consultas repetidas

## Arquitectura

```
Frontend (React 18 + Vite + Tailwind)
    |
    | HTTP / JSON
    v
Backend (Node.js + Express)
    |
    | mssql driver
    v
Azure SQL Server (MAXPOINT)
```

- **Backend**: Express con pool de conexiones a SQL Server. Endpoints para productos, filtros y exportacion.
- **Frontend**: React con Tailwind CSS, filtros persistentes y reset inteligente al cambiar cadena.
- **Deploy**: Docker Compose.

## Stack

| Componente | Tecnologia |
|------------|-----------|
| Backend | Node.js, Express, mssql |
| Frontend | React 18, Vite, Tailwind CSS |
| Base de datos | SQL Server (Azure) |
| Exportacion | ExcelJS, PDFKit |
| Infraestructura | Docker Compose, Nginx |
