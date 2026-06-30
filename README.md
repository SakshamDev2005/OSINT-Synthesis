# OSINT Synthesizer

AI-powered Open Source Intelligence platform that combines multi-engine web search with LLM-driven analysis to generate structured intelligence reports.

## Features

- Multi-source OSINT collection
  - DuckDuckGo
  - Wikipedia
  - Hacker News
  - NewsAPI (optional)
- LLM-powered intelligence synthesis via LiteLLM
- Structured JSON responses with schema validation
- FastAPI backend
- Dark-themed web interface
- Model allowlisting and rate limiting
- Automated test suite

## Tech Stack

| Layer | Technology |
|---------|------------|
| Backend | FastAPI, Python |
| LLM Gateway | LiteLLM |
| Validation | Pydantic |
| Search | DDGS, Wikipedia, Hacker News, NewsAPI |
| Frontend | HTML, CSS, JavaScript |
| Deployment | Docker |

## Architecture

```text
User → Web UI
     → FastAPI API
     → Search Pipeline
     → LLM Analysis
     → Validation & Normalization
     → Structured Intelligence Report
```

## Project Structure

```text
.
├── app/
│   ├── main.py
│   ├── models.py
│   ├── osint_service.py
│   ├── search_service.py
│   └── utils.py
├── static/
│   ├── index.html
│   ├── style.css
│   └── app.js
├── tests/
│   └── test_osint_service.py
├── Dockerfile
├── requirements.txt
└── README.md
```

## API Endpoints

| Method | Endpoint | Description |
|----------|----------|-------------|
| GET | `/health` | Health check |
| GET | `/api/models` | Available models |
| GET | `/api/probe-model` | Model connectivity test |
| POST | `/api/case-file` | Generate intelligence report |

## Security

- Input validation with Pydantic
- Per-IP rate limiting
- Configurable CORS policy
- Security response headers
- XSS-safe frontend rendering
- Hallucinated URL filtering
- Error sanitization

## Testing

```bash
pytest tests -v
```

## Docker

```bash
docker build -t osint-synthesizer .
docker run -p 8000:8000 osint-synthesizer
```

## Future Improvements

- Add more search providers
- Authentication and API keys
- Persistent report storage
- Background job processing
- Advanced source credibility scoring
