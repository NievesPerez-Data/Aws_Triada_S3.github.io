# 🚀 TRIAD: Despliegue de Web Estática en AWS

Este proyecto nace con un objetivo técnico claro: **dominar el despliegue profesional de arquitecturas web utilizando Amazon Web Services (AWS)**. A través de este repositorio, se documenta la transición de un desarrollo local hacia una infraestructura Cloud robusta y escalable.

## 🎯 El Desafío: Web Estática en la Nube

La meta principal de **TRIAD** ha sido demostrar la capacidad de orquestar y desplegar una web estática optimizada dentro de un **bucket de Amazon S3**. 

Este proceso no solo implica subir archivos, sino configurar la arquitectura necesaria para un entorno de producción real:
* **Gestión de Almacenamiento (S3):** Configuración de buckets para servir contenido de alto rendimiento.
* **Infraestructura y Seguridad:** Configuración de permisos, políticas de acceso (IAM) y visibilidad pública controlada.
* **Arquitectura Astro:** Uso de frameworks modernos para generar HTML estático eficiente, ligero y veloz.
* **Integración Continua:** Flujo de trabajo orientado a que cada cambio se refleje en la nube de forma automatizada.

---

## 🏗️ Estructura del Proyecto

Basado en el framework **Astro**, la web se organiza de la siguiente manera para garantizar modularidad y rendimiento:

```text
├── src/
│   ├── components/      # Elementos reutilizables (Botones, Cards, Navbar)
│   ├── layouts/         # Plantillas base de las páginas
│   ├── pages/           # Rutas y contenido principal de la web
│   └── styles/          # Archivos de CSS global
├── public/              # Activos estáticos (Imágenes, fuentes, iconos)
├── astro.config.mjs     # Configuración central de Astro
└── package.json         # Dependencias y scripts de construcción
```

### 🔍 ¿Qué encontrarás en la web?
Al explorar la página [TRIAD - Proyecto](https://nievesperez-data.github.io/Aws_Triada_S3.github.io/proyecto/), verás una interfaz diseñada para la claridad técnica:
1.  **Dashboard de Arquitectura:** Resumen de las herramientas Cloud utilizadas.
2.  **Secciones de Contenido:** Información desglosada sobre los pilares del proyecto (S3, Políticas, Astro).
3.  **Optimización:** Una experiencia de usuario fluida gracias al renderizado estático.

---

## 🛠️ Guía de Desarrollo (Original)

> **Nota:** Esta sección conserva la documentación técnica original del fork para el mantenimiento del código.

### Comandos de inicio

Astro viene con una interfaz de línea de comandos (CLI) integrada.

| Comando | Acción |
| :--- | :--- |
| `npm install` | Instala las dependencias necesarias. |
| `npm run dev` | Inicia el servidor de desarrollo local en `localhost:4321`. |
| `npm run build` | Genera el sitio estático para producción (en la carpeta `dist/`). |
| `npm run preview` | Previsualiza la construcción local antes de subir a AWS. |

---

## 🛡️ Configuración en AWS (Resumen Técnico)

Para replicar este despliegue, se deben considerar los siguientes puntos clave en la consola de AWS:
1.  **Static Website Hosting:** Habilitado en las propiedades del Bucket.
2.  **Block Public Access:** Desactivado (solo lo necesario para acceso de lectura).
3.  **Bucket Policy:**
    ```json
    {
        "Version": "2012-10-17",
        "Statement": [
            {
                "Sid": "PublicReadGetObject",
                "Effect": "Allow",
                "Principal": "*",
                "Action": "s3:GetObject",
                "Resource": "arn:aws:s3:::tu-nombre-de-bucket/*"
            }
        ]
    }
    ```

---
✨ *Proyecto creado y desplegado como parte de un desafío de infraestructura Cloud.*
