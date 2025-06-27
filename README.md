# 🤖 AIDW Conversational Assistant (Azure Backend)

This backend powers the **AIDW Conversational Assistant** — a smart AI-driven bot that enables users to explore and query **AI Design Wins (AIDW)** data via natural language. The system is built using **Microsoft Azure** services including Azure Functions, Azure OpenAI, and Azure Cognitive Search.
<img src="https://github.com/user-attachments/assets/42fceb2c-42ad-4b11-8f7f-ff619cf694df">

![AIDW](https://github.com/user-attachments/assets/6ebb68e6-8c85-4275-9771-f246883f2708)
---

## 📦 Tech Stack

- **☁️ Platform**: Microsoft Azure  
- **⚙️ Runtime**: Azure Functions (Python)  
- **🧠 AI Services**: Azure OpenAI (GPT models)  
- **🔍 Search**: Azure Cognitive Search  
- **🗃️ Database**: PostgreSQL (used for chart data and structured responses)  

---

## 🛠️ Installation & Setup

### 🔁 Step 1: Clone the Repository

```bash
git clone https://github.com/yourusername/aidw-assistant-backend.git
cd aidw-assistant-backend
```

### ⚒️ Step 2: Install Azure Functions Core Tools

Azure Functions Core Tools (`func`) is required to run the app locally.

#### ✅ On Windows (via npm):

```bash
npm install -g azure-functions-core-tools@4 --unsafe-perm true
```

---

### 🐍 Step 3: Set Up Python Environment & Install Dependencies

```bash
# Create a virtual environment
python -m venv env

# Activate it
# On macOS/Linux:
source env/bin/activate
# On Windows:
env\Scripts\activate

# Install dependencies
pip install -r requirements.txt
```

---

### 🔐 Step 4: Load Environment Variables

Create a `.env` file in the project root and add the following variables (these should match what's configured in the Azure Portal under **Function App > Configuration > Application Settings**):

```env
AZURE_OPENAI_ENDPOINT=""
AZURE_OPENAI_MODEL=""
AZURE_OPENAI_API_VERSION=""
SEARCH_SERVICE_NAME=""
SEARCH_INDEX_NAME=""
pssql_host=""
pssql_port=""
pssql_user=""
pssql_password=""
pssql_database=""
```

---

### 🌐 Step 5: Network Configuration & Deployment

- Configure **Virtual Network (VNet)** and **NSG (Network Security Group)** to allow access to:
  - Azure Storage
  - Logic Apps
  - Web Apps (if integrated)
  - Azure Content Safety
- Ensure firewall/private endpoint access to PostgreSQL is enabled.
- Deploy the Function App using:

```bash
func azure functionapp publish <your-function-app-name>
```

> 🧪 Ensure you're logged in via `az login` and the correct subscription is selected.

---

### 🚀 Step 6: Test the Function App

Use the **"Test/Run"** blade in Azure Portal and submit the following sample payload:

```json
{
  "question": "hi",
  "model": "gpt-4o-mini",
  "chat_history": []
}
```

---

### 🌐 Step 7: Deploy the Web App

Deploy your frontend (web app) to Azure App Service and connect it with the backend function URL.

Test it using a browser or tools like Postman/curl.

---

## 👥 Team

| Name           | Role                      | Organization       |
|----------------|---------------------------|--------------------|
| Rahul Jigan    | Lead Data Scientist       | Third Eye Data     |
| Swapna Jirale  | Data Engineer             | Third Eye Data     |
| Fayez Khan     | Full Stack Developer      | Third Eye Data     |

---

## 📄 License

This project is licensed under the **MIT License**.
