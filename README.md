# 📋 Ficha médica – Registro clínico

[![HTML5](https://img.shields.io/badge/HTML5-E34F26?logo=html5&logoColor=white)](https://developer.mozilla.org/es/docs/Web/HTML)
[![CSS3](https://img.shields.io/badge/CSS3-1572B6?logo=css3&logoColor=white)](https://developer.mozilla.org/es/docs/Web/CSS)
[![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?logo=javascript&logoColor=black)](https://developer.mozilla.org/es/docs/Web/JavaScript)
[![GitHub Pages](https://img.shields.io/badge/GitHub%20Pages-222222?logo=githubpages&logoColor=white)](https://pages.github.com/)

Aplicación web para el ingreso y gestión de fichas médicas. Permite registrar pacientes, validar campos, buscar por apellido, editar y eliminar registros, con almacenamiento local en el navegador. Proyecto desarrollado como parte de una evaluación de verificación y validación de software.

## ✅ Requisitos cumplidos

- **10 campos obligatorios:** RUT, Nombres, Apellidos, Dirección, Ciudad, Teléfono, Email, Fecha de Nacimiento, Estado civil, Comentarios.
- **Botones:** Guardar, Limpiar, Cerrar.
- **Búsqueda por apellido** (coincidencia parcial, insensible a mayúsculas).
- **Manejo de duplicados:** Si el RUT ya existe, pregunta si desea sobrescribir un registro existente o crear uno nuevo (duplicado).
- **Validación en tiempo real** de cada campo.
- **Persistencia local** (los datos se guardan en `localStorage`).
- **Edición y eliminación** de registros desde la tabla.
- **Diseño responsive** (adaptado a móviles y pantallas grandes).

## 🚀 Tecnologías utilizadas

- **HTML5** (estructura semántica)
- **CSS3** (Grid, Flexbox, variables CSS, media queries)
- **JavaScript (ES6+)** (manipulación del DOM, eventos, almacenamiento local)
- **GitHub Pages** (despliegue gratuito)

## 🖥️ Funcionalidades principales

| Función | Descripción |
|---------|-------------|
| **Guardar** | Valida todos los campos. Si el RUT no existe, crea un nuevo registro. Si existe, permite sobrescribir un registro existente o crear un duplicado. |
| **Limpiar** | Resetea el formulario y elimina mensajes de error. Cancela cualquier edición activa. |
| **Cerrar** | Oculta la aplicación y muestra una pantalla de cierre (simula el cierre de la aplicación). |
| **Buscar por apellido** | Filtra la tabla mostrando los registros cuyo apellido contenga el texto ingresado. |
| **Editar** | Carga los datos del registro en el formulario, cambia el botón “Guardar” a “Actualizar” y muestra un botón “Cancelar edición”. |
| **Eliminar** | Solicita confirmación y elimina el registro de la tabla y del almacenamiento local. |
| **Autocompletado** | Al escribir un RUT existente y salir del campo, se autocompletan los demás datos del paciente. |
| **Mayúsculas automáticas** | Los campos de texto (nombres, apellidos, dirección, ciudad, email, estado civil, comentarios) se convierten automáticamente a mayúsculas mientras se escribe. |
| **Validación de RUT** | Algoritmo de módulo 11 (dígito verificador chileno). |
| **Cálculo de edad** | A partir de la fecha de nacimiento, se muestra la edad en la tabla. |

## 📦 Instalación y uso local

1. Clona el repositorio:
   ```bash
   git clone https://github.com/TU_USUARIO/ficha-medica.git
