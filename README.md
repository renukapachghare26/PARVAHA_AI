# PRAVAHA-AI / Asteria Corridor Command Center

A predictive, physics-constrained traffic decision-support system — a live traffic management dashboard paired with a microscopic traffic simulation backend. Built for **SIH 2026** (Open Innovation track).

The system forecasts near-future traffic queues, detects spillback risk before it becomes gridlock, generates bounded signal alternatives, and validates every candidate through SUMO counterfactual simulation before it's ever recommended — with a hard SafetyGate blocking anything unsafe along the way.

## My Role

I worked on the research, positioning, and documentation side of this project — including the SafetyGate framing, competitive landscape analysis (SCOOT/SCATS, SURTRAC, Google Project Green Light, academic RL/SUMO work), and the project's technical write-ups — along with backend/ML logic contributions.

## Team

Built by a team of 6 for SIH 2026 as a collaborative effort across signal coordination, root-cause detection, and the simulate-before-deploy pipeline.

## Requirements
- **Python**: 3.9+ (Tested on 3.11)
- **Node.js**: v18+ 
- **SUMO (Simulation of Urban MObility)**: v1.27.1

**Important Note on SUMO**: SUMO cannot be installed solely via Python pip. You must install the SUMO binaries on your host system and ensure the `sumo` command is in your system $PATH. 
- macOS: `brew install sumo`
- Ubuntu: `sudo apt-get install sumo sumo-tools sumo-doc`

## Setup Instructions

### 1. Backend Setup
```bash
cd backend
python -m venv venv
source venv/bin/activate
pip install -r requirements.txt
```

### 2. Frontend Setup
```bash
cd frontend
npm install
```

## Running the Application

1. **Start the Backend Server (with active virtual environment)**:
```bash
cd backend
uvicorn app.main:app --reload
```
*Note: The backend will automatically spawn a background thread to run SUMO via TraCI on startup.*

2. **Start the Frontend Development Server**:
```bash
cd frontend
npm run dev
```

3. Open your browser to the URL provided by the Vite frontend server (typically http://localhost:5173).
