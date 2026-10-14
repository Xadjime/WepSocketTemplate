# Django WebSocket Template

A robust, production-ready starter template for building real-time applications using **Django**, **Django Channels**, **Daphne**, and **PostgreSQL**.

---

## 🚀 Tech Stack

- **Backend:** Python, Django, Django Channels, Daphne (ASGI Server)
- **Real-time:** WebSockets (`AsyncWebsocketConsumer`), Channel Layers
- **Database:** PostgreSQL (`psycopg`)
- **Environment Management:** `python-dotenv`
- **Frontend:** HTML5, Vanilla JavaScript (WebSocket API)

---

## 📁 Project Structure

```text
WepSocketTemplate/
├── apps/               # Django app containing WebSocket consumers and routing
│   ├── consumers.py    # Async WebSocket consumer for real-time chat
│   └── routing.py      # WebSocket URL routing definitions
├── templates/          # HTML templates
│   └── chat.html       # Client-side WebSocket chat interface
├── WepSocketTemplate/  # Project configuration
│   ├── asgi.py         # ASGI application entry point (Daphne/Channels)
│   ├── settings.py     # Django settings & database configuration
│   ├── urls.py         # HTTP URL routing
│   └── wsgi.py         # WSGI application entry point
├── manage.py           # Django management script
├── requirement.txt     # Python package dependencies
└── .env_example        # Environment variable template
```

---

## 🛠️ Getting Started

### 1. Prerequisites
- Python 3.10+ (tested with Python 3.14)
- PostgreSQL

### 2. Clone the Repository
```bash
git clone https://github.com/your-username/WepSocketTemplate.git
cd WepSocketTemplate
```

### 3. Create & Activate Virtual Environment
```bash
python -m venv .venv
source .venv/bin/activate  # On Windows use: .venv\Scripts\activate
```

### 4. Install Dependencies
```bash
pip install -r requirement.txt
```

### 5. Configure Environment Variables
Copy `.env_example` to `.env` and fill in your PostgreSQL credentials:
```bash
cp .env_example .env
```

Open `.env` and update your database details:
```env
DB_NAME=your_db_name
DB_USER=your_db_user
DB_PASSWORD=your_db_password
DB_HOST=localhost
DB_PORT=5432
```

### 6. Run Database Migrations
```bash
python manage.py migrate
```

### 7. Run the Development Server
You can run the application using **Daphne** (recommended for ASGI/WebSockets):
```bash
daphne WepSocketTemplate.asgi:application
```
Alternatively, Django's built-in development server also supports ASGI via Channels:
```bash
python manage.py runserver
```

---

## 💬 Usage / Testing

1. Open your browser and navigate to `http://127.0.0.1:8000/` (or your configured host). *(Note: Add views/urls mapping to `chat.html` if required)*
2. Open multiple browser tabs to test real-time broadcasting across connected WebSocket clients via `ChatConsumer`.

---

## 📜 License
This project is open-source and available under the [MIT License](LICENSE).
