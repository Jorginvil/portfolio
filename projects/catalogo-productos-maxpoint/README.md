# Catalogo de Productos MAXPOINT

Plataforma full-stack para gestion, consulta y visualizacion del catalogo de productos del sistema POS MAXPOINT.

## Problema que resuelve

El equipo de operaciones, marketing y soporte necesita consultar rapidamente el catalogo de productos: ver imagenes, precios, clasificaciones, menus asignados y comparar configuraciones entre tiendas. Antes esto requeria consultas SQL manuales. Esta plataforma centraliza todo en una interfaz visual con filtros intuitivos, administracion y exportacion.

## Funcionalidades

### API Backend
- **Consulta de productos**: Por cadena con filtros avanzados (clasificacion, menu, categoria de precio, categoria de boton)
- **Filtros dinamicos en cascada**: Los filtros se ajustan automaticamente segun la seleccion previa
- **Preguntas sugeridas**: Consulta de preguntas frecuentes asociadas a cada producto por clasificacion
- **Exportacion Excel**: Generacion de catalogos en Excel con formato personalizado, estilos y cabeceras
- **Autenticacion JWT**: Login con control de acceso por perfil (Admin)
- **Documentacion API**: Docs interactivos con Scalar (OpenAPI/Swagger)
- **Health check**: Monitoreo de estado del servicio y conexion a BD
- **Pool de conexiones**: Conexiones optimizadas a SQL Server

### Frontend
- **Navegacion por cadena**: Selector de cadena con carga dinamica de productos
- **Filtrado jerarquico**: Clasificacion > Menu > Categoria de precio > Categoria de boton
- **Busqueda con debounce**: Busqueda en tiempo real (350ms) con cache
- **Imagenes con zoom**: Vista previa de imagenes de producto con modal de zoom
- **Comparacion de menus**: Compara menus entre dos tiendas lado a lado
- **Sincronizacion a tienda de pruebas**: Sincroniza productos a tienda de test (admin)
- **Bandas de precios**: Visor de bandas de precios y ubicaciones por banda
- **Ubicacion de productos**: Consulta en que tiendas esta asignado cada producto
- **Cache inteligente**: Cache de 5 minutos en el cliente para consultas repetidas

## Endpoints principales

```
POST /api/login                        - Autenticacion
GET  /api/health                       - Estado del servicio
GET  /api/filtros                      - Filtros dinamicos por cadena
GET  /api/productos                    - Productos con filtros
GET  /api/preguntas-sugeridas/:plu_id  - Preguntas sugeridas
POST /api/descargar-excel              - Exportacion a Excel
GET  /api/docs                         - Documentacion interactiva
```

## Arquitectura

```
Frontend (React 18 + Vite + Tailwind CSS)
    |
    | HTTP / JSON + JWT
    v
API (Node.js + Express)
    |
    | mssql (pool, 10 conexiones)
    v
SQL Server (Azure)
```

- **Backend**: Express con autenticacion JWT, pool de conexiones y documentacion OpenAPI.
- **Frontend**: React con Tailwind CSS, sistema de diseno MAXPOINT (rojo #E4002B), modales con blur backdrop.
- **Deploy**: Docker Compose en desarrollo, Kubernetes (AKS) + Azure DevOps CI/CD en produccion.

## Stack

| Componente | Tecnologia |
|------------|-----------|
| Backend | Node.js, Express, mssql, JWT |
| Frontend | React 18, Vite, Tailwind CSS |
| Base de datos | SQL Server (Azure) |
| Exportacion | ExcelJS |
| Documentacion | Scalar (OpenAPI) |
| Infraestructura | Docker Compose, Kubernetes (AKS), Nginx |
| CI/CD | Azure DevOps |
