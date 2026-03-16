# QA Task Manager

Plataforma de gestion de tareas con panel integrado de pruebas de calidad (QA).

## Problema que resuelve

Proyecto desarrollado como parte de un curso de QA con IA. Combina una aplicacion funcional de tareas con un panel completo de pruebas automatizadas, demostrando diferentes tipos de testing sobre una API REST real.

## Funcionalidades

### Gestion de Tareas
- Crear, editar y eliminar tareas
- Filtrar por estado, prioridad y categoria
- Dashboard con estadisticas en tiempo real
- Interfaz con modo oscuro y efectos glassmorphism

### Panel de Pruebas QA
6 tipos de pruebas con resultados visuales en tiempo real:

| Prueba | Descripcion |
|--------|------------|
| **Carga** | 50 usuarios concurrentes, 10 peticiones cada uno. Mide req/segundo y tasa de exito |
| **Estres** | Crea 1000 tareas en lotes para evaluar capacidad bajo volumen extremo |
| **API** | Valida todos los endpoints REST (GET, POST, PUT, DELETE) con codigos HTTP |
| **Rendimiento** | 20 iteraciones midiendo tiempos de respuesta (promedio, min, max) |
| **Validacion** | Casos edge: titulos vacios, caracteres especiales, XSS |
| **Integracion** | Flujos completos CRUD de principio a fin |

## Arquitectura

```
Frontend (HTML/CSS/JS)
    |
    | HTTP / JSON
    v
Backend (Node.js + Express)
    |
    | In-memory
    v
Array de tareas (runtime)
```

Aplicacion monolitica con servidor Express que sirve el frontend y expone la API REST. Almacenamiento en memoria para simplicidad.

## Stack

| Componente | Tecnologia |
|------------|-----------|
| Backend | Node.js, Express |
| Frontend | HTML5, CSS3, JavaScript vanilla |
| Testing | Panel QA custom (carga, estres, API, rendimiento) |
| Infraestructura | Docker |
