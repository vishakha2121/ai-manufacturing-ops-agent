# 🚀 AI Manufacturing Operations Agent

> An intelligent, autonomous agent that **coordinates production schedules**, **predicts equipment bottlenecks**, **optimizes resource allocation**, and **minimizes production downtime** — powered by IoT, Reinforcement Learning, Optimization Algorithms, and Google Gemini LLM.

![Status](https://img.shields.io/badge/status-active-brightgreen)
![Python](https://img.shields.io/badge/python-3.10+-blue)
![FastAPI](https://img.shields.io/badge/FastAPI-0.110+-009688)
![React](https://img.shields.io/badge/react-18-61dafb)
![License](https://img.shields.io/badge/license-MIT-yellow)
![Made with ❤️](https://img.shields.io/badge/made%20with-%E2%9D%A4-red)

---

## 📌 Table of Contents

- [Overview](#-overview)
- [Problem Statement](#-problem-statement)
- [Key Features](#-key-features)
- [System Architecture](#-system-architecture)
- [Tech Stack](#-tech-stack)
- [Project Structure](#-project-structure)
- [Database Schema](#-database-schema)
- [API Endpoints](#-api-endpoints)
- [Installation & Setup](#-installation--setup)
- [Environment Variables](#-environment-variables)
- [How It Works](#-how-it-works)
- [Screenshots](#-screenshots)
- [Roadmap](#-roadmap)
- [Learning Outcomes](#-learning-outcomes)
- [Author](#-author)
- [License](#-license)

---

## 🧠 Overview

**AI Manufacturing Operations Agent** is an end-to-end intelligent system that acts as an **autonomous operations manager** for a smart factory. It ingests real-time IoT sensor data from machines, predicts bottlenecks and failures using Machine Learning, optimizes production schedules using Linear Programming, and learns adaptive job-assignment policies via Reinforcement Learning. A **Gemini-powered AI agent** provides natural-language insights and recommendations via an interactive chat interface.

The system features a **modern React dashboard** with live WebSocket updates, interactive Gantt charts, real-time alerts, and AI chat — all built to run efficiently on **CPU-only hardware** for practice and portfolio purposes.

---

## 🎯 Problem Statement

Modern manufacturing plants face critical challenges:

| Problem | Impact |
|---------|--------|
| **Unplanned machine downtime** | 💸 Heavy revenue loss per hour |
| **Poor production scheduling** | ⏳ Idle machines & delayed orders |
| **Bottleneck detection delays** | 🐢 Slower throughput |
| **Reactive maintenance** | 🔧 Higher repair costs |
| **Manual resource allocation** | ❌ Human error-prone decisions |

**Solution:** An AI agent that **predicts, optimizes, and coordinates** everything in real-time.

---

## ✨ Key Features

### 🏭 1. Production Schedule Coordination
- Auto-generates optimal job-to-machine assignments
- Respects capacity, priority, and deadline constraints
- Linear Programming (PuLP) based scheduler
- Interactive **Gantt chart** visualization

### ⚠️ 2. Equipment Bottleneck Prediction
- Random Forest / XGBoost based prediction model
- Real-time risk scoring per machine
- Color-coded alert system (Low / Medium / High risk)
- Historical trend analysis

### ⚙️ 3. Resource Allocation Optimization
- Balances workers, machines, and time slots
- Multi-objective optimization (throughput vs. cost)
- Dynamic re-allocation on disruptions

### 🛑 4. Downtime Minimization
- Predictive failure alerts (before breakdown)
- RL-based maintenance scheduling
- Downtime risk gauge per machine
- Root-cause analysis dashboard

### 🤖 5. Reinforcement Learning Agent
- Custom Q-Learning / DQN environment
- Learns optimal job-assignment policy
- Training progress visualization (reward curves)
- Episode playback controls

### 💬 6. Gemini AI Assistant
- Natural language Q&A: *"Why is Machine B2 slow?"*
- Auto-generated daily operational summaries
- Proactive recommendations
- Chat history stored in DB

### 📡 7. IoT Sensor Simulation
- 10+ virtual machines streaming live data
- Metrics: temperature, vibration, RPM, status, uptime
- WebSocket-based real-time updates (2-3 sec interval)
- Simulates realistic anomalies

### 📊 8. Real-Time Dashboard
- Live machine status cards
- Streaming sensor charts (Recharts)
- Alert banner for critical issues
- Factory-wide KPI stats

---

## 🏗️ System Architecture

```
┌──────────────────────────────────────────────────────────────────┐
│                      REACT FRONTEND (Vite)                       │
│   Dashboard │ Predictions │ Scheduler │ RL Agent │ Chat UI       │
└──────────────────────────┬───────────────────────────────────────┘
                           │ REST + WebSocket
                           ▼
┌──────────────────────────────────────────────────────────────────┐
│                    FASTAPI BACKEND (Python)                      │
│                                                                  │
│  ┌─────────────┐  ┌──────────────┐  ┌──────────────────┐         │
│  │ IoT         │  │ ML           │  │ Optimization     │         │
│  │ Simulator   │→ │ Predictor    │→ │ Engine (PuLP)    │         │
│  └─────────────┘  └──────────────┘  └──────────────────┘         │
│                                                                  │
│  ┌─────────────┐  ┌──────────────┐  ┌──────────────────┐         │
│  │ RL Agent    │  │ Gemini LLM   │  │ WebSocket        │         │
│  │ (Q-Learning)│  │ Agent        │  │ Manager          │         │
│  └─────────────┘  └──────────────┘  └──────────────────┘         │
└──────────────────────────┬───────────────────────────────────────┘
                           │ SQLAlchemy ORM
                           ▼
┌──────────────────────────────────────────────────────────────────┐
│              MYSQL DATABASE (schema + seed data)                 │
│  machines │ sensor_readings │ jobs │ schedules │ predictions     │
│  alerts   │ rl_episodes     │ chat_history                       │
└──────────────────────────────────────────────────────────────────┘
```

---

## 🛠️ Tech Stack

| Layer | Technology | Purpose |
|-------|-----------|---------|
| **Backend** | Python 3.10+ | Core language |
| **API Framework** | FastAPI + Uvicorn | REST + WebSocket server |
| **ORM** | SQLAlchemy | Database abstraction |
| **Database** | MySQL | Persistent storage |
| **ML** | scikit-learn, XGBoost | Bottleneck & failure prediction |
| **Optimization** | PuLP / Google OR-Tools | Linear Programming scheduler |
| **RL** | Custom Q-Learning / Stable-Baselines3 | Adaptive policy learning |
| **LLM** | Google Gemini API (`google-generativeai`) | Natural language insights |
| **Frontend** | React 18 + Vite | UI framework |
| **Styling** | TailwindCSS + shadcn/ui | Modern design system |
| **Animations** | Framer Motion | Smooth transitions |
| **Charts** | Recharts | Live data visualization |
| **Icons** | Lucide React | Clean icon set |
| **Routing** | React Router v6 | Client-side routing |
| **HTTP Client** | Axios | API calls |
| **Real-time** | WebSocket (native) | Live updates |

---

## 📁 Project Structure

```
ai-manufacturing-ops-agent/
│
├── README.md
├── LICENSE
├── .gitignore
├── docker-compose.yml
│
├── backend/
│   ├── requirements.txt
│   ├── .env.example
│   ├── main.py
│   ├── config.py
│   │
│   ├── database/
│   │   ├── __init__.py
│   │   ├── db.py
│   │   ├── models.py
│   │   └── schema.sql
│   │
│   ├── api/
│   │   ├── __init__.py
│   │   ├── machines.py
│   │   ├── sensors.py
│   │   ├── predictions.py
│   │   ├── optimization.py
│   │   ├── rl_agent.py
│   │   ├── chat.py
│   │   └── websocket.py
│   │
│   ├── services/
│   │   ├── __init__.py
│   │   ├── iot_simulator.py
│   │   ├── bottleneck_predictor.py
│   │   ├── scheduler_optimizer.py
│   │   ├── rl_environment.py
│   │   ├── rl_trainer.py
│   │   ├── gemini_agent.py
│   │   └── downtime_analyzer.py
│   │
│   ├── ml_models/
│   │   ├── __init__.py
│   │   ├── train_bottleneck.py
│   │   ├── train_failure.py
│   │   └── saved_models/
│   │       └── .gitkeep
│   │
│   ├── utils/
│   │   ├── __init__.py
│   │   ├── logger.py
│   │   ├── helpers.py
│   │   └── constants.py
│   │
│   ├── data/
│   │   └── seed_data.py
│   │
│   └── tests/
│       ├── __init__.py
│       ├── test_machines.py
│       ├── test_predictions.py
│       └── test_optimization.py
│
├── frontend/
│   ├── package.json
│   ├── vite.config.js
│   ├── tailwind.config.js
│   ├── postcss.config.js
│   ├── index.html
│   ├── .env.example
│   │
│   └── src/
│       ├── main.jsx
│       ├── App.jsx
│       ├── index.css
│       ├── assets/
│       ├── api/
│       ├── components/
│       │   ├── layout/
│       │   ├── dashboard/
│       │   ├── predictions/
│       │   ├── scheduler/
│       │   ├── rl/
│       │   ├── chat/
│       │   └── ui/
│       ├── pages/
│       ├── hooks/
│       ├── context/
│       ├── routes/
│       ├── utils/
│       └── styles/
│
└── database/
    ├── schema.sql
    ├── seed.sql
    └── er_diagram.md
```

---

## 🗄️ Database Schema

| Table | Purpose | Key Columns |
|-------|---------|-------------|
| `machines` | Machine master data | id, name, type, capacity, status |
| `sensor_readings` | Live IoT data | id, machine_id, temperature, vibration, rpm, timestamp |
| `jobs` | Production orders | id, product, quantity, priority, deadline |
| `schedules` | Optimized schedule | id, job_id, machine_id, start_time, end_time |
| `predictions` | ML prediction results | id, machine_id, bottleneck_score, failure_probability |
| `alerts` | Warning logs | id, machine_id, severity, message, created_at |
| `rl_episodes` | RL training logs | id, episode, reward, epsilon, timestamp |
| `chat_history` | Gemini conversation | id, user_message, ai_response, timestamp |

---

## 🔌 API Endpoints

### Machines
| Method | Endpoint | Description |
|--------|----------|-------------|
| GET | `/api/machines` | List all machines |
| GET | `/api/machines/{id}` | Get machine details |
| POST | `/api/machines` | Add new machine |
| PUT | `/api/machines/{id}` | Update machine |

### Sensors
| Method | Endpoint | Description |
|--------|----------|-------------|
| GET | `/api/sensors/live` | Latest sensor readings |
| GET | `/api/sensors/{machine_id}/history` | Historical data |
| WS | `/ws/sensors` | Live WebSocket stream |

### Predictions
| Method | Endpoint | Description |
|--------|----------|-------------|
| GET | `/api/predictions/bottleneck` | Bottleneck risk for all machines |
| GET | `/api/predictions/failure/{machine_id}` | Failure probability |
| POST | `/api/predictions/retrain` | Retrain ML models |

### Optimization
| Method | Endpoint | Description |
|--------|----------|-------------|
| POST | `/api/optimize/schedule` | Generate optimized schedule |
| GET | `/api/optimize/schedule/latest` | Get latest schedule |
| GET | `/api/optimize/allocate` | Resource allocation plan |

### Reinforcement Learning
| Method | Endpoint | Description |
|--------|----------|-------------|
| POST | `/api/rl/train` | Start training episode |
| GET | `/api/rl/status` | Training progress |
| GET | `/api/rl/episodes` | Episode history |

### AI Chat
| Method | Endpoint | Description |
|--------|----------|-------------|
| POST | `/api/agent/chat` | Send message to Gemini |
| GET | `/api/agent/chat/history` | Chat history |
| POST | `/api/agent/summary` | Generate daily summary |

---

## 🚀 Installation & Setup

### Prerequisites
- Python 3.10+
- Node.js 18+
- MySQL 8.0+
- Git
- Google Gemini API Key → [Get here](https://aistudio.google.com/apikey)

### 1️⃣ Clone the Repository

```bash
git clone https://github.com/vishakha2121/ai-manufacturing-ops-agent.git
cd ai-manufacturing-ops-agent
```

### 2️⃣ Backend Setup

```bash
cd backend

# Create virtual environment
python -m venv venv

# Activate it
# Windows:
venv\Scripts\activate
# Mac/Linux:
source venv/bin/activate

# Install dependencies
pip install -r requirements.txt

# Setup environment variables
copy .env.example .env    # Windows
# cp .env.example .env    # Mac/Linux
# Edit .env and add your Gemini API key + DB credentials
```

### 3️⃣ Database Setup

```bash
# Login to MySQL
mysql -u root -p

# Create database
CREATE DATABASE manufacturing_ops;
USE manufacturing_ops;

# Run schema
source ../database/schema.sql;

# Load seed data (optional)
source ../database/seed.sql;
```

### 4️⃣ Run Backend Server

```bash
# Still inside backend/ with venv activated
uvicorn main:app --reload --port 8000
```

Backend will run at → **http://localhost:8000**
API docs → **http://localhost:8000/docs**

### 5️⃣ Frontend Setup

```bash
# Open new terminal
cd frontend

# Install dependencies
npm install

# Setup env
copy .env.example .env

# Run dev server
npm run dev
```

Frontend will run at → **http://localhost:5173**

### 6️⃣ Access the Application

| Service | URL |
|---------|-----|
| Frontend Dashboard | http://localhost:5173 |
| Backend API | http://localhost:8000 |
| Swagger Docs | http://localhost:8000/docs |

---

## 🔐 Environment Variables

### `backend/.env`

```env
# Database
DB_HOST=localhost
DB_PORT=3306
DB_USER=root
DB_PASSWORD=your_mysql_password
DB_NAME=manufacturing_ops

# Gemini API
GEMINI_API_KEY=your_gemini_api_key_here
GEMINI_MODEL=gemini-1.5-flash

# Server
BACKEND_PORT=8000
FRONTEND_URL=http://localhost:5173

# IoT Simulator
SIMULATOR_INTERVAL=3
NUM_MACHINES=10
```

### `frontend/.env`

```env
VITE_API_BASE_URL=http://localhost:8000
VITE_WS_URL=ws://localhost:8000/ws
```

> ⚠️ **NEVER commit `.env` files to GitHub.** They are already in `.gitignore`.

---

## ⚙️ How It Works

### 🔄 Data Flow

1. **IoT Simulator** generates fake sensor data every 3 seconds → stored in MySQL
2. **ML Predictor** analyzes the latest data → predicts bottleneck & failure risk
3. **Optimization Engine** takes pending jobs + machine state → generates optimal schedule
4. **RL Agent** learns from simulation → improves job-assignment policy over time
5. **Gemini LLM** explains insights in natural language
6. **WebSocket** pushes all updates to React dashboard in real-time

### 🧠 ML Pipeline

```
Raw Sensor Data → Feature Engineering → Trained Model (.pkl) → Prediction API
```

- **Model**: Random Forest Classifier
- **Features**: avg temperature, vibration trend, uptime %, error count
- **Target**: `is_bottleneck` (0 or 1)
- **Training**: Weekly retrain via `/api/predictions/retrain`

### 🎯 Optimization Pipeline

```
Pending Jobs + Machine Constraints → PuLP LP Solver → Optimal Schedule → Gantt Chart
```

- **Objective**: Minimize total completion time (makespan)
- **Constraints**: Machine capacity, job priority, deadlines

### 🤖 RL Pipeline

```
Environment (State) → Agent (Q-Table) → Action → Reward → Update Policy → Repeat
```

- **State**: Machine statuses + pending jobs + time
- **Actions**: Assign job / Schedule maintenance / Wait
- **Reward**: `+throughput − downtime_cost − idle_time`
- **Algorithm**: Q-Learning (tabular, CPU-friendly)

---

## 📸 Screenshots

> _Add screenshots here after building the UI._

| Page | Preview |
|------|---------|
| Dashboard | ![Dashboard](docs/screenshots/dashboard.png) |
| Predictions | ![Predictions](docs/screenshots/predictions.png) |
| Scheduler | ![Scheduler](docs/screenshots/scheduler.png) |
| RL Agent | ![RL Agent](docs/screenshots/rl-agent.png) |
| Chat | ![Chat](docs/screenshots/chat.png) |

---

## 🗺️ Roadmap

- [x] Project planning & folder structure
- [ ] IoT simulator with 10 machines
- [ ] MySQL schema + seed data
- [ ] FastAPI base + machine APIs
- [ ] Bottleneck prediction ML model
- [ ] PuLP-based scheduler
- [ ] Q-Learning RL agent
- [ ] Gemini chat integration
- [ ] React dashboard UI
- [ ] WebSocket live updates
- [ ] Gantt chart visualization
- [ ] Deployment (local Docker)

---

## 🎓 Learning Outcomes

Through this project, the following were explored:

- ✅ End-to-end **full-stack AI application** development
- ✅ **IoT data simulation** & streaming architecture
- ✅ **Machine Learning** for predictive maintenance
- ✅ **Reinforcement Learning** for adaptive scheduling
- ✅ **Linear Programming** for resource optimization
- ✅ **LLM integration** (Gemini) for natural language UX
- ✅ **Real-time WebSocket** communication
- ✅ **Modern React** with TailwindCSS + Framer Motion
- ✅ **Database design** for time-series + operational data

---

## 👩‍💻 Author

**Vishakha**
- GitHub: [@vishakha2121](https://github.com/vishakha2121)
- Project Repo: [ai-manufacturing-ops-agent](https://github.com/vishakha2121/ai-manufacturing-ops-agent)

---

## 📄 License

This project is licensed under the **MIT License** — see the [LICENSE](LICENSE) file for details.

---

## 🙏 Acknowledgements

- [FastAPI](https://fastapi.tiangolo.com/) — modern Python web framework
- [React](https://react.dev/) + [Vite](https://vitejs.dev/) — blazing fast frontend
- [TailwindCSS](https://tailwindcss.com/) — utility-first CSS
- [scikit-learn](https://scikit-learn.org/) — ML made simple
- [PuLP](https://coin-or.github.io/pulp/) — LP optimization
- [Google Gemini](https://ai.google.dev/) — LLM reasoning

---

<div align="center">

**⭐ If you found this project useful, please give it a star! ⭐**

Made with ❤️ by **Vishakha**

</div>