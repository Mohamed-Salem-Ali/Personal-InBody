
# BodyTrack - Personal Body Composition Tracker

BodyTrack is a full-stack application for tracking and analyzing InBody test results. It helps you visualize your progress, understand body composition trends, and receive AI-powered insights.

## Project Structure

```
bodytrack/
├── config/             # Django Setting & Config (in backend/)
├── accounts/           # User Authentication App (in backend/)
├── inbody/             # InBody Data Management App (in backend/)
├── analytics/          # Data Analysis App (in backend/)
├── backend/            # Backend Source Code
├── frontend/           # React + Vite Frontend
├── nginx/              # Nginx Configuration
├── docker-compose.yml  # Dev orchestration
├── docker-compose.prod.yml # Prod orchestration
└── manage.py           # Django Management Script (in backend/)
```

## Features

- **Authentication**: Secure JWT-based auth with user profiles.
- **InBody Data Management**: CRUD operations for InBody records including Segmental Analysis.
- **Dashboard**: Comprehensive overview of current status and key metrics.
- **Analytics**: Interactive charts for Weight, Muscle, Fat, Score, Visceral Fat, and BMR trends.
- **Insights**: AI-driven analysis of your body composition changes and health risks.
- **Comparison**: Compare any two records side-by-side.

## Tech Stack

- **Backend**: Django, Django REST Framework, PostgreSQL
- **Frontend**: React, Vite, Tailwind CSS, Recharts, Axios
- **DevOps**: Docker, Nginx

## Getting Started

### Prerequisites

- Docker & Docker Compose
- Node.js 20+ (for local frontend dev)
- Python 3.11+ (for local backend dev)

### Quick Start (Docker) - Development

1.  **Clone and Navigate**:
    ```bash
    git clone <repo>
    cd bodytrack
    ```

2.  **Run with Docker Compose**:
    ```bash
    docker-compose up --build
    ```
    - Frontend: http://localhost:3000
    - Backend API: http://localhost:8000
    - Admin: http://localhost:8000/admin

3.  **Seed Data** (Optional):
    ```bash
    docker-compose exec backend python manage.py seed_saloom_data
    ```
    - Creates user: `saloom` / `Saloom@123`
    - Adds 12 months of sample data.

### Quick Start (Docker) - Production

1.  **Run with Production Compose**:
    ```bash
    docker-compose -f docker-compose.prod.yml up --build -d
    ```
    - App: http://localhost (Served via Nginx)

## Development Setup (Manual)

### Backend

1.  Navigate: `cd backend`
2.  Create venv: `python -m venv venv`
3.  Activate: `source venv/bin/activate` (Linux/Mac) or `venv\Scripts\activate` (Windows)
4.  Install: `pip install -r requirements.txt`
5.  Migrate: `python manage.py migrate`
6.  Run: `python manage.py runserver`

### Frontend

1.  Navigate: `cd frontend`
2.  Install: `npm install`
3.  Run: `npm run dev`

## License

MIT
