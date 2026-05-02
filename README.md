# LLM Chat Bot 

## Architecture
- server.py: Ollama 8000 port -> LLM server

## TODO List
Backend
- API

UI 
- Chatting history
- Message box, Send button

## API Definitions

### Chat API
- **POST /api/chat**
  - Request: `{ "message": "user message", "session_id": "session_id" }`
  - Response: `{ "response": "llm response", "session_id": "session_id" }`

### Chat History API
- **GET /api/history/:session_id**
  - Response: `{ "messages": [{ "role": "user/assistant", "content": "message" }] }`

- **POST /api/history**
  - Request: `{ "session_id": "session_id" }`
  - Response: `{ "session_id": "session_id", "created_at": "timestamp" }`

### Session API
- **GET /api/sessions**
  - Response: `{ "sessions": [{ "session_id": "id", "created_at": "timestamp" }] }`

- **DELETE /api/sessions/:session_id**
  - Response: `{ "status": "deleted" }`