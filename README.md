# MERN Dockerized Application

A full-stack MERN application containerized using Docker and Docker Compose.

Project Structure

Tutorials/
│
├── backend/
│   ├── config/
│   ├── model/
│   ├── Dockerfile
│   ├── .dockerignore
│   ├── .env.example
│   ├── package.json
│   └── index.js
│
├── frontend/
│   ├── public/
│   ├── src/
│   ├── Dockerfile
│   ├── .dockerignore
│   ├── package.json
│   └── vite.config.js
│
├── docker-compose.yml
└── README.md

# Features

- Dockerized MERN stack application
- Separate frontend and backend containers
- Environment variable support using ".env"
- Secrets are not stored inside Docker images
- Easy deployment using Docker Compose

# Docker Images

backend  -> aditya9325/backend
frontend -> aditya9325/frontend

# Backend Environment Variables

Create a file named ".env" inside the "backend" directory:

PORT=4000

Example:

PORT=4000


# Docker Compose Configuration

services:
  backend:
    image: aditya9325/backend
    ports:
      - "4000:4000"
    env_file:
      - ./backend/.env

  frontend:
    image: aditya9325/frontend
    ports:
      - "5173:5173"
    depends_on:
      - backend

# Running the Project

Clone the repository:

git clone <repository-url>
cd Tutorials

Create backend environment file:

cp backend/.env.example backend/.env

Update the values in "backend/.env".

Start the containers:

docker compose up

Run in detached mode:

docker compose up -d

Stop the containers:

docker compose down

# Access Application

Frontend:

http://localhost:5173

Backend API:

http://localhost:4000

Security

- ".env" is ignored using ".dockerignore"
- Sensitive credentials are never included in Docker images
- Users can provide their own ".env" file while using the images

# Pull Images Manually

docker pull aditya9325/backend
docker pull aditya9325/frontend

# Technologies Used

Frontend

- React
- Vite
- JavaScript

Backend

- Node.js
- Express.js

DevOps

- Docker
- Docker Compose