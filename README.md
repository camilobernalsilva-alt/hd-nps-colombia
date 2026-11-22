# Resultados NPS Colombia · Hunter Douglas

Resultados de la encuesta NPS a distribuidores de Hunter Douglas y Flexalum, con focos de mejora y planes de acción por área.

Página publicada con GitHub Pages y datos compartidos en Google Sheets. Cada persona entra con su propia cuenta (correo @hdlao.com).

- **Página:** https://camilobernalsilva-alt.github.io/hd-nps-colombia/
- **Repositorio:** https://github.com/camilobernalsilva-alt/hd-nps-colombia
- `index.html`: la página. GitHub Pages la publica desde la raíz del repositorio.
- `Code.gs`: el script de Google Apps Script que guarda los datos y maneja las cuentas. No se sube a GitHub: va en la hoja de cálculo.

## 1. Base de datos en Google Sheets

1. Crea una hoja de cálculo nueva en Google Drive, por ejemplo "Resultados NPS Colombia – base de datos".
2. Abre **Extensiones > Apps Script**, reemplaza el contenido de `Código.gs` por el de `Code.gs` y guarda.
3. En **Configuración del proyecto > Propiedades de la secuencia de comandos**, crea la propiedad `CLAVE` con la clave del equipo (al menos 10 caracteres).
4. **Implementar > Nueva implementación > Aplicación web**. Ejecutar como: **Yo**. Quién tiene acceso: **Cualquier usuario**.
5. Autoriza los permisos. Si Google muestra "Google no ha verificado esta aplicación", es tu propio script: **Avanzado > Ir a… > Permitir**.
6. Copia la URL de la aplicación web (termina en `/exec`) y pégala en `index.html`, en la línea `const APPS_SCRIPT_URL = "";`.

Cuando cambies `Code.gs`: **Implementar > Gestionar implementaciones > editar > Nueva versión**. Así la URL no cambia.

La hoja crea sola sus pestañas: **Estado** (los datos; no se edita a mano), **Usuarios** (perfiles; la contraseña solo se guarda cifrada), **Bitacora** (quién guardó y cuándo) y **Resumen** (los datos en formato legible).

## 2. Publicación en GitHub Pages

1. Sube `index.html` y este `README.md` a la raíz del repositorio.
2. **Settings > Pages**: Source **Deploy from a branch**, rama `main`, carpeta `/ (root)`.
3. En uno o dos minutos la página queda en https://camilobernalsilva-alt.github.io/hd-nps-colombia/.

## 3. Primer ingreso y acceso del equipo

1. Abre la página, elige **Crear cuenta** y regístrate con `camilo.bernal@hdlao.com`: esa cuenta es el administrador principal.
2. Comparte el enlace y, por un canal privado, la clave del equipo.
3. Cada persona crea su cuenta con la clave del equipo, su correo **@hdlao.com** y una contraseña personal, y después ingresa con esos tres datos.

## Administración

Solo la ven `camilo.bernal@hdlao.com` y los correos que agregue. Desde ahí se ven todos los perfiles registrados, se agregan o quitan administradores, se desactivan o activan cuentas y se generan contraseñas temporales.

## Sincronización

- Cada cambio se envía al momento, y cada perfil abierto se guarda y se reconecta solo cada 3 minutos. **Sincronizar ahora** lo hace de inmediato.
- Si dos personas editan a la vez, los cambios se combinan. Si cambian el mismo campo, queda el último guardado.
- Sin internet, los cambios quedan en el navegador y se envían al volver la conexión.

## Seguridad

- Sin cuenta no se ve ningún dato, aunque la página de GitHub sea pública.
- Solo se aceptan correos @hdlao.com; lo valida el servidor.
- Tras 5 intentos fallidos, el correo queda bloqueado 10 minutos.
- Si la clave del equipo se filtra, cámbiala en la propiedad `CLAVE` y entrégala de nuevo al equipo.

## Datos de la encuesta

Los resultados de la encuesta son confidenciales y **no están dentro del HTML**: viven en la hoja de Google, detrás del login. Para cargarlos la primera vez, el administrador entra a **Configuración > Copia de seguridad > Cargar respaldo** y elige el archivo `nps_colombia_datos.json` (que se guarda fuera del repositorio). Después, los planes de acción se comparten con todo el equipo.
