# Prakhar Garg - Professional Portfolio

A modern, responsive portfolio website built with Flask and vanilla HTML/CSS/JavaScript. This project showcases professional experience, skills, education, and provides a contact form for inquiries.

---

## 📋 Table of Contents

- [Project Overview](#project-overview)
- [Features](#features)
- [Tech Stack](#tech-stack)
- [Project Structure](#project-structure)
- [Installation](#installation)
- [Usage](#usage)
- [Configuration](#configuration)
- [Deployment](#deployment)
- [Contact Information](#contact-information)
- [License](#license)

---

## 🎯 Project Overview

This is a professional portfolio website designed to:
- Showcase professional experience and projects
- Highlight education and core values
- Provide a seamless user experience across all devices
- Enable potential clients/employers to contact directly through a contact form
- Demonstrate full-stack development capabilities (Frontend + Backend + Deployment)

**Live Demo:** Deploy using the instructions below to view the portfolio online.

Future Workflow
Every time you make changes:

Edit files in your project
Stage changes --> git add .
Commit with message --> git commit -m "Describe what you changed"
Push to GitHub -->git push


---

## ✨ Features

### Frontend Features
- **Responsive Design** - Mobile-first approach, works on all devices
- **Modern UI** - Clean, minimalist design with professional typography
- **Navigation** - Easy navigation between Home and About pages
- **Contact Form** - Functional contact form with validation and status feedback
- **Social Links** - Direct links to email, phone, and GitHub profile

### Backend Features
- **Flask Routes** - Simple and efficient routing for multiple pages
- **Template Rendering** - Dynamic HTML rendering with Flask Jinja2
- **Debug Mode** - Development mode with hot-reload capability
- **Extensible** - Easy to add new pages and features

---

## 🛠️ Tech Stack

| Layer | Technology |
|-------|-----------|
| **Backend** | Flask 2.3.0 (Python) |
| **Frontend** | HTML5, CSS3, Vanilla JavaScript |
| **Styling** | Google Fonts (EB Garamond, DM Sans) |
| **Server** | Flask Development Server (Gunicorn for production) |
| **Deployment** | Render, Railway, or Similar Platforms |

---

## 📁 Project Structure

```
Prakharportfolio/
├── app.py                    # Main Flask application
├── requirements.txt          # Python dependencies
├── README.md                 # Project documentation (this file)
├── .gitignore               # Git ignore rules
├── .venv/                   # Virtual environment (not committed)
│
├── templates/               # HTML templates
│   ├── index.html           # Home page
│   └── about.html           # About/Experience page
│
└── static/                  # Static assets
    ├── css/
    │   └── style.css        # Main stylesheet
    └── js/
        └── contact.js       # Contact form functionality
```

### File Descriptions

| File | Purpose |
|------|---------|
| `app.py` | Main Flask application with routing logic |
| `requirements.txt` | Python package dependencies |
| `index.html` | Home page with featured projects |
| `about.html` | About section, experience, education, and contact form |
| `style.css` | All styling and responsive layout |
| `contact.js` | Form validation and submission handling |

---

## 🚀 Installation

### Prerequisites
- Python 3.8+ installed on your system
- Git (optional, for version control)
- pip (Python package manager)

### Step-by-Step Setup

1. **Clone the repository** (if using Git)
   ```bash
   git clone <repository-url>
   cd Prakharportfolio
   ```

2. **Create a virtual environment**
   ```bash
   # Windows
   python -m venv .venv
   .venv\Scripts\activate

   # macOS/Linux
   python3 -m venv .venv
   source .venv/bin/activate
   ```

3. **Install dependencies**
   ```bash
   pip install -r requirements.txt
   ```

4. **Add Gunicorn (for production)**
   ```bash
   pip install gunicorn
   ```

5. **Update requirements.txt** (after installing packages)
   ```bash
   pip freeze > requirements.txt
   ```

---

## 💻 Usage

### Development Mode

1. **Start the Flask development server**
   ```bash
   python app.py
   ```

2. **Access the portfolio**
   - Open your browser and navigate to: `http://localhost:5000`
   - Home page: `http://localhost:5000/`
   - About page: `http://localhost:5000/about`

3. **Make changes** - The server auto-reloads on file changes (debug mode enabled)

### Project Routes

| URL | Description | File |
|-----|-------------|------|
| `/` | Home page with featured projects | `templates/index.html` |
| `/about` | About, experience, education, contact form | `templates/about.html` |

---

## ⚙️ Configuration

### Flask Configuration
Located in `app.py`:

```python
app.run(debug=True)  # Set debug=False for production
```

### Custom Configuration
To add custom settings, create a `config.py` file:

```python
class Config:
    DEBUG = False
    TESTING = False

class DevelopmentConfig(Config):
    DEBUG = True

class ProductionConfig(Config):
    DEBUG = False
```

Then update `app.py`:
```python
app.config.from_object('config.ProductionConfig')
```

---

## 🌐 Deployment

### Option 1: Render (Recommended)

1. **Prepare your project**
   - Ensure `requirements.txt` is up-to-date
   - Create `Procfile` in root directory:
     ```
     web: gunicorn app:app
     ```
   - Push code to GitHub

2. **Deploy to Render**
   - Go to [render.com](https://render.com)
   - Sign up and connect your GitHub account
   - Click "New +" → "Web Service"
   - Select your repository
   - Configure:
     - **Name**: Your app name
     - **Runtime**: Python 3
     - **Build Command**: `pip install -r requirements.txt`
     - **Start Command**: `gunicorn app:app`
   - Click "Create Web Service"

3. **Access your app**
   - Your portfolio will be live at: `your-app-name.onrender.com`

### Option 2: Railway

1. Go to [railway.app](https://railway.app)
2. Connect your GitHub repository
3. Railway auto-detects Flask apps
4. Deploy with one click

### Option 3: Heroku (Paid)

1. Install Heroku CLI
2. Run: `heroku login`
3. Create app: `heroku create your-app-name`
4. Deploy: `git push heroku main`

### Important: Update for Production

In `app.py`, change:
```python
app.run(debug=True)  # ❌ Development only
```

To:
```python
app.run(debug=False)  # ✅ Production
```

Or let your deployment platform handle this automatically.

---

## 📝 Contact Information

- **Email**: prakharjoy2010@gmail.com
- **Phone**: +91-7397975778
- **GitHub**: [prakhargrg](https://github.com/prakhargrg)
- **Portfolio**: [Your deployed URL]

---

## 📄 License

This project is open source and available under the MIT License. Feel free to use it as a template for your own portfolio.

---

## 🔄 Future Enhancements

Potential features to add:

- [ ] Add blog section with markdown support
- [ ] Implement email backend for contact form (SendGrid, EmailJS)
- [ ] Add project filtering and search
- [ ] Dark mode toggle
- [ ] Analytics integration
- [ ] SEO optimization
- [ ] Testimonials section
- [ ] Skills/technology showcase

---

## 🤝 Contributing

To contribute improvements:

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/improvement`)
3. Commit changes (`git commit -m 'Add improvement'`)
4. Push to branch (`git push origin feature/improvement`)
5. Open a Pull Request

---

## 📞 Support

For issues or questions:
1. Check existing documentation
2. Review Flask documentation: [flask.palletsprojects.com](https://flask.palletsprojects.com)
3. Contact via email or GitHub issues

---

## 📌 Version History

| Version | Date | Changes |
|---------|------|---------|
| 1.0.0 | March 2026 | Initial portfolio launch |

---

**Last Updated**: March 14, 2026

**Created by**: Prakhar Garg
