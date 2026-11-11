# 🌾 AI Agent for Smart Farming Advice
### IBM University Engagement Project — Problem Statement #9

> An AI Agent for Smart Farming Advice powered by **RAG (Retrieval-Augmented Generation)** and **IBM Granite**, delivering real-time, localized agricultural guidance to small-scale farmers.

---

## 👨‍💻 Author
| Field | Details |
|-------|---------|
| **Name** | Vedant Varshney |
| **Email** | vedantvarshney958@gmail.com |
| **Phone** | +91-7900427390 |
| **Domain** | Agriculture / AgriTech / Smart Farming |

---

## 📋 Problem Statement
Small-scale farmers in rural areas face critical knowledge gaps in accessing real-time, localized agricultural guidance. Information about weather forecasts, soil conditions, crop recommendations, pest control, and market prices is fragmented and inaccessible.

**This AI Agent bridges the knowledge gap by delivering:**
- 🌦️ Real-time weather forecasts & crop advisories
- 🌱 Soil-type based crop recommendations
- 🐛 Pest identification & control guidance
- 📈 Live mandi (market) price intelligence
- 🗣️ Multilingual interaction in regional Indian languages

---

## 🏗️ Architecture

```
Farmer Query (Multilingual Chat UI)
          │
          ▼
IBM Watsonx AI Agent (Orchestrator) — ibm/granite-3-3-8b-instruct
          │
    ┌─────┼──────┬──────┐
    ▼     ▼      ▼      ▼
Weather  Soil  Pest  Market
Agent    Agent Agent  Agent
    │     │      │      │
    ▼     ▼      ▼      ▼
OpenWx  AgriDB PestDB Agmarknet
API     RAG    RAG    API
    └─────┴──────┴──────┘
          │
          ▼
Response Aggregator
          │
          ▼
IBM Granite — Final Response Generation
          │
          ▼
Farmer receives answer in local language
```

---

## 🛠️ Technologies Used

| Technology | Purpose |
|------------|---------|
| **IBM Granite** (`ibm/granite-3-3-8b-instruct`) | Natural language understanding & generation |
| **IBM watsonx.ai** | Model deployment, embeddings, AI governance |
| **IBM Cloud Lite** | Hosting, scaling, security |
| **LangFlow** | Multi-agent workflow orchestration |
| **FAISS / Chroma** | Vector database for RAG |
| **OpenWeather API** | Real-time weather data |
| **Agmarknet API** | Live mandi price data |
| **Streamlit** | Farmer-facing web dashboard |

---

## 🤖 Agents

### 1. 🌦️ Weather & Forecast Agent
Retrieves real-time weather forecasts and provides crop-specific advisories like irrigation timing, frost alerts, and sowing windows.

### 2. 🌱 Soil & Crop Advisory Agent
Analyzes soil type (black cotton, red, alluvial) and seasonal data to recommend the best crops with fertilizer and irrigation schedules.

### 3. 🐛 Pest Control Agent
Identifies pests from farmer descriptions and suggests organic/chemical remedies with safety guidelines using RAG over trusted agricultural databases.

### 4. 📈 Market Price Agent
Delivers live mandi rates from Agmarknet — minimum, maximum, and modal price per quintal — helping farmers decide the best time to sell.

---

## 🚀 Setup Instructions

### Prerequisites
- Python 3.9+
- IBM Cloud Lite account (free at [ibm.com/cloud/free](https://ibm.com/cloud/free))
- LangFlow installed (`pip install langflow`)

### Installation

```bash
git clone https://github.com/Vedant958/farming_project.git
cd farming_project
pip install -r requirements.txt
```

### Environment Variables
Create a `.env` file:
```env
WATSONX_API_KEY=your_watsonx_api_key
WATSONX_PROJECT_ID=your_project_id
WATSONX_URL=https://us-south.ml.cloud.ibm.com
OPENWEATHER_API_KEY=your_openweather_key
AGMARKNET_API_KEY=your_agmarknet_key
```

### Run the LangFlow Workflow
```bash
langflow run langflow_workflow.json
```

### Run the Streamlit Dashboard
```bash
streamlit run app.py
```

---

## 📁 Repository Structure

```
farming_project/
├── app.json                          # Project metadata
├── langflow_workflow.json            # LangFlow multi-agent workflow
├── Smart_Farming_AI_Agent.pptx       # Project presentation
├── SmartFarming_ProblemStatement.pdf # Problem statement PDF
├── README.md                         # This file
└── requirements.txt                  # Python dependencies
```

---

## 📦 Requirements

```
langflow>=1.0.0
ibm-watsonx-ai>=0.2.0
streamlit>=1.28.0
python-dotenv>=1.0.0
faiss-cpu>=1.7.4
requests>=2.31.0
```

---

## 🏆 IBM Certificates
- ✅ Getting Started with Artificial Intelligence — IBM SkillsBuild (10 Nov 2026)
- ✅ Getting Started with Cybersecurity — IBM SkillsBuild (10 Nov 2026)
- ✅ Exploring Quantum Computing — IBM SkillsBuild (10 Nov 2026)
- ✅ Level Up Cybersecurity with Generative AI — IBM SkillsBuild (10 Nov 2026)
- ✅ Lab: Troubleshoot Your Code Using IBM Bob — IBM SkillsBuild (19 Aug 2026)

---

## 📄 License
This project is submitted as part of the IBM University Engagement Program 2026.
