# Jorge Castro - Portfolio de Proyectos

Profesional con 12 anos de experiencia en operaciones y tecnologia, especializado en el analisis del core de negocio y el desarrollo de soluciones tecnologicas para optimizar procesos operativos. Experiencia en automatizacion, analisis de datos, implementacion de herramientas basadas en IA y desarrollo de aplicaciones internas orientadas a mejorar la eficiencia operativa.

Los proyectos presentados aqui son herramientas que he desarrollado para resolver necesidades reales de operacion en cadenas de restaurantes, integrando sistemas POS, bases de datos corporativas y flujos de trabajo del dia a dia.

---

## Proyectos

### 1. POS Validator
**Validador de configuraciones de tiendas MAXPOINT contra base de datos centralizada.**

Herramienta que audita la configuracion de restaurantes, estaciones, impresoras, menus, formas de pago y usuarios, detectando entidades faltantes o incompletas. Incluye modo de comparacion entre tiendas y verificacion de sincronizacion con base de datos local.

`Python` `FastAPI` `React` `SQL Server` `Docker`

[Ver detalle del proyecto](projects/pos-validator/)

---

### 2. Reporte de Ventas
**Dashboard de reportes y analitica de ventas para cadenas de restaurantes.**

Panel interactivo que consulta ordenes de venta, muestra productos vendidos por fecha con metricas financieras (costos, margenes, mix de ventas), metodos de pago, notas de credito y cierres diarios. Incluye sistema de alertas automaticas via Telegram para deteccion de anomalias.

`React` `Node.js` `Express` `MongoDB` `Chart.js` `Docker`

[Ver detalle del proyecto](projects/reporte-ventas/)

---

### 3. Catalogo de Productos - Imagen PLU
**Navegador visual de catalogo de productos con imagenes y filtros avanzados.**

Aplicacion que permite explorar el catalogo de productos MAXPOINT por cadena, con filtrado jerarquico (clasificacion, menu, categoria de precio, categoria de boton), busqueda con debounce, zoom de imagenes y exportacion a Excel.

`React` `Vite` `Tailwind CSS` `Node.js` `Express` `SQL Server` `Docker`

[Ver detalle del proyecto](projects/imagen-plu/)

---

### 4. API Catalogo BackOffice
**API REST para gestion y consulta del catalogo de productos BackOffice MXPv2.**

Servicio backend que expone endpoints para consulta de productos por cadena, filtros dinamicos en cascada, preguntas sugeridas por producto y exportacion de catalogos a Excel con formato personalizado.

`Node.js` `Express` `SQL Server` `ExcelJS` `Docker`

[Ver detalle del proyecto](projects/catalogo-api/)

---

### 5. Catalogo Productos MXP2
**Comparador de menus entre BackOffice (UAT) y POS (Produccion).**

Sistema que permite navegar la jerarquia de menus (Menu > Categoria > Producto) y comparar campo a campo las diferencias entre lo configurado en BackOffice y lo desplegado en POS, detectando PLUs no asignados y discrepancias de sincronizacion.

`React` `TypeScript` `FastAPI` `MongoDB` `Vite` `Docker`

[Ver detalle del proyecto](projects/catalogo-productos/)

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
| **Infraestructura** | Docker, Docker Compose, Nginx |
| **Integraciones** | Telegram Bot API, ExcelJS, PDFKit |
| **Herramientas** | Git, VS Code, Azure Data Studio |

---

## Contacto

- **GitHub:** [Jorginvil](https://github.com/Jorginvil)
