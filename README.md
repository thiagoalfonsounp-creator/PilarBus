# PilarBus - Ecosistema Móvil de Transporte Público

Este repositorio contiene la arquitectura y la documentación del flujo de desarrollo para la plataforma **PilarBus**, un sistema diseñado para la visualización en tiempo real del transporte público en la ciudad de Pilar.

---

## 🚀 Flujo de Trabajo con Control de Versiones (Git & GitHub)

Para garantizar la estabilidad del sistema y permitir entregas continuas sin interrupción del servicio, el equipo utiliza una estrategia de desarrollo basada en ramificación (Branching Strategy):

1. **Rama Principal (`main`):** Contiene código únicamente en estado listo para producción y totalmente probado.
2. **Ramas de Características (`feature/nombre-funcionalidad`):** Todo nuevo desarrollo o corrección se realiza en ramas separadas (por ejemplo: `feature/rastreo-tiempo-real` o `feature/integracion-sube`).

### Uso de Pull Requests (PR)
* Ningún desarrollador tiene permitido realizar `push` directamente sobre la rama `main`.
* Para integrar nuevo código, se debe abrir un **Pull Request (PR)** desde la rama `feature` hacia `main`.
* Todo PR requiere al menos la **revisión y aprobación (Code Review)** de un compañero de equipo antes de ser fusionado (*merged*). Esto asegura la calidad del código, el cumplimiento de estándares y previene la introducción de errores en producción.

---

## ⚙️ Integración y Entrega Continua (CI/CD)

El proyecto utiliza un pipeline automatizado de CI/CD (mediante GitHub Actions) para validar cada cambio de manera rápida y segura.

### 1. Validación Automática (CI - Integración Continua)
Cada vez que se abre o actualiza un Pull Request, la automatización ejecuta los siguientes pasos:
* **Build:** Compila la aplicación para verificar que no existan errores de sintaxis o dependencias rotas.
* **Test:** Ejecuta automáticamente la suite de pruebas unitarias e integrales (por ejemplo, validación de endpoints y lógica de rastreo).

> Si la fase de **Build** o **Test** falla, el Pull Request se bloquea automáticamente y no puede fusionarse a `main` hasta corregir el problema.

### 2. Despliegue Automático (CD - Entrega Continua)
Una vez que el Pull Request es aprobado y fusionado con éxito en la rama `main`:
* El pipeline activa el despliegue automático hacia la infraestructura en la nube.
* Se realiza un despliegue sin tiempo de inactividad (*Zero-Downtime Deployment*), garantizando que los ciudadanos sigan utilizando la aplicación sin interrupciones mientras se actualiza la versión.

---

## 👥 Equipo de Desarrollo
* **Asignatura:** Fundamentos del Desarrollo del Software y Metodologías Ágiles
* **Universidad Nacional de Pilar (2026)**
