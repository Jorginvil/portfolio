# Reporte de Ventas UAT

Ambiente de pruebas (UAT/Staging) del dashboard de ventas, conectado a bases de datos independientes para validacion previa a produccion.

## Problema que resuelve

Antes de desplegar cambios en el dashboard de ventas productivo, es necesario validar que las nuevas consultas, filtros y visualizaciones funcionan correctamente con datos reales pero en un ambiente aislado. Este proyecto es el entorno UAT que garantiza la estabilidad del sistema productivo.

## Funcionalidades

- **Dashboard de ventas**: Visualizacion de ventas diarias con graficas por hora
- **Productos por fecha**: Consulta detallada de productos vendidos con metricas financieras
- **Metodos de pago**: Desglose por forma de pago con conteo de transacciones
- **Notas de credito**: Seguimiento de notas de credito emitidas
- **Cierre diario**: Conciliacion financiera de fin de dia
- **Filtros de transacciones**: Por estado, estado SRI, cajero
- **Exportacion Excel**: Descarga de reportes con formato profesional

## Diferencias con Produccion

| Aspecto | UAT | Produccion |
|---------|-----|-----------|
| Base de datos | Cluster QA (UAT_KFC_POS_*) | Cluster PRD (POS_PurchaseOrders) |
| Alertas Telegram | No incluidas | Si, cada 5 minutos |
| Puertos | Backend 3009, Frontend 3010 | Backend 3007, Frontend 3008 |
| Proposito | Validacion y pruebas | Operacion diaria |

## Arquitectura

```
Frontend (React 18 + Chart.js)
    |
    | HTTP / JSON
    v
Backend (Node.js + Express)
    |
    | Mongoose
    v
MongoDB Atlas (Cluster QA)
  - UAT_KFC_POS_*
  - UAT_MXPi_Pub_Sale
```

## Stack

| Componente | Tecnologia |
|------------|-----------|
| Backend | Node.js, Express, Mongoose |
| Frontend | React 18, Chart.js, Axios |
| Base de datos | MongoDB Atlas (cluster QA) |
| Exportacion | ExcelJS |
| Infraestructura | Docker Compose, Nginx |
