# Blogging Website Using Flask

A blogging website built with Python and Flask. Visitors can browse posts and read individual articles. Registered users can sign in, publish posts, and manage their profiles.

## Features

- Register, log in, and log out. Passwords are hashed with bcrypt.
- Browse published posts and open individual articles.
- Create posts and edit or delete your own posts.
- Update your username, email address, and profile picture.
- Upload a JPG or PNG profile picture. Pillow resizes it to fit within 125 × 125 pixels.

## Tech Stack

- **Flask** for routing and rendering Jinja templates
- **Flask-SQLAlchemy and SQLite** for storing users and posts
- **Flask-Login and Flask-Bcrypt** for session management and password hashing
- **Flask-WTF** for form handling and validation
- **Bootstrap and custom CSS** for styling

## Run Locally

### 1. Clone the repository and install dependencies

```bash
git clone https://github.com/Hemavarshika/Blogging-Website-using-flask.git
cd Blogging-Website-using-flask
python -m venv .venv
```

Activate the virtual environment with `.\.venv\Scripts\Activate.ps1` in Windows PowerShell or `source .venv/bin/activate` on macOS or Linux. Then install the dependencies.

```bash
python -m pip install Flask Flask-SQLAlchemy Flask-Login Flask-Bcrypt Flask-WTF Pillow email-validator
```

### 2. Arrange the application files

The repository stores its application files at the root. The Python imports expect a package named `flaskblog`, and Flask expects templates and static files inside that package. Arrange the files as follows.

```text
Blogging-Website-using-flask/
├── run.py
└── flaskblog/
    ├── __init__.py
    ├── forms.py
    ├── models.py
    ├── routes.py
    ├── templates/
    │   └── all .html files from the repository
    └── static/
        ├── main.css
        └── profile_pics/
            └── default.jpg
```

Add a JPG image of your choice as `default.jpg`. The app uses it for new accounts until the user uploads a profile picture.

### 3. Initialize the database and start Flask

From the repository root, create the SQLite tables and start the development server.

```bash
python -m flask --app flaskblog shell
```

```python
from flaskblog import db
db.create_all()
exit()
```

```bash
python run.py
```

Open `http://127.0.0.1:5000`, register an account, and select **New Post** to publish your first article.
