# AI-Driven Web Intelligence for Sustainable E-Commerce

## Overview
This platform acts as an autonomous sustainability analyst. It scrapes e-commerce product pages, analyzes them for sustainability claims (using local AI), and provides grounded insights without hallucinations.

## Key Features
- **Advanced Scraping**: Powered by Playwright (Headless, Stealth Mode).
- **Zero-Hallucination AI**: RAG pipeline uses ONLY scraped data.
- **Local Intelligence**: Uses Ollama (Llama 3.2) for privacy and zero cost.
- **Vector Database**: ChromaDB for semantic search.

## Installation

1. **Prerequisites**:
   - Python 3.9+
   - [Ollama](https://ollama.com/) (Run `ollama pull llama3.2`)

2. **Install Dependencies**:
   ```bash
   pip install -r requirements.txt
   playwright install chromium
   ```

## How to Run

### 1. Start the Backend (API & Scraper)
*Use the special launcher for Windows compatibility:*
```bash
python backend/run.py
```
*Port: 8000*

### 2. Start the Frontend (UI)
```bash
streamlit run frontend/streamlit/app.py
```
*Port: 8501*

### 3. Start AI Engine
```bash
ollama serve
```

## Usage
1. Open the Dashboard (http://localhost:8501).
2. Go to **Scraper Control**.
3. Enter a product URL (e.g., specific item page).
4. Click **Start Scraping**.
5. Go to **AI Analysis**.
6. Ask: "Is this sustainable?", "What certifications does it have?".

## Project Structure
- `ai_engine/`: RAG pipeline and Prompts.
- `backend/`: FastAPI application.
- `data/`: ChromaDB storage.
- `frontend/`: Streamlit application.
- `scrapers/`: Playwright automation logic.
