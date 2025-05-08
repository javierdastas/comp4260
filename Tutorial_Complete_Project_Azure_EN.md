# 🧑‍🏫 Complete Tutorial: Deploying a Web Application in Azure using Azure for Students

This tutorial guides students step-by-step to complete the project of a web application deployed on **Azure App Service**, connected to an **Azure SQL Database**, **without using virtual machines (VMs)**.

---

## ✅ Prerequisites
- An active **Azure for Students** account.
- The base Flask project downloaded.
- Python 3.8+ installed on your computer.

---

## 🔹 Step 1: Create the SQL Database in Azure

1. Sign in at [https://portal.azure.com](https://portal.azure.com).
2. Click **"Create a resource"** > **"SQL Database"**.
3. Enter:
   - Database name: `project_tasks`
   - Create a new server with username and password
4. Select **S0** as the basic pricing tier.
5. Review and click **Create**.
6. Once created, go to the server > "Firewalls" > **Add your IP** > **Save**.

---

## 🔹 Step 2: Get the connection string

1. Open your SQL database from the portal.
2. Click **"Connection strings"** > select `ODBC`.
3. Copy the string and replace:
   - `{your_password}` with your actual password.

---

## 🔹 Step 3: Create an App Service in Azure

1. In the portal, click **"Create a resource"** > **"App Service"**.
2. Fill in:
   - App name: `app-tasks-jd` (use your initials or name)
   - Free plan (F1)
   - Code, Linux, and stack: **Python 3.8**

---

## 🔹 Step 4: Configure environment variables

1. In your App Service, go to **"Configuration > Application settings"**.
2. Add the following keys:

| Name           | Value (Example)                        |
|----------------|----------------------------------------|
| SQL_SERVER     | servername.database.windows.net        |
| SQL_DATABASE   | project_tasks                          |
| SQL_USERNAME   | adminuser@servername                   |
| SQL_PASSWORD   | YourSecurePassword123                  |

3. Click **Save**.

---

## 🔹 Step 5: Prepare your application locally

1. Open terminal and clone the repository:
```bash
git clone https://github.com/your_user/azure_students_project.git
cd azure_students_project
```

2. Create a virtual environment and install dependencies:
```bash
python -m venv venv
source venv/bin/activate  # On Windows: venv\Scripts\activate
pip install -r requirements.txt
```

3. Run locally to test:
```bash
python app.py
```

---

## 🔹 Step 6: Deploy the application to Azure

1. In App Service > "Deployment Center":
   - Connect your GitHub repository.
   - Select the main branch.

2. Make sure you have the `requirements.txt` file.

Azure will detect Flask and automatically deploy the app.

---

## 🔹 Step 7: Verify your application

1. Go to your App Service URL:
   ```
   https://app-tasks-jd.azurewebsites.net
   ```
2. Make sure you can:
   - Add tasks
   - Mark tasks as done
   - Delete tasks

---

## 🧠 Tips

- Use the **Azure Pricing Calculator** to estimate costs.
- Document each step for your report.
- Take screenshots of the Azure portal.

---

## 🎓 Credits

Instructor: Javier A. Dastas  
Course: Cloud Computing  
Interamerican University of Puerto Rico – Arecibo Campus
