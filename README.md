# PilarBus: Ecosistema Móvil y Plataforma Web de Transporte Público

## Descripción del Proyecto
El proyecto **PilarBus** es una iniciativa orientada a la transformación del transporte público local mediante el desarrollo e implementación de una plataforma integral (aplicación móvil y sistema web). Su objetivo principal radica en proporcionar a los ciudadanos la visualización del recorrido y la ubicación de las unidades en tiempo real, mejorando la previsibilidad y la calidad del servicio de movilidad.

Dadas las características del entorno operacional y la necesidad de incorporar la retroalimentación continua de los usuarios beta, la arquitectura del software y su proceso de desarrollo se conciben bajo principios de alta adaptabilidad e integración continua.

---

## Estrategia de Control de Versiones y Flujo de Trabajo

Para garantizar la estabilidad del software en producción y permitir un ritmo de desarrollo colaborativo y ordenado, el equipo adopta una estrategia de ramificación (*Branching Strategy*) estructurada:

* **Rama Principal (`main`):** Almacena únicamente versiones estables del código que han superado los procesos de validación y se encuentran en condiciones de desplegarse en el entorno de producción.
* **Ramas de Funcionalidad (`feature/*`):** Todo nuevo requerimiento, mejora o corrección se desarrolla en ramas independientes a partir de `main` (por ejemplo: `feature/rastreo-tiempo-real` o `feature/integracion-sube`).

### Protocolo de Pull Requests y Revisión de Código
La integración de cambios a la rama principal está estrictamente regulada mediante las siguientes directrices:
* Queda restringido el envío directo de cambios (*direct push*) sobre la rama `main`.
* Todo desarrollo completado debe someterse a la creación de un **Pull Request (PR)** hacia la rama principal.
* Cada Pull Request requiere la revisión y aprobación formal (*Code Review*) de al menos un integrante del equipo técnico. Este proceso asegura el cumplimiento de las normativas de arquitectura, la calidad del código y previene la introducción de regresiones en el sistema.

---

## Integración y Entrega Continua (CI/CD)

El repositorio cuenta con un flujo de trabajo automatizado (*Pipeline CI/CD*) que garantiza que cada modificación sea evaluada antes de su incorporación definitiva.

### 1. Integración Continua (CI)
Ante la apertura o actualización de un Pull Request, el sistema ejecuta de forma automática las siguientes etapas de verificación:
* **Compilación (*Build*):** Comprueba que la solución compile correctamente y que no existan inconsistencias en las dependencias del proyecto.
* **Verificación de Pruebas (*Test*):** Ejecuta la batería de pruebas unitarias y de integración para certificar que la lógica de negocio y las interfaces de conexión funcionan acorde a las especificaciones.

En caso de detectarse fallos en cualquiera de estas fases, la fusión del Pull Request queda bloqueada hasta que las observaciones sean subsanadas.

### 2. Entrega y Despliegue Continuo (CD)
Una vez que el Pull Request cuenta con la aprobación requerida y supera las pruebas automatizadas, se efectúa la fusión con la rama `main`:
* El flujo de despliegue transfiere automáticamente los cambios hacia la infraestructura en la nube.
* Se utiliza un esquema de despliegue sin interrupción del servicio (*Zero-Downtime Deployment*), lo que asegura la operatividad ininterrumpida de la aplicación
