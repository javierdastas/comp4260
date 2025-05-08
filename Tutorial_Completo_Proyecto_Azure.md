# 🧑‍🏫 Tutorial Completo: Despliegue de una Aplicación Web en Azure usando Azure for Students

Este tutorial guía a los estudiantes paso a paso para completar el proyecto de una aplicación web desplegada en **Azure App Service**, conectada a una **Azure SQL Database**, **sin usar máquinas virtuales (VMs)**.

---

## ✅ Requisitos Previos
- Tener una cuenta activa de **Azure for Students**.
- Haber descargado el proyecto base (Flask).
- Tener instalado Python 3.8+ en tu computadora.

---

## 🔹 Paso 1: Crear la Base de Datos en Azure

1. Inicia sesión en [https://portal.azure.com](https://portal.azure.com).
2. Haz clic en **"Crear un recurso"** > **"SQL Database"**.
3. Ingresa:
   - Nombre de base de datos: `proyecto_tareas`
   - Crear un nuevo servidor con usuario y contraseña
4. Selecciona **S0** como plan básico.
5. Revisa y haz clic en **Crear**.
6. Una vez creada, ve al servidor > "Firewalls" > **Agrega tu IP** > **Guardar**.

---

## 🔹 Paso 2: Obtener la cadena de conexión

1. Abre tu base de datos desde el portal.
2. Haz clic en **"Cadenas de conexión"** > selecciona `ODBC`.
3. Copia la cadena y sustituye:
   - `{your_password}` por la contraseña real.

---

## 🔹 Paso 3: Crear App Service en Azure

1. En el portal, haz clic en **"Crear un recurso"** > **"App Service"**.
2. Llena:
   - Nombre de la app: `app-tareas-jd` (usa tu nombre o siglas)
   - Plan gratuito (F1)
   - Código, Linux, y stack: **Python 3.8**

---

## 🔹 Paso 4: Configurar las variables de entorno

1. En tu App Service, ve a **"Configuración > Configuración de la aplicación"**.
2. Añade las siguientes claves:

| Nombre         | Valor (Ejemplo)                         |
|----------------|------------------------------------------|
| SQL_SERVER     | servidor.database.windows.net            |
| SQL_DATABASE   | proyecto_tareas                          |
| SQL_USERNAME   | adminuser@servidor                       |
| SQL_PASSWORD   | TuContraseñaSegura123                    |

3. Haz clic en **Guardar**.

---

## 🔹 Paso 5: Preparar tu aplicación localmente

1. Abre terminal y clona el repositorio:
```bash
git clone https://github.com/tu_usuario/azure_students_project.git
cd azure_students_project
```

2. Crea entorno virtual e instala dependencias:
```bash
python -m venv venv
source venv/bin/activate  # En Windows: venv\Scripts\activate
pip install -r requirements.txt
```

3. Ejecuta localmente para probar:
```bash
python app.py
```

---

## 🔹 Paso 6: Desplegar la aplicación a Azure

1. En App Service > "Centro de implementación":
   - Conecta tu repositorio de GitHub.
   - Selecciona rama principal.

2. Asegúrate de tener el archivo `requirements.txt`.

Azure detectará Flask y hará el despliegue automáticamente.

---

## 🔹 Paso 7: Verifica tu aplicación

1. Accede a la URL de tu App Service:
   ```
   https://app-tareas-jd.azurewebsites.net
   ```
2. Asegúrate de que puedas:
   - Agregar tareas
   - Marcarlas como hechas
   - Eliminarlas

---

## 🧠 Sugerencias

- Usa **Azure Pricing Calculator** para estimar el costo.
- Documenta cada paso para tu entrega.
- Toma capturas del portal de Azure.

---

## 🎓 Créditos

Curso: Cloud Computing  
Profesor: Javier A. Dastas  
Universidad Interamericana de Puerto Rico – Recinto de Arecibo
