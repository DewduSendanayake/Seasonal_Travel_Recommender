# 🌴 Seasonal Travel Recommender for Sri Lanka 🌴 

> An intelligent multi-agent travel planning assistant powered by LangGraph that helps you discover the best of Sri Lanka based on weather, seasons, and your personal preferences.

[![Python](https://img.shields.io/badge/Python-3.11+-blue.svg)](https://www.python.org/downloads/)
[![FastAPI](https://img.shields.io/badge/FastAPI-Latest-green.svg)](https://fastapi.tiangolo.com/)
[![React](https://img.shields.io/badge/React-19.1+-61DAFB.svg)](https://reactjs.org/)
[![LangGraph](https://img.shields.io/badge/LangGraph-Latest-orange.svg)](https://github.com/langchain-ai/langgraph)

---

## ✨ What is This?

The **Seasonal Travel Recommender** is a sophisticated AI-powered travel assistant specifically designed for Sri Lanka tourism. Using a multi-agent architecture built with LangGraph, it provides personalized travel recommendations by analyzing weather patterns, seasonal conditions, and user preferences.

### 🎯 Key Highlights

- **9 Specialized AI Agents** working in perfect orchestration
- **Weather-Aware Recommendations** based on Sri Lanka's monsoon seasons
- **Interactive Chat Interface** for natural conversation planning
- **Location Intelligence** with vector-based knowledge stores
- **Smart Packing Lists** tailored to your destination and season
- **Day-by-Day Activity Planning** customized to your preferences
- **Resumable Planning Sessions** with conversation history
- **Secure Authentication** with JWT tokens

---

## 🏗️ Architecture

The system uses a **LangGraph-based state machine** with multiple specialized agents:

### Intelligent Agent Network

| Agent | Role | Function |
|-------|------|----------|
| 🎯 **Router Agent** | Traffic Controller | Classifies user intent and routes to appropriate agent |
| 🎭 **Orchestrator Agent** | Data Extraction | Extracts trip details (destination, dates, preferences, budget) |
| 📍 **Location Agent** | Destination Recommendations | Suggests locations based on season and preferences using RAG |
| 🎡 **Activity Agent** | Activity Planning | Generates day-by-day activity suggestions |
| 🎒 **Packing Agent** | Packing Lists | Creates customized packing lists based on weather and activities |
| 🌧️ **Weather Agent** | Weather Intelligence | Provides seasonal weather insights for Sri Lanka |
| 💬 **Chat Agent** | General Conversation | Handles casual questions and general travel queries |
| 🔍 **Explorer Agent** | Knowledge Retrieval | RAG-based search through travel knowledge base |
| 🎨 **Summary Agent** | Itinerary Generation | Creates polished, formatted trip summaries |

### 📊 Workflow Flow

```
User Query → Router → Orchestrator (if planning) → Location → Activity → Packing → Summary
                 ↓
              Chat Agent (for casual queries)
                 ↓
           Explorer Agent (for knowledge queries)
```

---

## 🛠️ Technology Stack

### Backend
- **Framework**: FastAPI (Python 3.11+)
- **AI Orchestration**: LangGraph, LangChain
- **LLM**: OpenAI API (GPT-3.5/4) & Google Gemini
- **Vector Stores**: FAISS & Chroma for RAG
- **Database**: MongoDB (conversation history & user data)
- **Validation**: Pydantic for data schemas
- **Authentication**: JWT tokens

### Frontend
- **Framework**: React 19.1 + Vite
- **Styling**: TailwindCSS 4.1
- **Routing**: React Router v6
- **Icons**: Heroicons & Lucide React
- **Markdown**: React Markdown with GFM support
- **HTTP Client**: Axios

### Infrastructure
- **Containerization**: Docker support
- **Deployment**: Vercel-ready configuration
- **CORS**: Configured for local and production environments

---

## 📦 Installation & Setup

### Prerequisites
- Python 3.11 or higher
- Node.js 18+ and npm
- MongoDB instance (local or cloud)
- OpenAI API key and/or Google Gemini API key

### 1️⃣ Clone the Repository
```bash
git clone https://github.com/DewduSendanayake/Seasonal_Travel_Recommender.git
cd Seasonal_Travel_Recommender
```

### 2️⃣ Backend Setup

#### Install Python Dependencies
```bash
pip install -r requirements.txt
```

#### Configure Environment Variables
Create a `.env` file in the root directory:
```env
# API Keys
OPENAI_API_KEY=your_openai_api_key_here
GOOGLE_API_KEY=your_gemini_api_key_here

# MongoDB
MONGODB_URI=mongodb://localhost:27017/
DATABASE_NAME=seasonal_travel_recommender

# JWT Secret
SECRET_KEY=your_secret_key_here

# CORS Origins (comma-separated)
CORS_ORIGINS=http://localhost:5173,http://localhost:3000
```

#### Run the Backend Server
```bash
# From the project root
uvicorn server.api.main:app --reload --host 0.0.0.0 --port 8000
```

The API will be available at `http://localhost:8000`

### 3️⃣ Frontend Setup

#### Install Dependencies
```bash
cd client
npm install
```

#### Run the Development Server
```bash
npm run dev
```

The frontend will be available at `http://localhost:5173`

### 4️⃣ Access the Application
Open your browser and navigate to `http://localhost:5173` to start planning your Sri Lankan adventure! 🎉

---

## 🚀 Usage Examples

### Example 1: Full Trip Planning
```
User: "I want to plan a family trip to Sri Lanka in December"
System: Asks for missing details (dates, number of travelers, preferences)
User: Provides information interactively
System: Generates complete itinerary with locations, activities, and packing list
```

### Example 2: Quick Location Query
```
User: "What are the best beaches in Sri Lanka during October?"
System: Provides location recommendations with weather insights
```

### Example 3: Activity Suggestions
```
User: "What activities can we do in Ella?"
System: Suggests activities based on location and season
```

---

## 📁 Project Structure

```
Seasonal_Travel_Recommender/
├── server/                      # Backend (Python/FastAPI)
│   ├── agents/                  # AI Agent implementations
│   │   ├── activity_agent/
│   │   ├── chat_agent/
│   │   ├── decision_agent/
│   │   ├── explorer_agent/
│   │   ├── location_agent/
│   │   ├── orchestrator_agent/
│   │   ├── packing_agent/
│   │   ├── summary_agent/
│   │   └── weather_agent/
│   ├── api/                     # FastAPI routes
│   │   ├── main.py             # App entry point
│   │   ├── route.py            # Chat endpoints
│   │   ├── auth.py             # Authentication
│   │   └── conversations.py    # History management
│   ├── workflow/                # LangGraph workflow
│   │   ├── workflow.py         # State machine definition
│   │   ├── agent_nodes.py      # Agent node functions
│   │   └── app_state.py        # State schema
│   ├── schemas/                 # Pydantic models
│   ├── utils/                   # Utilities (DB, helpers)
│   ├── data/                    # Knowledge base data
│   └── tools/                   # Custom tools
├── client/                      # Frontend (React/Vite)
│   ├── src/
│   │   ├── components/
│   │   ├── pages/
│   │   └── App.jsx
│   ├── package.json
│   └── vite.config.js
├── requirements.txt             # Python dependencies
├── README.md                    # This file
├── LICENSE                      # MIT License
└── .gitignore
```

---

## 🔒 Environment Variables

| Variable | Description | Required |
|----------|-------------|----------|
| `OPENAI_API_KEY` | OpenAI API key for GPT models | Yes |
| `GOOGLE_API_KEY` | Google Gemini API key | Optional |
| `MONGODB_URI` | MongoDB connection string | Yes |
| `DATABASE_NAME` | MongoDB database name | Yes |
| `SECRET_KEY` | JWT secret for authentication | Yes |
| `CORS_ORIGINS` | Allowed CORS origins | No (defaults provided) |

---

## 🌟 Features in Detail

### 🔄 Resumable Workflow
The orchestrator intelligently manages missing information:
- Asks focused follow-up questions
- Maintains conversation context
- Automatically fills in defaults where appropriate
- Supports multi-turn conversations

### 🗺️ Knowledge-Based Recommendations
Uses vector stores (FAISS/Chroma) for:
- Contextual location suggestions
- Weather-aware destination filtering
- Activity recommendations based on interests

### 📊 Structured Data Extraction
Automatically extracts:
- 📍 Destination
- 📅 Travel dates (start & end)
- 👥 Number of travelers
- 🌦️ Season (auto-detected from dates)
- 💰 Budget preferences
- 🎯 Trip type (leisure, adventure, cultural, etc.)
- ❤️ User preferences and interests

### 💾 Conversation History
- Persistent storage in MongoDB
- Automatic title generation for conversations
- Easy retrieval of past planning sessions

---

## 🐳 Docker Support

```bash
# Build the Docker image
docker build -t seasonal-travel-recommender .

# Run the container
docker run -p 8000:8000 -e OPENAI_API_KEY=your_key seasonal-travel-recommender
```

---

## 🤝 Contributing

Contributions are welcome! Here's how you can help:

1. 🍴 Fork the repository
2. 🌿 Create a feature branch (`git checkout -b feature/amazing-feature`)
3. ✍️ Commit your changes (`git commit -m 'Add amazing feature'`)
4. 📤 Push to the branch (`git push origin feature/amazing-feature`)
5. 🎉 Open a Pull Request

### Areas for Contribution
- 🗺️ Additional location data for Sri Lanka
- 🌦️ Improved weather prediction models
- 🎨 UI/UX improvements
- 📝 Documentation enhancements
- 🧪 Test coverage

---

## 📄 License

This project is licensed under the **MIT License** - see the [LICENSE](LICENSE) file for details.

---

## 🙏 Acknowledgments

- 🎓 Built with [LangGraph](https://github.com/langchain-ai/langgraph) and [LangChain](https://github.com/langchain-ai/langchain)
- 🤖 Powered by OpenAI and Google Gemini
- 🎨 UI components inspired by modern design patterns
- 🌍 Special thanks to the Sri Lankan tourism community for knowledge base contributions
- 💙 Thanks to all contributors and supporters!

---

## 📞 Support & Contact

- 🐛 **Issues**: [GitHub Issues](https://github.com/DewduSendanayake/Seasonal_Travel_Recommender/issues)
- 💬 **Discussions**: [GitHub Discussions](https://github.com/DewduSendanayake/Seasonal_Travel_Recommender/discussions)
- 👥 **Authors**: [DewduSendanayake](https://github.com/DewduSendanayake), [dulhara79](https://github.com/dulhara79), [UVINDUSEN](https://github.com/UVINDUSEN), [SENUVI20](https://github.com/SENUVI20)

---

<div align="center">

### 🌴 Happy Traveling! Enjoy the Pearl of the Indian Ocean! 🌊

Made with ❤️ for Sri Lanka travelers

</div>
