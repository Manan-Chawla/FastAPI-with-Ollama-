# Local AI Text Generation API (FastAPI + Ollama)

A lightweight, secure, and fully local **AI text generation API** built using **FastAPI** and **Ollama (LLaMA 3)**. This project demonstrates how to run large language models locally and expose them via a clean REST API with **API key authentication and credit-based usage control**.

---

## 🚀 Features

* 🔥 FastAPI-based backend
* 🤖 Local LLaMA 3 inference using Ollama
* 🔐 API key authentication via request headers
* 💳 Credit-based request limiting per API key
* 🧪 Easy testing with Postman
* 🌐 No cloud dependency – runs completely offline

---

## 🛠️ Tech Stack

* **Python 3.9+**
* **FastAPI** – API framework
* **Uvicorn** – ASGI server
* **Ollama** – Local LLM runner
* **python-dotenv** – Environment variable management
* **requests** – HTTP utilities
* **Postman Agent** – API testing

---

## 📁 Project Structure

```
ai-text-api/
│── main.py
│── requirements.txt
│── .env
│── README.md
│── venv/
```

---

## ⚙️ Setup Instructions

### 1️⃣ Clone the Repository

```bash
git clone <your-repo-url>
cd ai-text-api
```

### 2️⃣ Create & Activate Virtual Environment (Recommended)

```bash
python -m venv venv
```

**Activate:**

* Windows:

```bash
venv\Scripts\activate
```

* macOS / Linux:

```bash
source venv/bin/activate
```

---

### 3️⃣ Install Dependencies

Create a `requirements.txt` file with:

```
fastapi
uvicorn
ollama
python-dotenv
requests
```

Install all dependencies:

```bash
pip install -r requirements.txt
```

---

### 4️⃣ Setup Environment Variables

Create a `.env` file in the root directory:

```
API_KEY=your_secret_api_key_here
```

---

### 5️⃣ Install & Run Ollama

Download and install Ollama from the official site.

Pull the LLaMA 3 model:

```bash
ollama pull llama3
```

Make sure Ollama is running in the background.

---

### 6️⃣ Run the FastAPI Server

```bash
uvicorn main:app --reload
```

Server will start at:

```
http://127.0.0.1:8000
```

---

## 📡 API Usage

### Endpoint

```
POST /generate
```

### Headers

```
x-api-key: your_secret_api_key_here
```

### Request Body (JSON)

```json
{
  "prompt": "Explain FastAPI in simple terms"
}
```

### Response

```json
{
  "response": "FastAPI is a modern Python framework used to build fast APIs..."
}
```

⚠️ Each request consumes **1 credit** from the API key.

---

## 🔐 Credit System Logic

* Each API key starts with a fixed number of credits
* Every successful request deducts 1 credit
* Requests are rejected once credits reach zero

This simulates **real-world SaaS-style API usage control**.

---

## ❓ Do Users Need to Write Code?

**Yes — but only once.**

* Backend code is written a single time
* After setup, users interact only via API calls
* No code changes needed for normal usage

---

## ✨ Future Improvements

* Database-backed API key storage
* Rate limiting & request logging
* User dashboard
* Frontend UI integration
* Cloud / VPS deployment

---

## 📜 License

This project is open-source and free to use for learning and experimentation.

---

## 👤 Author

**Manan Chawla**

If you find this project useful, feel free to ⭐ the repository or suggest improvements!
