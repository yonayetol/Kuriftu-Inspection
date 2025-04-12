# Kuriftu Inspect 2.0

A mobile-friendly resort inspection system built with Django and Django REST Framework.

## Features

### 1. Mobile-Friendly Digital Checklists
- Create and manage inspection checklists
- Organize items by categories (Rooms, Pool, Restaurant, etc.)
- Pass/Fail tracking with notes and media attachments
- Real-time inspection progress tracking

### 2. Automated Issue Reporting
- Automatic issue creation for failed checklist items
- Priority levels (Critical, High, Medium, Low)
- Media attachments and detailed descriptions
- Location tracking

### 3. Task Assignment & Follow-up
- Assign tasks to teams or individuals
- Track task status and due dates
- Comment system for updates
- Team management

### 4. Analytics & Reporting
- Common failure analysis
- Location-based issue tracking
- Time-series trends
- Recurring issue identification

## Tech Stack
- Django & Django REST Framework
- PostgreSQL
- Bootstrap 5
- Chart.js

## Installation

1. Create a virtual environment:
```bash
python -m venv venv
source venv/bin/activate  # Linux/Mac
.\venv\Scripts\activate   # Windows
```

2. Install dependencies:
```bash
pip install -r requirements.txt
```

3. Create a `.env` file:
```
DJANGO_SECRET_KEY=your-secret-key
DEBUG=True
DB_NAME=kuriftu_inspect
DB_USER=postgres
DB_PASSWORD=your-password
DB_HOST=localhost
DB_PORT=5432
```

4. Run migrations:
```bash
python manage.py migrate
```

5. Create a superuser:
```bash
python manage.py createsuperuser
```

6. Run the development server:
```bash
python manage.py runserver
```

## API Endpoints

### Authentication
- `POST /api/token/` - Get JWT token
- `POST /api/token/refresh/` - Refresh JWT token

### Users
- `GET /api/users/` - List users
- `POST /api/users/` - Create user
- `GET /api/users/{id}/` - Get user details

### Inspections
- `GET /api/inspections/categories/` - List categories
- `GET /api/inspections/items/` - List checklist items
- `POST /api/inspections/` - Create inspection
- `GET /api/inspections/{id}/` - Get inspection details

### Issues
- `GET /api/issues/` - List issues
- `POST /api/issues/` - Create issue
- `GET /api/issues/{id}/` - Get issue details

### Tasks
- `GET /api/tasks/` - List tasks
- `POST /api/tasks/` - Create task
- `GET /api/tasks/{id}/` - Get task details

### Reports
- `GET /api/reports/common-failures/` - Get common failures
- `GET /api/reports/issue-statistics/` - Get issue statistics
- `GET /api/reports/task-statistics/` - Get task statistics
- `GET /api/reports/recurring-issues/` - Get recurring issues

## User Roles
- **Admin**: Full system access
- **Manager**: Can manage inspections, issues, and tasks
- **Inspector**: Can perform inspections and report issues

## License
MIT License
