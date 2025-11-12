# Flask SQLite Demo

A Python Web application demo project based on [Flask](https://flask.palletsprojects.com/) and SQLite. Uses SQLAlchemy as ORM and demonstrates how to build a traditional synchronous web application.

## Tech Stack

- **Python**: 3.13+
- **Flask**: 3.1.2+
- **Flask-SQLAlchemy**: 3.1.1+
- **SQLAlchemy**: 2.0.41+
- **Pytest**: 8.4.2+ (Testing framework)

## Project Structure

```
flask-sqlite-demo/
├── app/
│   ├── main.py              # Flask application entry point
│   ├── domain/
│   │   └── models.py        # Data model definitions
│   └── routes/
│       └── hero_route.py   # Hero API routes
├── db/
│   ├── schema.ddl          # Database schema definition
│   └── demo.sqlite3        # SQLite database file
├── tests/                  # Test files
├── pyproject.toml          # Project configuration and dependencies
├── Justfile                # Just build tool configuration
└── README.md
```

## Features

- RESTful API design
- SQLAlchemy ORM integration
- Flask Blueprint route organization
- SQLite database support
- Unit testing support

## Quick Start

### Prerequisites

- Python 3.13 or higher
- pip or uv (recommended)

### Installation and Running

```bash
# Create virtual environment (recommended)
python -m venv venv
source venv/bin/activate  # Windows: venv\Scripts\activate

# Install dependencies
pip install -e ".[dev]"

# Or use uv (faster)
uv pip install -e ".[dev]"

# Run application
python -m app.main
```

The application will start at `http://localhost:5000` (default port).

### Environment Variables

You can configure the database connection via environment variables:

```bash
export SQLALCHEMY_DATABASE_URI="sqlite:///path/to/db/demo.sqlite3"
```

If not set, it defaults to `./db/demo.sqlite3`.

## API Endpoints

### Root Path
```http
GET http://localhost:5000/
```
Response: `Flask is working`

### Hero API

All Hero-related API endpoints are defined in `/app/routes/hero_route.py` with path prefix `/heros`.

## Database

### Database Initialization

The database schema is defined in `db/schema.ddl`. The database connection is automatically initialized when the application starts.

## References

- [Flask Official Documentation](https://flask.palletsprojects.com/)
- [Flask-SQLAlchemy Documentation](https://flask-sqlalchemy.palletsprojects.com/)
- [SQLAlchemy Documentation](https://docs.sqlalchemy.org/)
