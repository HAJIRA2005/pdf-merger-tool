# PDF Merger Tool

🔗 **GitHub Repository:** [https://github.com/HAJIRA2005/pdf-merger-tool](https://github.com/HAJIRA2005/pdf-merger-tool)

A simple, modern web application to upload multiple PDFs and merge them into a single file.

## Features
- Upload multiple PDFs at once
- Drag-and-drop support (bonus)
- Reorder files (move up/down)
- Remove selected files
- Merge with progress/status messages
- Light/Dark theme toggle (bonus)

## Tech Stack
- Frontend: HTML, CSS, vanilla JavaScript
- Backend: Node.js + Express + pdf-lib

## Getting Started

### Prerequisites
- Node.js 18+ (for local development)
- Docker and Docker Compose (for Docker deployment)

### Local Installation & Run
```bash
npm install
npm start
```
The app will start at `http://localhost:3000`.

### Docker Deployment

**Note:** Make sure Docker Desktop is installed and running before proceeding.

**Having Docker issues?** See `QUICK_FIX.md` for troubleshooting steps.

#### Quick Start (Windows)
- Double-click `docker-start.bat` to build and start the container
- Double-click `docker-stop.bat` to stop the container

#### Using Docker Compose (Recommended)
```bash
# Build and start the container
docker-compose up -d

# View logs
docker-compose logs -f

# Stop the container
docker-compose down
```

#### Using Docker directly
```bash
# Build the Docker image
docker build -t pdf-merger-tool .

# Run the container
docker run -d -p 3000:3000 --name pdf-merger pdf-merger-tool

# View logs
docker logs -f pdf-merger

# Stop the container
docker stop pdf-merger

# Remove the container
docker rm pdf-merger
```

The app will be available at `http://localhost:3000` when running in Docker.

## Usage
1. Click "Upload PDFs" or drag & drop PDFs into the drop area.
2. Reorder files if needed using ↑/↓ buttons.
3. Select files and click "Remove Selected" to remove them.
4. Click "Merge PDFs". The merged PDF will download automatically.

## Project Structure
```
.
├── public/
│   ├── index.html
│   ├── style.css
│   └── app.js
├── server.js
├── package.json
├── Dockerfile
├── docker-compose.yml
├── .dockerignore
├── docker-start.bat (Windows helper)
├── docker-stop.bat (Windows helper)
├── docker-build.bat (Windows helper)
├── .gitignore
└── README.md
```

## API
- POST `/merge` — accepts `multipart/form-data` with field name `files` (multiple). Returns the merged PDF as `application/pdf`.

## Notes
- Files are processed in-memory and never written to disk.
- Only `application/pdf` files are accepted.

## GitHub Deployment

### Quick Setup
1. Install Git: https://git-scm.com/download/win
2. Create a GitHub repository
3. Run `deploy-to-github.bat` or follow `GITHUB_SETUP.md`

### GitHub Actions
This repository includes GitHub Actions workflows:
- **Docker Build**: Automatically builds and pushes Docker images to GitHub Container Registry
- **Docker Deploy**: Tests Docker image builds on every push

See `GITHUB_SETUP.md` for detailed instructions.

### Using GitHub Container Registry
After pushing to GitHub, pull and run:
```bash
docker pull ghcr.io/HAJIRA2005/pdf-merger-tool:latest
docker run -d -p 3000:3000 ghcr.io/HAJIRA2005/pdf-merger-tool:latest
```

## 🔗 Repository

**GitHub:** [https://github.com/HAJIRA2005/pdf-merger-tool](https://github.com/HAJIRA2005/pdf-merger-tool)

## License
MIT




