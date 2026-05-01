# masterblog-api

A two-service blog application: a Flask REST API backend and a Flask frontend that communicates with it via JavaScript.

## Project Structure

```
4_10-MasterBlog-API/
├── backend/
│   ├── data/masterblog_posts.json   # post data storage
│   └── static/masterblog.json       # Swagger API spec
└── frontend/
    ├── frontend_app.py              # Flask frontend server
    ├── templates/index.html
    └── static/main.js, styles.css
```

## Setup

Install Flask if you haven't already:

```bash
pip install flask
```

## Running the App

You need to start **two servers** in separate terminals.

**1. Start the backend API** (port 5002):

```bash
cd backend
python backend_app.py
```

**2. Start the frontend** (port 5001):

```bash
cd frontend
python frontend_app.py
```

Then open your browser at `http://127.0.0.1:5001`.

## Using the Frontend

- **Load Posts** — enter the API base URL (`http://127.0.0.1:5002/api`) and click **Load Posts**
- **Add a Post** — fill in the title and content fields, then click **Add Post**
- **Delete a Post** — click the **Delete** button on any post

## API Endpoints

| Method | Endpoint | Description |
|--------|----------|-------------|
| `GET` | `/api/posts` | Return all posts |
| `POST` | `/api/posts` | Create a new post (`title`, `content` required) |
| `PUT` | `/api/posts/<id>` | Update a post by ID |
| `DELETE` | `/api/posts/<id>` | Delete a post by ID |
| `GET` | `/api/posts/search?title=&content=` | Search posts by title or content |

Full interactive API docs are available via Swagger UI at `http://127.0.0.1:5002/api/docs` when the backend is running.