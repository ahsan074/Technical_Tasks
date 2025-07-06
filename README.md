# Technical_Tasks

🧠 FastAPI-Based Intelligent Agent
📌 Overview
This project is a FastAPI-based intelligent agent designed as part of a data engineering internship project. It includes:

A tool-augmented agent that uses external APIs to respond to user prompts.

Modular architecture with tool abstraction.

Local and Docker-based deployment.

An automated evaluation setup.

A conceptual write-up on agent behavior and design choices.

📁 Project Structure
├── part1/                    # Core application
│   ├── main.py               # FastAPI app
│   ├── agent.py              # Agent logic and tool calling
│   ├── system_prompt.py      # System prompt for LLM behavior
│   ├── tools/                # Tool modules
│   │   ├── weather_api.py
│   │   └── wikipedia_tool.py
│   ├── requirements.txt
│   ├── .env                  # API keys (not tracked in Git)
│   └── README.md             # Setup instructions
│
├── part2/                    # Dockerization
│   ├── Dockerfile
│   ├── .dockerignore
│   └── README.md             # Docker usage
│
├── part3/
│   └── ANSWERS.md            # Answers for agent correctness and prompt design

🚀 Features Implemented
✅ Weather API Tool (based on WeatherAPI.com)

✅ Wikipedia Summary Tool (via Wikipedia package)

✅ Robust Fallback Handling

✅ System Prompt Enforcement

✅ FastAPI Backend

✅ Docker Containerization

✅ Railway Deployment (Optional)

✅ Environment Variable Management

✅ Modular Code & Tool Abstraction

✅ Answer Sheet for Conceptual Questions (Part 3)


🛠 How to Use the Project
🔧 Local Setup (Part 1)
cd part1
python -m venv venv
venv\Scripts\activate      # Windows
pip install -r requirements.txt

Add your API keys in a .env file
WEATHER_API_KEY=your_weather_key
HF_API_KEY=your_huggingface_key   # If using LLM

Start the FastAPI server:
uvicorn main:app --reload

Test it:
curl -X POST http://127.0.0.1:8000/agent \
  -H "Content-Type: application/json" \
  -d "{\"prompt\": \"What's the weather in Lahore?\"}"

🐳 Docker Deployment (Part 2)
cd part2
docker build -t agent-service .
docker run -p 8000:8000 agent-service


🌐 Cloud Deployment 
The project was tested with Railway for deployment. 
You can choose Railway, Render, or Hugging Face Spaces (if LLM involved). 
Be sure to add environment variables on the platform dashboard for secure API key handling.


📘 Conceptual Design (Part 3)
Find full explanations in part3/ANSWERS.md. Highlights include:

How to detect incorrect or stale outputs.

Techniques for prompt engineering and enforcing agent behavior.

Understanding tool abstraction for modularity and extensibility.



