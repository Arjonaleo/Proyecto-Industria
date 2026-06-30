# SGA - Sistema de Gestión de Almacén

Sistema web y móvil para gestionar operaciones de recepción, almacenamiento,
ubicación, inventario, surtido y distribución de productos promocionales
para **ZPremia / Grupo Zeta**.

Desarrollado por **ORPEL** | Global University - Taller de Proyecto
Orientado a la Industria y Seguridad

---

## Estado Actual

**Fase activa:** F1–F2 - Inicio, Planificación y Análisis  
**Semana:** 3 de 30 · Junio 2026  
**Próximo hito:** Requerimientos aprobados (sem. 5)

---

## Stack Tecnológico

| Capa          | Tecnología                              |
|---------------|-----------------------------------------|
| Backend       | Java 17 + Spring Boot 3                 |
| Frontend      | Angular 17                              |
| Base de datos | SQL Server 2017 Standard Edition        |
| Mobile        | Android Java - Honeywell EDA60K / EDA51 |
| Servidor      | Windows Server + IIS 8+                 |
| Red           | LAN / WLAN IEEE 802.11 a/b/g/n/ac       |

---

## Módulos del Sistema

### Web
- **Catálogos** - Empresas, Almacenes, Racks, Pasillos, Productos, Proveedores, Clientes, Usuarios y más
- **Recibo** - Importación de Packing List, recibo sin inspección, asignación de ubicaciones
- **Inventarios** - Entradas, salidas, ajustes e inventario físico
- **Traspasos** - Orden de surtido, traspaso de envío y recepción
- **Reportes** - Recepción, inventario, histórico, cortesías, incidencias
- **Seguridad** - Gestión de usuarios y perfiles
- **Parámetros** - Configuración del sistema y notificaciones

### Mobile (Android - Honeywell)
Inspección · Entradas · Salidas · Ubicaciones · Traspaso de envío · Traspaso de recepción

---


## Cronograma

30 semanas - Junio a Diciembre 2026 - Metodología Cascada

| Fase    | Semanas | Descripción                   |
|---------|---------|-------------------------------|
| F1      | 1–2     | Inicio y Planificación        |
| F2      | 2–6     | Análisis y Especificación     |
| F3      | 3–8     | Arquitectura y Diseño         |
| F4      | 8–9     | Configuración de Ambientes    |
| F5–F7   | 10–21   | Desarrollo Backend + IZeta    |
| F8      | 11–19   | Desarrollo Frontend Web       |
| F9      | 15–21   | App Mobile Android            |
| F10–F11 | 12–26   | Pruebas QA + UAT              |
| F12     | 26–28   | Despliegue y Puesta en Marcha |
| F13–F14 | 28–30   | Estabilización y Cierre       |

Ver cronograma completo → [`docs/01-gestion/cronograma/`](docs/01-gestion/cronograma/)

---

## Estructura del Repositorio

```
Proyecto-Industria/
├── docs/
│   ├── 01-gestion/       # Planificación, actas, Gantt, riesgos
│   ├── 02-analisis/      # ERS, casos de uso, reglas de negocio
│   ├── 03-disenio/       # Arquitectura, BD, APIs, UX-UI
│   ├── 04-configuracion/ # Setup de ambientes Dev/QA/UAT
│   ├── 05-qa/            # Plan de pruebas, casos, reportes, UAT
│   └── 06-despliegue/    # Manuales, plan de despliegue, cierre
├── backend/              # Java Spring Boot
├── frontend/             # Angular
├── mobile/               # Android (Honeywell EDA60K / EDA51)
└── database/             # SQL Server - diseño, migraciones, seeds
```

---

## Prerrequisitos de Desarrollo

> Documentación de setup en construcción - ver [F4 Configuración de Ambientes](docs/04-configuracion/) al completarse la fase de diseño (sem. 8–9).

---

## Documentación

- [ERS_01 - Especificación de Requerimientos](docs/02-analisis/ERS_01.pdf)
- [Planificación ORPEL](docs/01-gestion/planificacion-orpel.pdf)
- [Cronograma Gantt](docs/01-gestion/cronograma/gantt_cronograma_sga.html)
- [Guía de contribución](CONTRIBUTING.md)

---

## Restricciones Clave

- SGA **no modifica** la BD de IZeta - integración solo lectura vía APIs
- App mobile **no opera offline**
- Hardware fijo: Honeywell EDA60K, EDA51, impresora PC42T (ZPL-II)
- Infraestructura **on-premise** (sin cloud)
