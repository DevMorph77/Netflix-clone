# Netflix-Clone

This project is a **Netflix Clone** built using **Django**. The platform allows users to create profiles, browse movies based on age restrictions, and watch them. Each user can manage multiple profiles, just like Netflix, and movies are filtered by age limits.

## Table of Contents

- [Features](#features)
- [Project Structure](#project-structure)
- [Installation](#installation)
- [Usage](#usage)
- [Views Overview](#views-overview)
- [Contributing](#contributing)
- [License](#license)

---

## Features

- User authentication with multiple profiles.
- Movies filtered by age limit set on profiles.
- Watch movies directly on the platform.
- View movie details with a simple, user-friendly interface.

---

## Project Structure

```
.
├── core/                   # Main app directory
│   ├── __init__.py
│   ├── views.py            # All the views for handling requests
│   ├── models.py           # Database models (Profile, Movie, etc.)
│   ├── forms.py            # Forms for user input (Profile form)
│   ├── urls.py             # URL routing for the core app
│   └── templates/          # HTML templates specific to the core app
│       ├── index.html      # Homepage template
│       ├── profileList.html# Profile list template
│       ├── profileCreate.html# Profile creation template
│       ├── movieList.html  # List of movies based on profile
│       ├── movieDetail.html# Movie detail template
│       └── showMovie.html  # Movie streaming page template
├── django_netflix/          # Project settings directory
│   ├── __init__.py
│   ├── settings.py         # Main Django project settings
│   ├── urls.py             # Project-level URL configuration
│   └── wsgi.py             # WSGI entry point for deployment
├── static/                 # Directory for static files (CSS, JS, images)
│   ├── css/                # CSS files
│   ├── js/                 # JavaScript files
│   └── images/             # Images used in the project
├── templates/              # Global templates used across the project
│   ├── base.html           # Base HTML template (common layout)
├── manage.py               # Django management script
├── requirements.txt        # Python dependencies
└── README.md               # Project documentation
```

---

## Installation

### Prerequisites

- Python 3.7+
- Django 3.x+
- Virtual environment (recommended)

### Clone the Repository

```bash
git clone https://github.com/yourusername/netflix-clone.git
cd netflix-clone
```

### Set Up Virtual Environment

```bash
# Create a virtual environment
python -m venv venv

# Activate the virtual environment
# On Windows
venv\Scripts\activate

# On macOS/Linux
source venv/bin/activate
```

### Install Dependencies

```bash
pip install -r requirements.txt
```

### Set Up the Database

Run migrations to create the necessary database tables:

```bash
python manage.py migrate
```

### Create a Superuser

```bash
python manage.py createsuperuser
```

### Run the Development Server

```bash
python manage.py runserver
```

The app will now be accessible at [http://127.0.0.1:8000](http://127.0.0.1:8000).

---

## Usage

1. Create an account or log in as an existing user.
2. Create a profile with an age limit (e.g., for children or adults).
3. Browse movies based on the selected profile's age limit.
4. Watch movies or view movie details.

---

## Views Overview

### **Home View**

- URL: `/`
- Redirects authenticated users to the profile list. Unauthenticated users are shown the login page.

### **Profile List View**

- URL: `/profile/`
- Displays a list of profiles associated with the logged-in user.
- Only accessible for logged-in users.

### **Profile Create View**

- URL: `/profile/create/`
- Allows the creation of a new profile with a specific age limit.
- Adds the newly created profile to the user's account.

### **Watch View**

- URL: `/watch/<profile_id>/`
- Shows the list of movies that match the selected profile's age limit.
- Displays a showcase movie at the top of the list.
- Redirects if the profile doesn't belong to the logged-in user.

### **ShowMovieDetail View**

- URL: `/movie/<movie_id>/detail/`
- Displays detailed information about the selected movie.
- Redirects to the profile list if the movie doesn't exist.

### **ShowMovie View**

- URL: `/movie/<movie_id>/watch/`
- Streams the selected movie.
- Redirects if the movie doesn't exist.

---

## Contributing

Contributions are welcome! To contribute:

1. Fork the repository.
2. Create a feature branch (`git checkout -b feature-branch`).
3. Commit your changes (`git commit -m "Add feature"`).
4. Push to the branch (`git push origin feature-branch`).
5. Open a pull request.

---

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.
