# Registro de clases particulares

Página para cargar pagos y clases desde el celular. Cada registro se escribe en la pestaña **Movimientos** de tu Google Sheets, y el **Resumen** se actualiza solo.

Este repo no contiene datos privados: la URL de tu hoja y el PIN se cargan una sola vez en cada dispositivo y quedan guardados ahí.

## Puesta en marcha

### 1. La hoja de cálculo
1. Subí `Registro_clases_particulares.xlsx` a Google Drive.
2. Abrilo y andá a **Archivo → Guardar como Hojas de cálculo de Google**. Trabajá siempre sobre esa copia (el script no funciona sobre un .xlsx).

### 2. El script que conecta la página con la hoja
1. En la hoja: **Extensiones → Apps Script**.
2. Borrá lo que haya y pegá el contenido de `Code.gs`.
3. Cambiá `CAMBIA-ESTE-PIN` por un PIN largo que solo sepas vos. Guardá.
4. **Implementar → Nueva implementación** → tipo **Aplicación web**:
   - Ejecutar como: **Yo**
   - Quién tiene acceso: **Cualquier usuario**
5. Autorizá los permisos (Google va a avisar que la app no está verificada: es tu propio script, elegí *Configuración avanzada → Ir a…*).
6. Copiá la **URL de la aplicación web** (termina en `/exec`).

### 3. GitHub Pages
1. Creá un repo nuevo y subí `index.html` y este `README.md`. **No subas `Code.gs` con tu PIN.**
2. **Settings → Pages → Deploy from a branch → main / (root)** → Save.
3. En un minuto queda publicado en `https://TU-USUARIO.github.io/NOMBRE-DEL-REPO/`.

### 4. En el celular
1. Abrí la página, pegá la URL `/exec` y el PIN, y tocá **Conectar**.
2. Agregala a la pantalla de inicio (Safari: *Compartir → Agregar a inicio*; Chrome: *⋮ → Agregar a pantalla principal*).

## Uso
- **Pago recibido**: lo que te pagó la familia, sea el monto que sea.
- **Clase dada**: lo que corresponde cobrar. Si el alumno tiene tarifa cargada, el monto se completa solo.
- Los alumnos se agregan en la pestaña **Alumnos** de la hoja y aparecen solos en la página.

## Si cambiás el script
Después de editar `Code.gs` en Apps Script: **Implementar → Gestionar implementaciones → ✏️ → Versión: Nueva versión → Implementar**. Así la URL sigue siendo la misma.
