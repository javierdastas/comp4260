# ⚙️ Guía: Configurar Variables de Entorno en Azure App Service

## 1. Ve al portal de Azure
Abre [https://portal.azure.com](https://portal.azure.com) y selecciona tu **App Service**.

## 2. Ir a "Configuración"
1. En el menú lateral izquierdo, selecciona **"Configuración > Configuración de la aplicación"**.

## 3. Agregar variables
Haz clic en **"+ Nueva configuración de la aplicación"** e ingresa:

| Nombre             | Valor                         |
|--------------------|-------------------------------|
| SQL_SERVER         | nombre-servidor.database.windows.net |
| SQL_DATABASE       | nombre_base_datos             |
| SQL_USERNAME       | nombre_usuario@nombre-servidor |
| SQL_PASSWORD       | contraseña_segura             |

✅ Asegúrate de que los nombres coincidan con los usados en tu código (`os.getenv(...)`).

## 4. Guardar cambios
Haz clic en **"Guardar"** y luego **"Aceptar"** para reiniciar la aplicación.

¡Listo! Tu aplicación Flask en Azure puede acceder a la base de datos usando estas variables.
