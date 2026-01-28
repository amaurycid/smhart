# Plan Maestro de Desarrollo y Migración: SMHART GESTIÓN MÉDICA

Este documento detalla la estrategia de transformación digital para la plataforma de gestión oftalmológica, migrando de un entorno legado hacia una arquitectura moderna, escalable y en la nube.

## 1. Análisis del Estado Legado (Legacy)

El sistema actual presenta cuellos de botella técnicos que limitan la escalabilidad y la seguridad:

- **Tecnología Obsoleta:** Uso de IIS y Microsoft Active Server Pages (ASP), lo que dificulta el mantenimiento y la búsqueda de talento especializado.
- **Base de Datos Crítica:** SQL Server 2017 con esquema **desnormalizado**, falta de integridad referencial y redundancia de datos.
- **Deuda Técnica:** Lógica de negocio "hardcodeada" en el código fuente, impidiendo una evolución ágil hacia nuevas funcionalidades.
- **Paradigma Monolítico:** Diseñado para un único cliente, lo que imposibilita un modelo de negocio SaaS (Software as a Service) sin rediseño.

---

## 2. Definición del Nuevo Stack Tecnológico

Se propone la transición a un ecosistema de alto rendimiento y bajo consumo de recursos:

### Infraestructura (LEMP)

- **L**inux (Ubuntu Server)
- **E**ngine-X (Nginx)
- **M**ariaDB / MySQL
- **P**HP 8.3+

### Frameworks de Desarrollo (TALL Stack)

- **Tailwind CSS:** Diseño responsivo y moderno basado en utilidades.
- **Alpine.js:** Reactividad ligera para el frontend.
- **Laravel:** Framework backend robusto y seguro.
- **Livewire:** Componentes dinámicos que eliminan la complejidad de frameworks JS pesados.

---

## 3. Propuestas Sugeridas para el Reporte

Para fortalecer la propuesta, se deben incluir los siguientes puntos críticos:

### A. Seguridad y Cumplimiento (Compliance)

- **Encriptación:** Implementación de cifrado **AES-256** para datos sensibles del historial médico.
- **Auditoría (Log System):** Registro inmutable de accesos y modificaciones en las historias clínicas para cumplimiento legal.

### B. Estrategia de Migración (ETL)

- **Limpieza de Datos:** Proceso de extracción para eliminar duplicados y corregir errores del sistema ASP.
- **Normalización:** Mapeo de datos planos a un esquema relacional optimizado para consultas rápidas.

### C. Innovación Operativa

- **Módulo de Dibujo:** Basado en HTML5 Canvas para permitir esquemas gráficos sobre fondos anatómicos del ojo.
- **Agente de IA:** Integración de modelos para el resumen automático de consultas y sugerencias de triaje.

---

## 4. Estimado de Tiempo de Ejecución

El proyecto se estima en un total de **21 a 27 semanas** para un MVP (Producto Mínimo Viable) robusto.

| Fase       | Actividad                                                                 | Duración      |
| :--------- | :------------------------------------------------------------------------ | :------------ |
| **Fase 1** | **Infraestructura Core:** Configuración LEMP y arquitectura Multitenancy. | ~~3 - 4 Semanas~~ |
| **Fase 2** | **Migración y ETL:** Limpieza y carga de datos desde SQL Server.          | 4 - 5 Semanas |
| **Fase 3** | **Desarrollo Médico:** Historias clínicas, agenda y flujo de consulta.    | 6 - 8 Semanas |
| **Fase 4** | **Módulos Especiales:** Ventas de lentes y herramienta de dibujo.         | 3 - 4 Semanas |
| **Fase 5** | **Inteligencia Artificial:** Integración de agentes de gestión.           | 3 - 4 Semanas |
| **Fase 6** | **QA y Despliegue:** Pruebas de estrés y paso a producción.               | 2 Semanas     |

---

## 5. Recomendaciones de Implementación

> **Estrategia de Multitenancy:** Se recomienda el uso de la librería `stancl/tenancy` para Laravel. Esto permite manejar múltiples clínicas de forma aislada, garantizando la privacidad de los datos de cada cliente.

- **API First:** Diseñar pensando en una futura App móvil nativa.
- **Backups:** Respaldos automatizados diarios en la nube con redundancia geográfica.

---
