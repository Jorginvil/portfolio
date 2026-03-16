# Catalogo Productos MXP2

Comparador de menus entre BackOffice (UAT) y POS (Produccion) para validar la sincronizacion de productos.

## Problema que resuelve

Cuando el equipo de BackOffice configura menus y productos en el ambiente UAT, estos deben sincronizarse correctamente a Produccion (POS). Detectar discrepancias manualmente entre ambos ambientes es impractico cuando hay cientos de productos. Esta herramienta automatiza la comparacion campo a campo.

## Funcionalidades

- **Navegacion dual**: Toggle entre vista POS (produccion) y BO (UAT)
- **Jerarquia de menus**: Menu > Categoria > Productos (PLUs) con paginacion
- **Comparacion campo a campo**: Diff visual entre version POS y BO de cada producto (estado, tipo, departamentos, impuestos, clasificaciones, imagenes)
- **Deteccion de PLUs no asignados**: Identifica productos que existen en BO pero no estan asignados en POS
- **Busqueda avanzada**: Filtros por nombre, estado, tipo y categoria con soporte regex
- **Paginacion configurable**: 20 items por pagina, configurable hasta 100

## Arquitectura

```
Frontend (React 18 + TypeScript + Vite)
    |
    | HTTP / JSON
    v
Backend (Python + FastAPI async)
    |
    | Motor (async MongoDB driver)
    v
MongoDB Atlas
  - UAT: UAT_KFC_POS_Menus
  - PRD: POS_Menus + BO_Menus
```

- **Backend**: FastAPI async con Motor (driver asincrono de MongoDB). Serializa ObjectIds, Decimal128 y datetimes.
- **Frontend**: React con TypeScript, navegacion por tabs sin libreria de routing.
- **Deploy**: Docker Compose con health checks.

## Stack

| Componente | Tecnologia |
|------------|-----------|
| Backend | Python, FastAPI, Motor, Pydantic |
| Frontend | React 18, TypeScript, Vite |
| Base de datos | MongoDB Atlas (dual: UAT + PRD) |
| Infraestructura | Docker Compose, Nginx |
