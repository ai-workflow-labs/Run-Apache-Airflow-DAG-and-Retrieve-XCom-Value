# 🚀 Run Apache Airflow DAG and Retrieve XCom Value

## 🧩 Overview
This workflow integrates **Apache Airflow’s DAGRun API** and **XCom** to enable **n8n** to trigger Airflow DAGs and seamlessly retrieve execution results.  

It provides an automated, secure, and efficient way to orchestrate and monitor Airflow workflows directly from n8n.

---

## ⚙️ Preparation Steps

### 1️⃣ Update Airflow API Link Prefix
- Navigate to the **`airflow-api`** node.  
- Update the Airflow API link prefix using the format:
http(s)://<ip>:<port>

makefile
Copy code

yaml
Copy code

---

### 2️⃣ Configure Authentication
- Go to the **`Airflow: dag_run`** node.  
- Update **Basic Auth** credentials with your **Airflow username** and **password**.  
- Repeat this step for the following nodes:
- `Airflow: dag_run - state`
- `Airflow: dag_run - get result`

> ⚠️ **Security Note:**  
> Basic Authentication stores credentials in plaintext.  
> If possible, use **API Keys** or **Tokens** for enhanced security.  

---

## 🔐 Authentication Recommendations
An example configuration is setting Airflow’s API authentication method to:
basic_auth

yaml
Copy code
You may choose other supported authentication mechanisms depending on your environment.

---

## 🧠 Required Permissions
Ensure the user account has the following permissions within Airflow:

| Permission Type | Required Access |
|------------------|-----------------|
| DAG Runs         | Create, Read     |
| XComs            | Read             |
| DAGs             | Edit, Read       |

---

## ✅ Summary
With this setup, n8n can:
- Trigger Airflow DAG runs 🏃‍♂️  
- Monitor their execution state 📊  
- Retrieve task results via XCom 💡  

This enables smooth automation and integration between your data workflows and Airflow orchestration layer.
