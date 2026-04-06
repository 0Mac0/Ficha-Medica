# 📋 Ficha médica – Registro clínico

[![HTML5](https://img.shields.io/badge/HTML5-E34F26?logo=html5&logoColor=white)](https://developer.mozilla.org/es/docs/Web/HTML)
[![CSS3](https://img.shields.io/badge/CSS3-1576B6?logo=css3&logoColor=white)](https://developer.mozilla.org/es/docs/Web/CSS)
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

La aplicación fue desarrollada en un solo archivo HTML que integra la estructura del formulario, los estilos visuales y la lógica de validación, búsqueda, edición, eliminación y almacenamiento local.

```html
<!DOCTYPE html>
<html lang="es">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0, user-scalable=yes" />
  <title>Ficha médica | Registro clínico extendido</title>
  <style>
    * {
      margin: 0;
      padding: 0;
      box-sizing: border-box;
    }

    body {
      background: #ffffff;
      font-family: 'Inter', system-ui, -apple-system, 'Segoe UI', Roboto, Helvetica, Arial, sans-serif;
      color: #0f172a;
      line-height: 1.4;
    }

    :root {
      --bg: #ffffff;
      --text: #1f2937;
      --muted: #4b5563;
      --line: #e2e8f0;
      --line-strong: #cbd5e1;
      --separator-dark: #1e293b;
      --accent: #2563eb;
      --accent-dark: #1e40af;
      --accent-soft: #eff6ff;
      --danger: #dc2626;
      --danger-bg: #fef2f2;
      --warning-bg: #fffbeb;
      --radius-card: 20px;
      --shadow-sm: 0 8px 20px rgba(0, 0, 0, 0.02), 0 2px 6px rgba(0, 0, 0, 0.05);
    }

    .wrap {
      max-width: 2200px;
      margin: 0 auto;
      padding: 24px 36px 32px 36px;
    }

    .two-columns {
      display: grid;
      grid-template-columns: 1.4fr 1.6fr;
      gap: 44px;
      align-items: start;
    }

    .grid-2col {
      display: grid;
      grid-template-columns: repeat(2, 1fr);
      gap: 28px 36px;
    }

    .full-width {
      grid-column: span 2;
    }

    .table-wrapper {
      overflow-x: auto;
      border-radius: 20px;
      border: 1px solid #eef2ff;
      background: white;
      width: 100%;
    }

    table {
      width: 100%;
      min-width: 1550px;
      border-collapse: collapse;
      font-size: 0.85rem;
    }

    input, select, textarea {
      width: 100%;
      border: 1px solid #cbd5e1;
      border-radius: 14px;
      padding: 12px 16px;
      font-family: inherit;
      font-size: 0.95rem;
      background: white;
      transition: all 0.2s ease;
      outline: none;
      color: #0f172a;
    }

    td, th {
      padding: 12px 14px;
      border-bottom: 1px solid #eef2ff;
      white-space: nowrap;
      overflow: hidden;
      text-overflow: ellipsis;
      max-width: 280px;
    }

    @media (max-width: 1400px) {
      .two-columns {
        grid-template-columns: 1fr;
        gap: 40px;
      }
      .wrap {
        padding: 20px 28px;
      }
      table {
        min-width: 1450px;
      }
    }

    @media (max-width: 640px) {
      .grid-2col {
        grid-template-columns: 1fr;
        gap: 20px;
      }
      .full-width {
        grid-column: span 1;
      }
      .stats-row {
        flex-direction: column;
        gap: 8px;
      }
      .stat-item {
        border-bottom: 1px solid #e2e8f0;
        padding-bottom: 12px;
      }
      .stat-item:last-child {
        border-bottom: none;
      }
      td, th {
        padding: 8px 10px;
        max-width: 200px;
      }
      table {
        min-width: 1350px;
      }
    }

    .page-header {
      margin-bottom: 28px;
      border-bottom: 4px solid var(--line-strong);
      padding-bottom: 20px;
    }

    h1 {
      font-size: clamp(1.8rem, 3vw, 2.5rem);
      font-weight: 700;
      letter-spacing: -0.02em;
      background: linear-gradient(135deg, #0f172a 0%, #1e293b 100%);
      background-clip: text;
      -webkit-background-clip: text;
      color: transparent;
      margin-bottom: 10px;
    }

    .subtitle {
      color: var(--muted);
      font-size: 1rem;
      max-width: 85%;
      margin-bottom: 12px;
      line-height: 1.45;
    }

    .badges {
      display: flex;
      flex-wrap: wrap;
      gap: 10px;
      margin-top: 4px;
    }

    .badge {
      border: 1px solid var(--line);
      background: #fafcff;
      padding: 6px 14px;
      border-radius: 60px;
      font-size: 0.8rem;
      font-weight: 500;
      color: #1e293b;
    }

    .form-panel {
      background: transparent;
    }

    form {
      display: flex;
      flex-direction: column;
      gap: 28px;
    }

    .section {
      border-bottom: 4px solid var(--line-strong);
      padding-bottom: 24px;
    }

    .section:last-of-type {
      border-bottom: none;
      padding-bottom: 0;
    }

    .section h2 {
      font-size: 1.3rem;
      font-weight: 600;
      margin-bottom: 20px;
      letter-spacing: -0.2px;
      color: #0c4e6e;
      display: flex;
      align-items: center;
      gap: 8px;
    }

    label {
      font-weight: 600;
      font-size: 0.9rem;
      display: block;
      margin-bottom: 8px;
      color: #1e293b;
      letter-spacing: -0.2px;
    }

    .help {
      font-size: 0.75rem;
      margin-top: 6px;
      min-height: 20px;
      color: #64748b;
    }

    .help.error {
      color: var(--danger);
      font-weight: 500;
    }

    .actions {
      display: flex;
      flex-wrap: wrap;
      gap: 12px;
      margin-top: 6px;
    }

    button {
      border: none;
      border-radius: 40px;
      padding: 10px 20px;
      font-weight: 600;
      font-size: 0.9rem;
      cursor: pointer;
      transition: transform 0.12s, background 0.2s;
    }

    button:active {
      transform: scale(0.97);
    }

    .primary {
      background: linear-gradient(105deg, var(--accent), #1e3a8a);
      color: white;
      box-shadow: 0 4px 8px rgba(37, 99, 235, 0.2);
    }

    .ghost {
      background: #f1f5f9;
      color: #1e293b;
    }

    .danger {
      background: #fee2e2;
      color: #991b1b;
    }

    .warning {
      background: #ffedd5;
      color: #b45309;
    }

    .summary-panel {
      display: flex;
      flex-direction: column;
      gap: 0;
    }

    .stats-simple {
      background: transparent;
      padding: 0 0 12px 0;
    }

    .stats-row {
      display: flex;
      justify-content: space-between;
      align-items: baseline;
      gap: 20px;
      flex-wrap: wrap;
    }

    .stat-item {
      flex: 1;
      min-width: 120px;
      padding: 8px 4px;
    }

    .stat-item strong {
      font-size: 2rem;
      font-weight: 800;
      display: block;
      line-height: 1.2;
      color: #0f172a;
      margin-bottom: 6px;
    }

    .stat-item span {
      font-size: 0.8rem;
      color: var(--muted);
      font-weight: 500;
      letter-spacing: -0.2px;
    }

    .separator {
      border: none;
      border-top: 4px solid var(--separator-dark);
      margin: 20px 0 24px 0;
      width: 100%;
    }

    .search-box {
      background: transparent;
      padding: 0 0 8px 0;
    }

    .search-box h2 {
      font-size: 1.1rem;
      margin-bottom: 14px;
      font-weight: 600;
    }

    .search-actions {
      display: flex;
      gap: 12px;
      margin: 12px 0 10px;
      flex-wrap: wrap;
    }

    .tip-note {
      background: #f8fafc;
      padding: 10px 14px;
      border-radius: 18px;
      font-size: 0.8rem;
      color: #334155;
      margin-top: 12px;
      border-left: 3px solid var(--accent);
    }

    .records-section {
      background: transparent;
    }

    .records-section h2 {
      font-size: 1rem;
      font-weight: 600;
      margin-bottom: 12px;
    }

    th {
      text-align: left;
      padding: 14px 12px;
      background: #fafcff;
      border-bottom: 3px solid var(--line-strong);
      font-weight: 700;
      color: #1e293b;
    }

    tr:hover td {
      background-color: #f9fbfe;
    }

    .editBtn, .deleteBtn {
      border-radius: 32px;
      padding: 6px 10px;
      font-size: 1.1rem;
      font-weight: 500;
      margin: 0 2px;
      display: inline-flex;
      align-items: center;
      justify-content: center;
      gap: 4px;
      background: transparent;
      transition: 0.15s ease;
      cursor: pointer;
      border: none;
      width: 36px;
      height: 36px;
    }

    .editBtn {
      background: #eef2ff;
      color: #1e3a8a;
    }

    .editBtn:hover {
      background: #dbeafe;
      transform: scale(1.02);
    }

    .deleteBtn {
      background: #fee2e2;
      color: #b91c1c;
    }

    .deleteBtn:hover {
      background: #fecaca;
      transform: scale(1.02);
    }

    .empty-row td {
      text-align: center;
      color: #6c757d;
      padding: 32px;
    }

    .toast {
      position: fixed;
      bottom: 24px;
      right: 24px;
      background: #1e293b;
      color: white;
      padding: 12px 20px;
      border-radius: 50px;
      font-weight: 500;
      font-size: 0.85rem;
      box-shadow: 0 10px 25px rgba(0,0,0,0.1);
      opacity: 0;
      transform: translateY(10px);
      transition: 0.2s ease;
      pointer-events: none;
      z-index: 1000;
    }

    .toast.show {
      opacity: 1;
      transform: translateY(0);
    }

    .hidden {
      display: none !important;
    }

    .close-view {
      min-height: 100vh;
      display: grid;
      place-items: center;
      background: #f1f5f9;
      padding: 24px;
    }

    .close-card {
      background: white;
      border-radius: 36px;
      padding: 32px;
      max-width: 480px;
      text-align: center;
      box-shadow: var(--shadow-sm);
    }
  </style>
</head>
<body>
  <div id="appShell">
    <div class="wrap">
      <div class="page-header">
        <h1>🟢 Formulario de ingreso · Ficha médica</h1>
        <p class="subtitle">Registro clínico</p>
        <div class="badges">
          <span class="badge">✅ 10 campos obligatorios</span>
          <span class="badge">🔍 Búsqueda por apellido</span>
          <span class="badge">💾 Persistencia local</span>
          <span class="badge">✏️ Edición / Eliminación</span>
          <span class="badge">🕒 Fecha y hora de registro</span>
          <span class="badge">📝 Autocompletado + Duplicados</span>
          <span class="badge">📌 Estado civil visible en tabla</span>
        </div>
      </div>

      <div class="two-columns">
        <div class="form-panel">
          <form id="medForm" novalidate>
            <div class="section">
              <h2>🩺 Datos del paciente</h2>
              <div class="grid-2col">
                <div class="field full-width">
                  <label for="rut">RUT *</label>
                  <input id="rut" name="rut" type="text" placeholder="12.345.678-9" autocomplete="off" maxlength="12" />
                  <div class="help" data-error-for="rut"></div>
                </div>

                <div class="field">
                  <label for="nombres">Nombres *</label>
                  <input id="nombres" type="text" placeholder="JUAN CARLOS" />
                  <div class="help" data-error-for="nombres"></div>
                </div>

                <div class="field"></div>

                <div class="field full-width">
                  <label for="apellidos">Apellidos *</label>
                  <input id="apellidos" type="text" placeholder="PÉREZ GONZÁLEZ" />
                  <div class="help" data-error-for="apellidos"></div>
                </div>

                <div class="field full-width">
                  <label for="direccion">Dirección *</label>
                  <input id="direccion" type="text" placeholder="AV. LOS CÓNDORES 123" />
                  <div class="help" data-error-for="direccion"></div>
                </div>

                <div class="field">
                  <label for="ciudad">Ciudad *</label>
                  <input id="ciudad" type="text" placeholder="SANTIAGO" />
                  <div class="help" data-error-for="ciudad"></div>
                </div>

                <div class="field"></div>

                <div class="field full-width">
                  <label for="telefono">Teléfono *</label>
                  <input id="telefono" type="tel" placeholder="912345678" maxlength="9" />
                  <div class="help" data-error-for="telefono"></div>
                </div>

                <div class="field full-width">
                  <label for="email">Email *</label>
                  <input id="email" type="email" placeholder="CORREO@EJEMPLO.CL" />
                  <div class="help" data-error-for="email"></div>
                </div>

                <div class="field">
                  <label for="fechaNacimiento">Fecha nacimiento *</label>
                  <input id="fechaNacimiento" type="date" />
                  <div class="help" data-error-for="fechaNacimiento"></div>
                </div>

                <div class="field"></div>

                <div class="field full-width">
                  <label for="estadoCivil">Estado civil *</label>
                  <select id="estadoCivil">
                    <option value="">SELECCIONE...</option>
                    <option>SOLTERO/A</option>
                    <option>CASADO/A</option>
                    <option>UNIÓN CIVIL</option>
                  </select>
                  <div class="help" data-error-for="estadoCivil"></div>
                </div>

                <div class="field full-width">
                  <label for="comentarios">Comentarios clínicos</label>
                  <textarea id="comentarios" rows="3" placeholder="ALERGIAS, PATOLOGÍAS PREVIAS, OBSERVACIONES..."></textarea>
                  <div class="help" data-error-for="comentarios"></div>
                </div>
              </div>
            </div>

            <div class="section">
              <h2>⚙️ Acciones</h2>
              <div class="actions">
                <button class="primary" type="submit" id="btnGuardar">💾 Guardar</button>
                <button class="ghost" type="button" id="btnLimpiar">🧹 Limpiar</button>
                <button class="warning hidden" type="button" id="btnCancelarEdicion">✖️ Cancelar edición</button>
                <button class="danger" type="button" id="btnCerrar">🔒 Cerrar aplicación</button>
              </div>
            </div>
          </form>
        </div>

        <div class="summary-panel">
          <div class="stats-simple">
            <div class="stats-row">
              <div class="stat-item">
                <strong id="totalRecords">0</strong>
                <span>registros almacenados</span>
              </div>
              <div class="stat-item">
                <strong id="searchHits">0</strong>
                <span>coincidencias en la búsqueda</span>
              </div>
              <div class="stat-item">
                <strong id="lastAction">✅ Listo</strong>
                <span>estado actual del sistema</span>
              </div>
            </div>
          </div>

          <hr class="separator" />

          <div class="search-box">
            <h2>🔎 Búsqueda por apellido</h2>
            <label for="apellidoBuscar">Apellido (parcial o completo)</label>
            <input id="apellidoBuscar" type="text" placeholder="Ej: PÉREZ, GONZÁLEZ" />
            <div class="search-actions">
              <button class="primary" type="button" id="btnBuscar">Buscar</button>
              <button class="ghost" type="button" id="btnVerTodos">Ver todos los registros</button>
            </div>
            <div class="tip-note" id="searchInfo">
              💡 La búsqueda es insensible a mayúsculas/minúsculas y detecta coincidencias parciales. Tabla con columna Estado Civil visible.
            </div>
          </div>

          <hr class="separator" />

          <div class="records-section">
            <h2>📋 Registros clínicos · Estado civil incorporado</h2>
            <div class="table-wrapper">
              <table>
                <thead>
                  <tr>
                    <th>📅 Fecha y Hora R</th>
                    <th>RUT</th>
                    <th>Nombres</th>
                    <th>Apellidos</th>
                    <th>Edad</th>
                    <th>💬 Comentario</th>
                    <th>Dirección</th>
                    <th>Ciudad</th>
                    <th>Teléfono</th>
                    <th>Email</th>
                    <th>📌 Estado civil</th>
                    <th>Acciones</th>
                  </tr>
                </thead>
                <tbody id="recordsBody">
                  <tr class="empty-row"><td colspan="12">📭 No hay registros aún. Complete el formulario.</td></tr>
                </tbody>
              </table>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>

  <div id="toast" class="toast"></div>

  <div id="closeView" class="close-view hidden">
    <div class="close-card">
      <h2>🚪 Aplicación cerrada</h2>
      <p>Puede cerrar esta pestaña manualmente. Todos los datos fueron guardados.</p>
      <button id="forceReloadBtn" style="margin-top: 20px; background:#eef2ff; border-radius: 40px; padding: 8px 18px;">Volver</button>
    </div>
  </div>

  <script>
    (function(){
      const STORAGE_KEY = 'fichas_medicas_v2';
      const form = document.getElementById('medForm');
      const toastEl = document.getElementById('toast');
      const recordsBody = document.getElementById('recordsBody');
      const totalSpan = document.getElementById('totalRecords');
      const searchHitsSpan = document.getElementById('searchHits');
      const lastActionSpan = document.getElementById('lastAction');
      const searchInfoDiv = document.getElementById('searchInfo');
      const appShell = document.getElementById('appShell');
      const closeViewDiv = document.getElementById('closeView');

      const rutInput = document.getElementById('rut');
      const emailInput = document.getElementById('email');
      const telefonoInput = document.getElementById('telefono');
      const apellidoBuscar = document.getElementById('apellidoBuscar');
      const btnBuscar = document.getElementById('btnBuscar');
      const btnVerTodos = document.getElementById('btnVerTodos');
      const btnGuardar = document.getElementById('btnGuardar');
      const btnLimpiar = document.getElementById('btnLimpiar');
      const btnCancelarEdicion = document.getElementById('btnCancelarEdicion');
      const btnCerrar = document.getElementById('btnCerrar');

      const EMAIL_REGEX = /^[^\s@]+@[^\s@]+\.[^\s@]{2,}$/i;
      let editingRecordId = null;

      const normalizeText = (v) => (v || '').toString().trim().replace(/\s+/g, ' ');
      const normalizeRUT = (v) => normalizeText(v).replace(/[^0-9kK]/g, '').toUpperCase();
      const normalizePhone = (v) => normalizeText(v).replace(/[^0-9]/g, '');
      const toUpperText = (v) => normalizeText(v).toUpperCase();

      function formatRUT(value) {
        const clean = normalizeRUT(value);
        if (!clean) return '';
        if (clean.length === 1) return clean;
        const body = clean.slice(0, -1);
        const dv = clean.slice(-1);
        const formattedBody = body.replace(/\B(?=(\d{3})+(?!\d))/g, '.');
        return `${formattedBody}-${dv}`;
      }

      function formatearFechaHora(isoString) {
        if (!isoString) return '—';
        try {
          const fecha = new Date(isoString);
          if (isNaN(fecha.getTime())) return isoString;
          const dia = fecha.getDate().toString().padStart(2,'0');
          const mes = (fecha.getMonth()+1).toString().padStart(2,'0');
          const anio = fecha.getFullYear();
          const horas = fecha.getHours().toString().padStart(2,'0');
          const minutos = fecha.getMinutes().toString().padStart(2,'0');
          const segundos = fecha.getSeconds().toString().padStart(2,'0');
          return `${dia}/${mes}/${anio} ${horas}:${minutos}:${segundos}`;
        } catch(e) {
          return '—';
        }
      }

      function calcularEdad(fechaNacimientoStr) {
        if (!fechaNacimientoStr) return '—';
        const nacimiento = new Date(fechaNacimientoStr + 'T00:00:00Z');
        if (isNaN(nacimiento.getTime())) return '?';
        const hoy = new Date();
        const hoyUTC = new Date(Date.UTC(hoy.getFullYear(), hoy.getMonth(), hoy.getDate()));
        const nacimientoUTC = new Date(Date.UTC(nacimiento.getUTCFullYear(), nacimiento.getUTCMonth(), nacimiento.getUTCDate()));
        let edad = hoyUTC.getUTCFullYear() - nacimientoUTC.getUTCFullYear();
        const mesDiff = hoyUTC.getUTCMonth() - nacimientoUTC.getUTCMonth();
        if (mesDiff < 0 || (mesDiff === 0 && hoyUTC.getUTCDate() < nacimientoUTC.getUTCDate())) {
          edad--;
        }
        return edad >= 0 ? edad : 0;
      }

      function loadRecords() {
        try {
          let records = JSON.parse(localStorage.getItem(STORAGE_KEY) || '[]');
          records = records.map(rec => {
            if (!rec.id) rec.id = Date.now() + '-' + Math.random().toString(36).substr(2, 6);
            if (!rec.fechaRegistro) rec.fechaRegistro = new Date().toISOString();
            return rec;
          });
          return records;
        } catch(e) { return []; }
      }

      function saveRecords(records) {
        localStorage.setItem(STORAGE_KEY, JSON.stringify(records));
        refreshStatsAndRender();
      }

      function showToast(msg, duration=2200) {
        toastEl.textContent = msg;
        toastEl.classList.add('show');
        clearTimeout(window._toastTimer);
        window._toastTimer = setTimeout(() => toastEl.classList.remove('show'), duration);
      }

      function setStatus(msg) { lastActionSpan.textContent = msg; }

      function clearErrors() {
        document.querySelectorAll('.help').forEach(el => { el.textContent = ''; el.classList.remove('error','ok'); });
      }

      function setError(field, msg) {
        const el = document.querySelector(`[data-error-for="${field}"]`);
        if (el) { el.textContent = msg; el.classList.add('error'); }
      }

      function validateRUT(rutStr) {
        const raw = (rutStr || '').toString().trim().toUpperCase();
        if (!raw) return 'El RUT es obligatorio.';
        if (/[^0-9Kk.-]/.test(raw)) return 'Solo números, puntos y guión.';
        const clean = normalizeRUT(raw);
        const match = clean.match(/^(\d{1,8})([0-9K])$/);
        if (!match) return 'Formato RUT inválido (ej: 12345678-5).';
        const body = match[1];
        const dv = match[2];
        let sum = 0, mult = 2;
        for(let i = body.length-1; i >=0; i--) {
          sum += parseInt(body[i],10) * mult;
          mult = mult === 7 ? 2 : mult+1;
        }
        const expectedDV = (11 - (sum % 11));
        const expected = expectedDV === 11 ? '0' : expectedDV === 10 ? 'K' : String(expectedDV);
        return expected !== dv ? 'Dígito verificador incorrecto.' : '';
      }

      function validateEmail(email) { return (!email || !EMAIL_REGEX.test(email)) ? 'Email válido requerido.' : ''; }
      function validatePhone(phone) { const ph = normalizePhone(phone); return (!ph || !/^\d{8,9}$/.test(ph)) ? 'Teléfono debe tener 8 o 9 dígitos.' : ''; }

      function getFormData() {
        return {
          rut: formatRUT(rutInput.value),
          nombres: toUpperText(document.getElementById('nombres').value),
          apellidos: toUpperText(document.getElementById('apellidos').value),
          direccion: toUpperText(document.getElementById('direccion').value),
          ciudad: toUpperText(document.getElementById('ciudad').value),
          telefono: normalizePhone(telefonoInput.value),
          email: toUpperText(emailInput.value),
          fechaNacimiento: document.getElementById('fechaNacimiento').value,
          estadoCivil: toUpperText(document.getElementById('estadoCivil').value),
          comentarios: toUpperText(document.getElementById('comentarios').value)
        };
      }

      function validateFull(data) {
        clearErrors();
        let errors = {};
        const rutErr = validateRUT(data.rut);
        if (rutErr) errors.rut = rutErr;
        if (!data.nombres) errors.nombres = 'Nombres obligatorios.';
        if (!data.apellidos) errors.apellidos = 'Apellidos obligatorios.';
        if (!data.direccion) errors.direccion = 'Dirección obligatoria.';
        if (!data.ciudad) errors.ciudad = 'Ciudad obligatoria.';
        const phoneErr = validatePhone(data.telefono);
        if (phoneErr) errors.telefono = phoneErr;
        const emailErr = validateEmail(data.email);
        if (emailErr) errors.email = emailErr;
        if (!data.fechaNacimiento) errors.fechaNacimiento = 'Fecha nacimiento requerida.';
        else if (data.fechaNacimiento > new Date().toISOString().slice(0,10)) errors.fechaNacimiento = 'No puede ser futura.';
        if (!data.estadoCivil) errors.estadoCivil = 'Seleccione estado civil.';
        if (data.comentarios.length > 500) errors.comentarios = 'Máximo 500 caracteres.';
        Object.entries(errors).forEach(([k,v]) => setError(k,v));
        return errors;
      }

      function setFormData(record) {
        rutInput.value = formatRUT(record.rut || '');
        document.getElementById('nombres').value = record.nombres || '';
        document.getElementById('apellidos').value = record.apellidos || '';
        document.getElementById('direccion').value = record.direccion || '';
        document.getElementById('ciudad').value = record.ciudad || '';
        telefonoInput.value = record.telefono || '';
        emailInput.value = record.email || '';
        document.getElementById('fechaNacimiento').value = record.fechaNacimiento || '';
        document.getElementById('estadoCivil').value = record.estadoCivil || '';
        document.getElementById('comentarios').value = record.comentarios || '';
      }

      function clearForm() {
        form.reset();
        clearErrors();
        cancelEditMode(false);
        setStatus('Formulario limpio');
        showToast('Campos limpiados');
      }

      function cancelEditMode(showMsg=true) {
        editingRecordId = null;
        btnGuardar.textContent = 'Guardar';
        btnCancelarEdicion.classList.add('hidden');
        if(showMsg) {
          setStatus('Edición cancelada');
          showToast('Modo edición desactivado');
        }
      }

      function cancelAndClearForm() {
        if (editingRecordId) {
          cancelEditMode(true);
          clearForm();
        } else {
          clearForm();
        }
      }

      function autoCompletarPorRUT() {
        if (editingRecordId) return;
        const rutIngresado = rutInput.value.trim();
        if (!rutIngresado) return;
        const rutNorm = normalizeRUT(rutIngresado);
        if (!rutNorm) return;
        const records = loadRecords();
        const existente = records.find(r => normalizeRUT(r.rut) === rutNorm);
        if (existente) {
          setFormData(existente);
          showToast(`RUT existente: datos cargados automáticamente`, 2500);
          setStatus(`Datos de ${existente.nombres} ${existente.apellidos} cargados`);
        }
      }

      function refreshStatsAndRender() {
        const records = loadRecords();
        totalSpan.textContent = records.length;
        const queryRaw = apellidoBuscar.value.trim();
        if(queryRaw !== '') {
          const filtered = records.filter(r => normalizeSearch(r.apellidos).includes(normalizeSearch(queryRaw)));
          searchHitsSpan.textContent = filtered.length;
          renderTable(filtered);
          searchInfoDiv.innerHTML = `🔍 <strong>${filtered.length} coincidencia(s)</strong> para "${escapeHtml(queryRaw)}"`;
          if(filtered.length === 0) searchInfoDiv.innerHTML += `<span style="display:block; margin-top:4px;">Sin resultados, prueba otro apellido</span>`;
        } else {
          searchHitsSpan.textContent = '0';
          renderTable(records);
          searchInfoDiv.innerHTML = `💡 La búsqueda es insensible a mayúsculas/minúsculas y detecta coincidencias parciales.`;
        }
        setStatus(editingRecordId ? 'Modo edición activo' : 'Sincronizado');
      }

      function normalizeSearch(val) { return (val || '').toString().toLocaleLowerCase('es-CL'); }
      function escapeHtml(str) { return String(str).replace(/[&<>]/g, function(m){if(m==='&') return '&amp;'; if(m==='<') return '&lt;'; if(m==='>') return '&gt;'; return m;}); }

      function renderTable(recordsArray) {
        if(!recordsArray.length) {
          recordsBody.innerHTML = '<tr class="empty-row"><td colspan="12">📭 No hay registros aún. Complete el formulario.</td></tr>';
          return;
        }
        const html = recordsArray.map(rec => {
          const edad = calcularEdad(rec.fechaNacimiento);
          const fechaHoraMostrar = formatearFechaHora(rec.fechaRegistro);
          const estadoCivilMostrar = rec.estadoCivil && rec.estadoCivil.trim() !== '' ? rec.estadoCivil : '—';
          return `
            <tr>
              <td title="${escapeHtml(rec.fechaRegistro || '')}">${escapeHtml(fechaHoraMostrar)}</td>
              <td>${escapeHtml(formatRUT(rec.rut))}</td>
              <td>${escapeHtml(rec.nombres)}</td>
              <td>${escapeHtml(rec.apellidos)}</td>
              <td>${edad}</td>
              <td style="max-width: 180px; white-space: normal; word-break: break-word;">${escapeHtml(rec.comentarios || '—')}</td>
              <td>${escapeHtml(rec.direccion)}</td>
              <td>${escapeHtml(rec.ciudad)}</td>
              <td>${escapeHtml(rec.telefono)}</td>
              <td>${escapeHtml(rec.email)}</td>
              <td>${escapeHtml(estadoCivilMostrar)}</td>
              <td style="white-space: nowrap;">
                <div style="display: flex; gap: 6px; align-items: center;">
                  <button class="editBtn" data-action="edit" data-id="${escapeHtml(rec.id)}" title="Editar registro">✏️</button>
                  <button class="deleteBtn" data-action="delete" data-id="${escapeHtml(rec.id)}" title="Eliminar registro">🗑️</button>
                </div>
              </td>
            </tr>
          `;
        }).join('');
        recordsBody.innerHTML = html;
      }

      function searchBySurname() {
        const query = apellidoBuscar.value.trim();
        const records = loadRecords();
        if(!query) {
          renderTable(records);
          searchHitsSpan.textContent = '0';
          searchInfoDiv.innerHTML = '💡 La búsqueda es insensible a mayúsculas/minúsculas y detecta coincidencias parciales.';
          setStatus('Mostrando todos');
          showToast('Listado completo');
          return;
        }
        const filtered = records.filter(r => normalizeSearch(r.apellidos).includes(normalizeSearch(query)));
        searchHitsSpan.textContent = filtered.length;
        renderTable(filtered);
        setStatus(`Búsqueda: "${query}" - ${filtered.length} resultados`);
        showToast(`${filtered.length} coincidencias encontradas`);
        searchInfoDiv.innerHTML = `🔍 <strong>${filtered.length} resultado(s)</strong> para "${escapeHtml(query)}"`;
      }

      function deleteRecord(recordId) {
        let records = loadRecords();
        const idx = records.findIndex(r => r.id === recordId);
        if(idx === -1) { showToast('Registro no encontrado'); return; }
        const name = records[idx].nombres + ' ' + records[idx].apellidos;
        if(confirm(`¿Eliminar ficha de ${name}?`)) {
          records = records.filter(r => r.id !== recordId);
          saveRecords(records);
          setStatus('Registro eliminado');
          showToast(`Ficha de ${name} eliminada`);
          if(editingRecordId === recordId) cancelEditMode(false);
          const currentQuery = apellidoBuscar.value.trim();
          if(currentQuery) searchBySurname();
          else refreshStatsAndRender();
        }
      }

      function enterEditMode(record) {
        editingRecordId = record.id;
        setFormData(record);
        btnGuardar.textContent = 'Actualizar';
        btnCancelarEdicion.classList.remove('hidden');
        setStatus(`Editando: ${record.nombres} ${record.apellidos}`);
        showToast('Modo edición - modifica y guarda');
      }

      form.addEventListener('submit', (e) => {
        e.preventDefault();
        const data = getFormData();
        const errors = validateFull(data);
        if(Object.keys(errors).length) {
          setStatus('Corrige errores en el formulario');
          showToast('Campos inválidos');
          return;
        }

        let records = loadRecords();
        const currentRutNorm = normalizeRUT(data.rut);

        if(editingRecordId) {
          const editIndex = records.findIndex(r => r.id === editingRecordId);
          if(editIndex === -1) {
            showToast('Registro original no existe');
            cancelEditMode(false);
            return;
          }
          data.id = editingRecordId;
          data.fechaRegistro = new Date().toISOString();
          records[editIndex] = data;
          saveRecords(records);
          setStatus('Registro actualizado');
          showToast('Ficha actualizada correctamente');
          form.reset();
          cancelEditMode(false);
          apellidoBuscar.value = '';
          refreshStatsAndRender();
          return;
        }

        const existingWithSameRut = records.filter(r => normalizeRUT(r.rut) === currentRutNorm);
        if(existingWithSameRut.length > 0) {
          let msg = `Ya existe ${existingWithSameRut.length} registro(s) con el RUT ${data.rut}. ¿Qué deseas hacer?\n\n`;
          msg += `1. "Sobrescribir" -> Elegir cuál registro sobrescribir (se actualizarán sus datos y la fecha/hora).\n`;
          msg += `2. "Nuevo" -> Crear un nuevo registro con el mismo RUT (duplicado).`;
          const opcion = confirm(msg + "\n\nAceptar = Sobrescribir / Cancelar = Crear nuevo");
          if(opcion) {
            let opciones = existingWithSameRut.map((r, idx) => `${idx+1}. ${r.nombres} ${r.apellidos} (Registro del ${formatearFechaHora(r.fechaRegistro)})`).join('\n');
            let seleccion = prompt(`Selecciona el registro a sobrescribir:\n${opciones}\n\nIngresa el número (1-${existingWithSameRut.length}):`);
            let idxSeleccionado = parseInt(seleccion) - 1;
            if(isNaN(idxSeleccionado) || idxSeleccionado < 0 || idxSeleccionado >= existingWithSameRut.length) {
              showToast('Selección inválida, operación cancelada');
              return;
            }
            const targetRecord = existingWithSameRut[idxSeleccionado];
            const targetIndex = records.findIndex(r => r.id === targetRecord.id);
            data.id = targetRecord.id;
            data.fechaRegistro = new Date().toISOString();
            records[targetIndex] = data;
            saveRecords(records);
            setStatus('Registro sobrescrito');
            showToast('Registro actualizado exitosamente');
            form.reset();
            refreshStatsAndRender();
            return;
          } else {
            data.id = Date.now() + '-' + Math.random().toString(36).substr(2, 6);
            data.fechaRegistro = new Date().toISOString();
            records.push(data);
            saveRecords(records);
            setStatus('Nuevo registro duplicado guardado');
            showToast('Nuevo registro creado (mismo RUT)');
            form.reset();
            apellidoBuscar.value = '';
            refreshStatsAndRender();
            return;
          }
        }

        data.id = Date.now() + '-' + Math.random().toString(36).substr(2, 6);
        data.fechaRegistro = new Date().toISOString();
        records.push(data);
        saveRecords(records);
        setStatus('Registro guardado');
        showToast('Ficha guardada exitosamente');
        form.reset();
        apellidoBuscar.value = '';
        refreshStatsAndRender();
      });

      btnLimpiar.addEventListener('click', clearForm);
      btnCerrar.addEventListener('click', () => {
        try { window.close(); } catch(e){}
        appShell.classList.add('hidden');
        closeViewDiv.classList.remove('hidden');
        setStatus('App cerrada');
      });
      btnBuscar.addEventListener('click', searchBySurname);
      btnVerTodos.addEventListener('click', () => {
        apellidoBuscar.value = '';
        refreshStatsAndRender();
        setStatus('Mostrando todos los registros');
        showToast('Listado completo');
      });
      btnCancelarEdicion.addEventListener('click', cancelAndClearForm);
      rutInput.addEventListener('blur', autoCompletarPorRUT);

      recordsBody.addEventListener('click', (e) => {
        const edit = e.target.closest('.editBtn');
        if(edit) {
          const id = edit.dataset.id;
          const rec = loadRecords().find(r => r.id === id);
          if(rec) enterEditMode(rec);
          return;
        }
        const del = e.target.closest('.deleteBtn');
        if(del) deleteRecord(del.dataset.id);
      });

      const upperFields = ['nombres','apellidos','direccion','ciudad','email','estadoCivil','comentarios'];
      upperFields.forEach(id => {
        const el = document.getElementById(id);
        if(el) el.addEventListener('input', function() {
          const s=this.selectionStart, e=this.selectionEnd;
          this.value=this.value.toUpperCase();
          if(s!==null) this.setSelectionRange(s,e);
        });
      });

      telefonoInput.addEventListener('input', (e) => { e.target.value = e.target.value.replace(/[^0-9]/g, '').slice(0,9); });

      rutInput.addEventListener('input', (e) => {
        const cur = e.target.value;
        const form = formatRUT(cur);
        const atEnd = e.target.selectionStart === cur.length;
        e.target.value = form;
        if(atEnd) e.target.setSelectionRange(form.length, form.length);
      });

      rutInput.addEventListener('blur', () => {
        if(rutInput.value && validateRUT(rutInput.value)) {
          setError('rut','RUT inválido, campo limpiado');
          rutInput.value='';
        } else if(rutInput.value) rutInput.value = formatRUT(rutInput.value);
      });

      emailInput.addEventListener('blur', () => {
        const val = emailInput.value.trim().toUpperCase();
        if(val && !EMAIL_REGEX.test(val)) {
          emailInput.value='';
          setError('email','Email inválido');
          showToast('Email inválido, limpiado');
        } else emailInput.value=val;
      });

      refreshStatsAndRender();
      setStatus('Listo para registrar informacion paciente');
    })();
  </script>
</body>
</html>
