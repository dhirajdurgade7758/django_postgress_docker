# Django + PostgreSQL + Docker Starter

This project is a Django 5 application configured to use PostgreSQL as its database, with Docker support for easy local development. It includes user authentication (via django-allauth), profile management, and a modular app structure.

---

## Features

* Django 5.x project structure
* PostgreSQL database (configured for Docker)
* User authentication and registration (django-allauth)
* User profile management (view, edit, onboarding, settings)
* Static and media file handling
* Docker Compose for easy setup
* Example apps: `a_home`, `a_users`
* HTMX integration for dynamic UI

---

## Project Structure

```
.
├── a_core/         # Django project settings and core config
├── a_home/         # Example app (home page, etc.)
├── a_users/        # User profiles, registration, etc.
├── static/         # Static files
├── templates/      # Project-level templates
├── postgres_data/  # PostgreSQL data and config (for Docker)
├── db.sqlite3      # (Legacy/optional) SQLite DB
├── manage.py
├── requirements.txt
├── docker-compose.yml
└── README.md
```

---

## Getting Started

### Prerequisites

* [Docker](https://www.docker.com/get-started)
* [Docker Compose](https://docs.docker.com/compose/)
* (Optional) Python 3.10+ and pip (for local, non-Docker dev)

### Quickstart with Docker

1. **Clone the repository:**

   ```sh
   git clone <your-repo-url>
   cd django_postgress_docker
   ```

2. **Build and run the Docker containers:**

   ```sh
   docker-compose up --build
   ```

3. **Apply migrations and create superuser:**

   ```sh
   docker-compose exec web python manage.py migrate
   docker-compose exec web python manage.py createsuperuser
   ```

---

## Configuration

* **Database:** Configured in `a_core/settings.py` to use PostgreSQL on port `5431` (see `docker-compose.yml`).
* **Static/Media:** Served from `/static/` and `/media/`.
* **Authentication:** Uses `django-allauth` for email-based login.
* **HTMX:** Included for dynamic frontend features.

---

## Useful Commands

```sh
python manage.py migrate
python manage.py createsuperuser
python manage.py runserver
pip install -r requirements.txt
docker-compose exec web python manage.py migrate
docker-compose exec web python manage.py createsuperuser
docker-compose up --build
```

---

## Troubleshooting

* If you change PostgreSQL config, restart the database container:

  ```sh
  docker-compose restart db
  ```

* For permission issues on `postgres_data/`, ensure your user has access.

---

## Default Accounts

Create an admin user with `createsuperuser` as shown above.

---

## License

MIT License (add your own license as needed).
