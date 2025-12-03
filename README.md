# 🌍 Seasonal Travel Recommender 🌦️

Welcome to the **Seasonal Travel Recommender**! This multi-agent travel planning assistant is designed to help you explore the beautiful landscapes of Sri Lanka, providing personalized recommendations based on weather, activities, and packing lists.

## 📦 Features

- **Multi-Agent System**: 
  - Orchestrator, Location, Activity, Packing, and Summary agents work together for comprehensive planning.
  
- **Resumable Workflow**: 
  - The system intelligently gathers missing information by asking follow-up questions, ensuring a smooth planning experience.

- **Interactive Chat Interface**: 
  - Engage in real-time conversations to plan your trip with a user-friendly chat interface.

- **Structured Data Extraction**: 
  - Easily extract trip details including destination, dates, traveler count, trip type, and preferences.

- **Knowledge Base**: 
  - Utilize a vector store-based knowledge base with FAISS/Chroma indexes for contextual recommendations.

- **Conversation History**: 
  - Persistent storage of conversation history with automatic title generation for easy retrieval.

## 🚀 Technology Stack

- **Backend**: 
  - Python 3.11+, FastAPI, LangGraph, Pydantic, OpenAI API, MongoDB

- **Frontend**: 
  - React, Vite, JavaScript

- **Database**: 
  - MongoDB for conversation history and user data

- **Knowledge Base**: 
  - FAISS/Chroma vector stores

- **Authentication**: 
  - JWT

- **Deployment**: 
  - Docker support available

## 📚 Installation

To get started with the Seasonal Travel Recommender, follow these steps:

1. Clone the repository:
   ```bash
   git clone https://github.com/DewduSendanayake/Seasonal_Travel_Recommender.git
   ```

2. Navigate to the project directory:
   ```bash
   cd Seasonal_Travel_Recommender
   ```

3. Install the required dependencies:
   ```bash
   pip install -r requirements.txt
   ```

4. Run the application:
   ```bash
   uvicorn main:app --reload
   ```

5. Open your browser and go to `http://localhost:8000`.

## 🎉 Contributing

We welcome contributions! If you have suggestions or improvements, feel free to fork the repository and submit a pull request.

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 🤝 Acknowledgments

- Thanks to the contributors and community for their valuable feedback and support!
- Special thanks to the libraries and tools that made this project possible.

---

Happy traveling! ✈️🌴
