# 🎧 GD Eventos: DJ Services Management

![React](https://img.shields.io/badge/React-20232A?style=for-the-badge&logo=react&logoColor=61DAFB) ![Node.js](https://img.shields.io/badge/Node.js-43853D?style=for-the-badge&logo=node.js&logoColor=white) ![MySQL](https://img.shields.io/badge/MySQL-00000F?style=for-the-badge&logo=mysql&logoColor=white) ![Docker](https://img.shields.io/badge/Docker-2CA5E0?style=for-the-badge&logo=docker&logoColor=white)

Sistema integral web para la gestión de fechas, cotizaciones y contratación de servicios para el DJ Gustavo Delgadillo. Este proyecto permite a los clientes explorar disponibilidad, solicitar presupuestos personalizados y realizar pagos electrónicos de forma segura, mientras el administrador gestiona su agenda.

---

### Vista Previa del Proyecto

| Home / Explorador de Fechas | Formulario de Cotización | Panel de Administración (Privado) |
| :---: | :---: | :---: |
| [Home](./) | [Cotizar](./) | [Dashboard](./) |

---

### Stack Tecnológico

El sistema utiliza una arquitectura Full-Stack desacoplada, priorizando el rendimiento y la seguridad del cliente:

* **Frontend:** Interfaz de usuario dinámica y responsiva construida con **React**, basada en un diseño de alta fidelidad de Figma (Brutalist UI).
* **Backend:** API REST desarrollada con Node.js y Express para el manejo de la lógica de negocio y procesamiento de solicitudes.
* **Base de Datos:** Almacenamiento relacional en MySQL 8.0 para la persistencia de eventos, clientes y transacciones.
* **Infraestructura:** Orquestación de servicios mediante Docker Compose para garantizar la portabilidad del entorno de desarrollo.

---

### Prácticas de Seguridad y Privacidad

Para proteger la integridad del sistema y la información de los clientes, se implementan las siguientes medidas:

* **Sanitización de Formularios:** Validación y limpieza de datos en el backend (ej. usando express-validator) para prevenir ataques de inyección SQL y XSS en el formulario de cotización.
* **Protección de Credenciales de Pago:** Integración con pasarelas de pago (como Stripe/PayPal) asegurando que los datos bancarios sensibles nunca toquen ni se almacenen en nuestra base de datos.
* **Gestión de Entorno Seguro:** Aislamiento estricto de claves API y credenciales de base de datos. Se utiliza un archivo `.env` local que está explícitamente excluido del control de versiones mediante `.gitignore` para evitar filtraciones en el repositorio.

---

### Configuración y Despliegue

**Requisitos previos**
* [Docker Desktop](https://www.docker.com/products/docker-desktop/) instalado.
* [Git](https://git-scm.com/) para clonar el repositorio.

**Instalación en 3 pasos**

1.  **Clonar el repositorio:** ```bash
    git clone [https://github.com/AlanArrietaF/GDconcurso.git](https://github.com/AlanArrietaF/GDconcurso.git)
    cd GDconcurso
    ```
2.  **Configurar variables de entorno:** Crea un archivo `.env` en la raíz (asegúrate de no subirlo al repositorio) con los siguientes parámetros:
    ```env
    DB_HOST=db 
    DB_USER=admin_gd 
    DB_PASSWORD=tu_password_seguro 
    DB_NAME=gd_eventos 
    PORT=3000
    ```
3.  **Levantar contenedores:** ```bash
    docker compose up --build
    ```

---

### Endpoints Principales de la API

* `GET /api/fechas` (Retorna la disponibilidad y el lineup programado).
* `POST /api/cotizar` (Recibe datos sanitizados del cliente para generar un presupuesto).
* `POST /api/pago/procesar` (Endpoint seguro para gestionar la intención de pago con la pasarela externa).

---

### Autor

Alan Arrieta UNAM ICO
Josue Mendez
---
© 2026 - GD Eventos Project
