# Sample Health API

A simple FastAPI-based health check service that provides a basic health endpoint.

## Features

- Health check endpoint at `/health`
- JSON response with status and message
- FastAPI framework with automatic API documentation
- Virtual environment support

## Installation

### Using uv (Recommended)

1. Install uv if you haven't already:
   ```bash
   pip install uv
   ```

2. Sync dependencies and create virtual environment:
   ```bash
   uv sync --link-mode=copy
   ```

3. Run the application:
   ```bash
   uv run python main.py
   ```

### Using pip

1. Create a virtual environment:
   ```bash
   python -m venv venv
   ```

2. Activate the virtual environment:
   ```bash
   # Windows
   venv\Scripts\activate

   # Linux/Mac
   source venv/bin/activate
   ```

3. Install dependencies:
   ```bash
   pip install -e .
   ```

4. Run the application:
   ```bash
   python main.py
   ```

## Usage

Once the server is running, you can access:

- **Health Check**: `http://localhost:8000/health`
  - Returns: `{"status": "healthy", "message": "Service is running"}`

- **API Documentation**: `http://localhost:8000/docs`
  - Interactive Swagger UI documentation

- **Alternative Docs**: `http://localhost:8000/redoc`
  - ReDoc documentation

## API Endpoints

### GET /

Returns the health status of the service (same as /health).

**Response:**
```json
{
  "status": "healthy",
  "message": "Service is running"
}
```

### GET /health

Returns the health status of the service.

**Response:**
```json
{
  "status": "healthy",
  "message": "Service is running"
}
```

## Development

- Python 3.11+
- FastAPI
- Uvicorn (ASGI server)

## Troubleshooting

### OneDrive Issues
If you're getting hardlink errors with uv in OneDrive folders, use:
```bash
uv sync --link-mode=copy
```

### Port Already in Use
If port 8000 is busy, you can run on a different port:
```bash
uv run uvicorn main:app --host 0.0.0.0 --port 8001
```