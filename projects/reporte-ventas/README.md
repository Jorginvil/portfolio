# Reporte de Ventas

Dashboard de reportes y analitica de ventas para cadenas de restaurantes, con sistema de alertas automaticas.

## Problema que resuelve

El equipo de operaciones necesita visibilidad diaria sobre las ventas: que productos se vendieron, con que metodo de pago, margenes de ganancia, mix de ventas y anomalias. Esta herramienta centraliza toda esa informacion en un panel interactivo, reemplazando reportes manuales en Excel.

## Funcionalidades

- **Productos por fecha**: Consulta de productos vendidos con 11 columnas de detalle (cantidad, costo, precio, margen, mix %, contribucion %)
- **Metodos de pago**: Desglose por forma de pago con conteo de transacciones
- **Notas de credito**: Seguimiento detallado de notas de credito emitidas
- **Cierre diario**: Conciliacion financiera de fin de dia
- **Alertas Telegram**: Sistema automatizado que cada 5 minutos revisa anomalias y envia notificaciones al equipo via Telegram
- **Exportacion Excel**: Descarga de reportes con formato profesional
- **Multi-ambiente**: Configuraciones para DEV, UAT, QA y Produccion

## Arquitectura

```
Frontend (React 18)
    |
    | HTTP / JSON
    v
Backend (Node.js + Express)
    |
    | Mongoose
    v
MongoDB (Ordenes POS)
    +
Telegram Bot API (Alertas)
```

- **Backend**: Express con cron jobs para monitoreo automatico. Endpoints REST para cada tipo de reporte.
- **Frontend**: React con Chart.js para graficas interactivas.
- **Deploy**: Docker Compose con Nginx.

## Stack

| Componente | Tecnologia |
|------------|-----------|
| Backend | Node.js, Express, Mongoose, node-cron |
| Frontend | React 18, Chart.js, Axios |
| Base de datos | MongoDB |
| Integraciones | Telegram Bot API, ExcelJS |
| Infraestructura | Docker Compose, Nginx |
