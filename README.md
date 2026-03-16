# Jorge Castro - Portfolio de Proyectos

Profesional con 12 anos de experiencia en operaciones y tecnologia, especializado en el analisis del core de negocio y el desarrollo de soluciones tecnologicas para optimizar procesos operativos. Experiencia en automatizacion, analisis de datos, implementacion de herramientas basadas en IA y desarrollo de aplicaciones internas orientadas a mejorar la eficiencia operativa.

Los proyectos presentados aqui son herramientas que he desarrollado para resolver necesidades reales de operacion en cadenas de restaurantes, integrando sistemas POS, bases de datos corporativas y flujos de trabajo del dia a dia.

---

## Proyectos

### 1. Catalogo de Productos MAXPOINT
**Plataforma full-stack para gestion y consulta visual del catalogo de productos MAXPOINT.**

Aplicacion completa con API REST y frontend interactivo que permite explorar productos por cadena, con filtrado jerarquico en cascada (clasificacion, menu, categoria de precio, categoria de boton), busqueda con debounce, imagenes con zoom, comparacion de menus entre tiendas, sincronizacion a tienda de pruebas y exportacion a Excel. Incluye autenticacion JWT y panel de administracion.

`React` `Vite` `Tailwind CSS` `Node.js` `Express` `SQL Server` `JWT` `ExcelJS` `Docker` `Kubernetes`

[Ver detalle del proyecto](projects/catalogo-productos-maxpoint/)

---

### 2. Catalogo Productos MXP2
**Comparador de menus entre BackOffice (UAT) y POS (Produccion).**

Sistema que permite navegar la jerarquia de menus (Menu > Categoria > Producto) y comparar campo a campo las diferencias entre lo configurado en BackOffice y lo desplegado en POS, detectando PLUs no asignados y discrepancias de sincronizacion.

`React` `TypeScript` `FastAPI` `MongoDB` `Vite` `Docker`

[Ver detalle del proyecto](projects/catalogo-productos-mxp2/)

---

### 3. POS Validator
**Validador de configuraciones de tiendas MAXPOINT contra base de datos centralizada.**

Herramienta que audita la configuracion de restaurantes, estaciones, impresoras, menus, formas de pago y usuarios, detectando entidades faltantes o incompletas. Incluye modo de comparacion entre tiendas y verificacion de sincronizacion con base de datos local.

`Python` `FastAPI` `React` `SQL Server` `Docker`

[Ver detalle del proyecto](projects/pos-validator/)

---

### 4. Reporte de Ventas (Produccion)
**Dashboard de reportes y analitica de ventas para cadenas de restaurantes.**

Panel interactivo que consulta ordenes de venta, muestra productos vendidos por fecha con metricas financieras (costos, margenes, mix de ventas), metodos de pago, notas de credito y cierres diarios. Incluye sistema de alertas automaticas via Telegram para deteccion de anomalias.

`React` `Node.js` `Express` `MongoDB` `Chart.js` `Docker`

[Ver detalle del proyecto](projects/reporte-ventas/)

---

### 5. Reporte de Ventas UAT
**Version UAT/Staging del dashboard de ventas para pruebas y validacion.**

Ambiente de pruebas del sistema de reportes de ventas, conectado a bases de datos UAT independientes. Permite validar nuevas funcionalidades y consultas antes de desplegarlas en produccion, garantizando la estabilidad del sistema productivo.

`React` `Node.js` `Express` `MongoDB` `Chart.js` `Docker`

[Ver detalle del proyecto](projects/reporte-ventas-uat/)

---

### 6. QA Task Manager
**Plataforma de gestion de tareas con panel integrado de pruebas QA.**

Aplicacion de tareas con dashboard de estadisticas y un panel de testing que ejecuta pruebas de carga (50 usuarios concurrentes), estres (1000 tareas en lote), validacion de API REST, rendimiento y deteccion de vulnerabilidades XSS.

`Node.js` `Express` `HTML/CSS` `Docker`

[Ver detalle del proyecto](projects/qa-task-manager/)

---

## Stack Tecnologico

| Area | Tecnologias |
|------|-------------|
| **Backend** | Python, FastAPI, Node.js, Express |
| **Frontend** | React, TypeScript, Vite, Tailwind CSS, Chart.js |
| **Bases de Datos** | SQL Server (Azure), MongoDB (Atlas) |
| **Autenticacion** | JWT |
| **Infraestructura** | Docker, Docker Compose, Nginx, Kubernetes (AKS) |
| **CI/CD** | Azure DevOps |
| **Integraciones** | Telegram Bot API, ExcelJS, PDFKit |
| **Herramientas** | Git, VS Code, Azure Data Studio |

---

## Contacto

- **GitHub:** [Jorginvil](https://github.com/Jorginvil)
