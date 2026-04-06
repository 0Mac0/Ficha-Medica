# 📋 Ficha médica – Registro clínico

[![HTML5](https://img.shields.io/badge/HTML5-E34F26?logo=html5&logoColor=white)](https://developer.mozilla.org/es/docs/Web/HTML)
[![CSS3](https://img.shields.io/badge/CSS3-1572B6?logo=css3&logoColor=white)](https://developer.mozilla.org/es/docs/Web/CSS)
[![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?logo=javascript&logoColor=black)](https://developer.mozilla.org/es/docs/Web/JavaScript)
[![GitHub Pages](https://img.shields.io/badge/GitHub%20Pages-222222?logo=githubpages&logoColor=white)](https://pages.github.com/)

## Descripción

Aplicación web desarrollada para el ingreso, validación, búsqueda y administración de fichas médicas.  
El sistema permite registrar pacientes mediante un formulario con controles de verificación, buscar usuarios por apellido, editar y eliminar registros, y almacenar la información de forma local en el navegador.

Este proyecto fue realizado como parte de una actividad de **verificación y validación de procesos en proyectos de desarrollo de software**, aplicando criterios objetivos para detectar errores frecuentes en formularios web y asegurar el correcto funcionamiento de la interfaz.

## Objetivo

Diseñar e implementar un formulario de ingreso para ficha médica que permita:

- registrar nuevos pacientes,
- validar correctamente los campos ingresados,
- evitar duplicidad de registros sin confirmación,
- buscar usuarios por apellido,
- editar y eliminar registros,
- mantener persistencia local de los datos,
- entregar una interfaz clara, funcional y responsiva.

## Tecnologías utilizadas

- **HTML5**: estructura semántica de la aplicación.
- **CSS3**: diseño visual, Grid, Flexbox, variables CSS y responsividad.
- **JavaScript (ES6+)**: validación de datos, eventos del DOM, almacenamiento local y lógica de negocio.
- **GitHub Pages**: publicación en internet para evaluación.

## Funcionalidades principales

- Registro de pacientes mediante formulario.
- Validación de campos obligatorios.
- Validación de RUT chileno mediante algoritmo módulo 11.
- Validación de correo electrónico.
- Validación de número telefónico.
- Cálculo de edad a partir de la fecha de nacimiento.
- Búsqueda de registros por apellido.
- Edición de registros existentes.
- Eliminación de registros con confirmación.
- Manejo de duplicados por RUT con opción de sobrescritura.
- Autocompletado de datos al ingresar un RUT existente.
- Persistencia local mediante `localStorage`.
- Botones de acción: **Guardar**, **Limpiar** y **Cerrar**.
- Interfaz adaptable a distintos tamaños de pantalla.

## Requerimientos funcionales

1. El sistema debe permitir ingresar nuevos registros de pacientes.
2. El formulario debe contener al menos los siguientes campos:
   - RUT
   - Nombres
   - Apellidos
   - Dirección
   - Ciudad
   - Teléfono
   - Email
   - Fecha de nacimiento
   - Estado civil
   - Comentarios
3. El sistema debe validar los campos antes de guardar.
4. El sistema debe verificar si el RUT ya existe.
5. Si el registro existe, debe solicitar confirmación para sobrescribirlo.
6. El sistema debe permitir crear un registro nuevo con el mismo RUT si el usuario lo decide.
7. El sistema debe permitir buscar usuarios por apellido.
8. El sistema debe permitir editar registros existentes.
9. El sistema debe permitir eliminar registros desde la tabla.
10. El sistema debe permitir limpiar el formulario.
11. El sistema debe permitir cerrar la aplicación.
12. El sistema debe guardar la información de forma persistente en el navegador.

## Requerimientos no funcionales

1. La aplicación debe estar disponible en internet para su evaluación.
2. La interfaz debe ser responsiva y adaptarse a móviles, tablets y escritorio.
3. La experiencia de uso debe ser clara e intuitiva.
4. El sistema debe responder de forma rápida ante las acciones del usuario.
5. El código debe ser legible, ordenado y fácil de mantener.
6. Las validaciones deben ejecutarse en tiempo real o al momento de enviar el formulario.
7. La aplicación debe funcionar en navegadores modernos.
8. Los datos ingresados deben mantenerse almacenados localmente en el navegador.
9. El sistema debe reducir errores de ingreso mediante validaciones preventivas.
10. La solución debe ser estable durante la interacción del usuario.

## Validaciones implementadas

- RUT obligatorio y validado con módulo 11.
- Nombres obligatorios.
- Apellidos obligatorios.
- Dirección obligatoria.
- Ciudad obligatoria.
- Teléfono con formato numérico y longitud válida.
- Email con formato correcto.
- Fecha de nacimiento obligatoria y no futura.
- Estado civil obligatorio.
- Comentarios con límite máximo de caracteres.

## Verificación y validación

Se realizaron pruebas para comprobar el comportamiento del sistema frente a entradas válidas e inválidas, verificando el correcto funcionamiento de los controles implementados.

### Pruebas realizadas

| Caso de prueba | Resultado esperado | Resultado obtenido |
|---|---|---|
| Ingreso de datos válidos | Guardar el registro correctamente | Cumple |
| Campo RUT vacío | Mostrar error de validación | Cumple |
| RUT con formato incorrecto | Rechazar el ingreso | Cumple |
| Email inválido | Limpiar el campo y mostrar mensaje | Cumple |
| Teléfono con letras | Rechazar caracteres no numéricos | Cumple |
| Fecha futura | Rechazar el registro | Cumple |
| Duplicado de RUT | Solicitar confirmación | Cumple |
| Búsqueda por apellido | Mostrar coincidencias parciales | Cumple |
| Edición de registro | Actualizar datos existentes | Cumple |
| Eliminación de registro | Solicitar confirmación y borrar | Cumple |
| Botón Limpiar | Vaciar formulario y errores | Cumple |
| Botón Cerrar | Ocultar la aplicación | Cumple |

## Observaciones

Durante las pruebas se controlaron errores frecuentes como:

- campos obligatorios sin completar,
- formato incorrecto de RUT,
- correos inválidos,
- teléfonos con caracteres no permitidos,
- registros duplicados,
- fechas de nacimiento no válidas,
- pérdida de datos al recargar la página.

## Código fuente

La aplicación fue desarrollada en un solo archivo HTML que integra:

- estructura del formulario,
- estilos CSS embebidos,
- lógica JavaScript para validación, persistencia y gestión de registros.

El código implementa:

- captura de datos desde formularios,
- normalización de texto,
- validación de entradas,
- formateo del RUT,
- cálculo de edad,
- búsqueda por apellido,
- edición y eliminación de registros,
- almacenamiento local con `localStorage`.

## Instalación y uso local

1. Clona el repositorio:
   ```bash
   git clone https://github.com/0Mac0/Ficha-Medica.git
