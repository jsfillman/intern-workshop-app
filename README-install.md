# Intern Workshop App - Installation Guide

A minimal Flask app with Bootstrap 5, designed for fast builds and deployment.

## Local Development

### Prerequisites
- Python 3.12+
- pip

### Quick Start

1. **Clone and setup**
   ```bash
   git clone <repository-url>
   cd intern-workshop-app
   pip install -r requirements.txt
   ```

2. **Run locally**
   ```bash
   python app.py
   ```
   App will be available at http://localhost:8080

3. **Custom environment variables** (optional)
   ```bash
   export TITLE="My Custom Title"
   export SUBTITLE="My Custom Subtitle"
   export BUTTON_TEXT="Click Me!"
   python app.py
   ```

## Docker Deployment

### Build and run with Docker

```bash
# Build the image
docker build -t intern-workshop-app .

# Run the container
docker run -p 8080:8080 intern-workshop-app
```

### Run with custom environment variables

```bash
docker run -p 8080:8080 \
  -e TITLE="Custom Docker Title" \
  -e SUBTITLE="Running in container 🐳" \
  -e BUTTON_TEXT="Docker Rules!" \
  intern-workshop-app
```

### Use pre-built image from GitHub Container Registry

```bash
# Pull and run latest
docker run -p 8080:8080 ghcr.io/[username]/intern-workshop-app:latest
```

## API Endpoints

- **GET /** - Main page with hero section
- **GET /status** - Health check endpoint returning `{"ok": true, "version": "1.0.0"}`

## Project Structure

```
.
├── app.py                          # Flask application
├── templates/index.html            # Bootstrap hero template
├── static/styles.css              # Custom styling
├── requirements.txt               # Python dependencies
├── Dockerfile                     # Docker configuration
├── .github/workflows/             # CI/CD automation
└── README-install.md             # This file
```