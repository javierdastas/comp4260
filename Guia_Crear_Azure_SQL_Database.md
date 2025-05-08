# 🛠 Guía Paso a Paso: Crear Azure SQL Database

## 1. Inicia sesión en el portal de Azure
Ve a [https://portal.azure.com](https://portal.azure.com)

## 2. Crear una nueva base de datos SQL
1. Haz clic en **"Crear un recurso"**.
2. Busca **"SQL Database"** y selecciónalo.
3. En la pestaña **"Básico"**:
   - **Nombre de la base de datos**: proyecto_estudiante (puede ser otro)
   - **Servidor**: Crea uno nuevo:
     - Nombre del servidor
     - Nombre de administrador (ej: adminuser)
     - Contraseña segura
4. Selecciona **"Plan Gratuito"** (si está disponible) o un tamaño pequeño como S0.
5. Revisa y haz clic en **"Crear"**.

## 3. Configurar acceso al servidor
1. Ve al recurso **Servidor SQL** creado.
2. Selecciona **"Firewalls y redes virtuales"**.
3. Haz clic en **"Agregar dirección IP del cliente actual"**.
4. Guarda los cambios.

## 4. Obtener los datos de conexión
1. En la base de datos, haz clic en **"Cadena de conexión"**.
2. Copia la cadena de ODBC y sustituye la contraseña.
3. Usa los siguientes valores como variables de entorno:
   - `SQL_SERVER`
   - `SQL_DATABASE`
   - `SQL_USERNAME`
   - `SQL_PASSWORD`
