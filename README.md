# Devlup-woc-backend

Backend API for Devlup Winter of Code program built with FastAPI and MongoDB.

## Prerequisites

- Python 3.12+
- MongoDB instance (local or cloud)
- pip (Python package manager)

## Setup Instructions

### 1. Clone the repository

```bash
git clone <repository-url>
cd Devlup-woc-backend
```

### 2. Install dependencies

```bash
pip install -r requirements.txt
```

### 3. Configure environment variables

Create a `.env` file in the root directory:

```bash
MONGO_URL=mongodb://localhost:27017/
```

Replace with your MongoDB connection string. For MongoDB Atlas:
```bash
MONGO_URL=mongodb+srv://<username>:<password>@<cluster>.mongodb.net/
```

### 4. Run the development server

From the root directory:

```bash
uvicorn app.main:app --reload
```

Or navigate to the app directory first:

```bash
cd app
uvicorn main:app --reload
```

### 5. Access the API

- **API Base URL**: http://localhost:8000
- **Interactive API Docs (Swagger)**: http://localhost:8000/docs
- **Alternative API Docs (ReDoc)**: http://localhost:8000/redoc

## API Endpoints

Visit http://localhost:8000/docs for complete API documentation with interactive testing.

## Project Structure

```
Devlup-woc-backend/
├── app/
│   ├── main.py              # FastAPI application entry point
│   ├── config/
│   │   └── database.py      # MongoDB connection configuration
│   ├── models/              # Data models
│   └── routes/              # API route handlers
│       ├── woc_route.py
│       └── devlup_route.py
├── requirements.txt         # Python dependencies
├── .env                     # Environment variables (create this)
└── README.md
```

## Database Collections

The application uses the following MongoDB collections:
- `projects`
- `timeline`
- `users`
- `mentors`
- `ideas`
- `programs`
- `proposals`
- `progress`

## Production Deployment

For production deployment (configured for Heroku):

```bash
uvicorn app.main:app --host 0.0.0.0 --port 8000
```

## Technologies Used

- **FastAPI** - Modern web framework for building APIs
- **Uvicorn** - ASGI server
- **PyMongo** - MongoDB driver
- **Python-Jose** - JWT token handling
- **Python-dotenv** - Environment variable management