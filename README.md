# Enterprise Data Visualisation Platform (EDVP)

[![React](https://img.shields.io/badge/Frontend-React%2018-blue)](https://github.com/Enterprise-Data-Visualisation/react-client)
[![Python](https://img.shields.io/badge/Backend-Python-yellow)](https://github.com/Enterprise-Data-Visualisation/asset-service)
[![Architecture](https://img.shields.io/badge/Architecture-Decoupled-green)](#system-architecture)

**A high-performance, decoupled visualization system designed to render complex asset data for enterprise analytics.**

## 🚀 Overview

The **Enterprise Data Visualisation Platform** is a micro-service based solution designed to bridge the gap between heavy backend data processing (Python) and high-performance client-side rendering (React). 

Unlike traditional monolithic dashboards, EDVP decouples the **Data Aggregation Layer** from the **Presentation Layer**, allowing for independent scaling and optimized payload delivery for financial datasets.

## 🏗 System Architecture

This platform follows a modern **Consumer-Provider pattern**, tailored for financial data visualization.

```mermaid
graph LR
    User[Client Browser] -->|HTTP/WebSocket| FE[React Frontend]
    FE -->|REST API| BE[Python Asset Service]
    BE -->|Data Aggregation| DS[(Data Sources/CSV)]
    
    subgraph Frontend Layer
    FE
    State[Zustand Store]
    Viz[Plotly/D3 Charts]
    end
    
    subgraph Backend Layer
    BE
    Pandas[Pandas Processing]
    API[FastAPI/Flask]
    end


📦 Micro-Services (Repositories)
This organization is split into domain-specific repositories to ensure separation of concerns:

1. Frontend Client (React)
Role: The visualization layer.

Tech Stack: React 18, TypeScript, Tailwind CSS, Plotly.js/Recharts.

Key Features:

Data Virtualization: Handles large datasets efficiently.

Responsive Charts: Dynamic scaling for complex time-series data.

Atomic State: Uses Zustand to minimize re-renders during high-frequency updates.

2. Asset Service (Python)
Role: The data aggregation and processing layer.

Tech Stack: Python, Pandas, REST API.

Key Features:

Data Normalization: Cleans and structures raw asset data before serving.

Optimized Payloads: Delivers lightweight JSON structures specifically formatted for frontend charting libraries.

💡 Engineering Decisions
Why Decoupled? Financial data science teams prefer Python (Pandas/NumPy) for data manipulation, while User Experience teams require the interactivity of React. This architecture allows both to coexist without locking the stack.

Performance First: Heavy data processing is offloaded to the Python backend. The React client receives only what it needs to render, ensuring the main thread remains unblocked (60 FPS UI).

🛠 Local Setup
To run the full suite locally:

Clone the repositories:

Bash
git clone [https://github.com/Enterprise-Data-Visualisation/react-client.git](https://github.com/Enterprise-Data-Visualisation/react-client.git)
git clone [https://github.com/Enterprise-Data-Visualisation/asset-service.git](https://github.com/Enterprise-Data-Visualisation/asset-service.git)
Start the Backend:

Bash
cd asset-service
pip install -r requirements.txt
python app.py
Start the Frontend:

Bash
cd react-client
npm install
npm run dev
Maintained by Archit Gupta - Senior Frontend Engineer


### **How to Install This (Crucial Step)**
1.  Go to your Organization page on GitHub (`github.com/orgs/Enterprise-Data-Visualisation`).
2.  Click **"New Repository"**.
3.  Name the repository **`.github`**.
4.  Make it **Public**.
5.  Create a folder inside it named `profile`.
6.  Create a file inside that named `README.md`.
7.  Paste the code above.
8.  **Update the Links:** I used generic names (`react-client`, `asset-service`). Change those URLs in the markdown to match your **actual** repo names.

This will put a professional "System Architecture" overview right on the front page of your Organization.
