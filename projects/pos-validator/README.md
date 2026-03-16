# POS Validator

Herramienta de validacion y auditoria de configuraciones de tiendas MAXPOINT contra una base de datos centralizada en Azure SQL Server.

## Problema que resuelve

Cuando se configura un nuevo restaurante en el sistema POS, hay decenas de entidades que deben estar correctamente registradas: datos del restaurante, estaciones, impresoras, menus, productos, formas de pago, descuentos, promociones, usuarios, secuencias de facturacion, entre otros. Validar todo esto manualmente es lento y propenso a errores.

POS Validator automatiza esta auditoria, mostrando en segundos el estado completo de cada modulo con porcentaje de completitud.

## Funcionalidades

- **Validacion de tienda**: Selecciona cadena y restaurante, obtiene un reporte completo con 13 modulos validados
- **Comparacion entre tiendas**: Compara configuracion de dos restaurantes lado a lado, detectando diferencias
- **Verificacion local vs Azure**: Compara la base de datos local del POS contra la centralizada en Azure
- **Drill-down por modulo**: Navega por entidades y colecciones dentro de cada modulo para ver el detalle exacto
- **Indicadores de estado**: OK (>=95%), PARTIAL (>0%), MISSING (0%), ERROR - con colores y porcentajes
- **Progreso ponderado**: Cada modulo tiene peso segun su importancia operativa

## Modulos validados

Restaurant, Estacion, Impresora, Menu, Producto, Formas de Pago, Descuento, Promocion, Pisos y Mesas, Usuarios, Secuencia de Facturacion, Medio de Venta, Replicacion.

## Arquitectura

```
Frontend (React 18 + Vite)
    |
    | HTTP / JSON
    v
Backend (Python 3.11 + FastAPI)
    |
    | PyODBC
    v
Azure SQL Server (MAXPOINT)
    + SQL Server local (Switch - TIDs)
```

- **Backend**: FastAPI con patron EAV (Entity-Attribute-Value) para consultas genericas. Dos queries batch por modulo.
- **Frontend**: React con useState puro, sin librerias de estado. Tema oscuro con acentos cyan.
- **Deploy**: Docker Compose con Nginx como reverse proxy.

## Stack

| Componente | Tecnologia |
|------------|-----------|
| Backend | Python 3.11, FastAPI, PyODBC |
| Frontend | React 18, Vite, CSS Grid |
| Base de datos | SQL Server (Azure + local) |
| Infraestructura | Docker Compose, Nginx |
