In this DevOps task, you need to build and deploy a full-stack CRUD application using the MEAN stack (MongoDB, Express, Angular 15, and Node.js). The backend will be developed with Node.js and Express to provide REST APIs, connecting to a MongoDB database. The frontend will be an Angular application utilizing HTTPClient for communication.  

The application will manage a collection of tutorials, where each tutorial includes an ID, title, description, and published status. Users will be able to create, retrieve, update, and delete tutorials. Additionally, a search box will allow users to find tutorials by title.

## Project setup

### Node.js Server

cd backend

npm install

You can update the MongoDB credentials by modifying the `db.config.js` file located in `app/config/`.

Run `node server.js`

### Angular Client

cd frontend

npm install

Run `ng serve --port 8081`

You can modify the `src/app/services/tutorial.service.ts` file to adjust how the frontend interacts with the backend.

Navigate to `http://localhost:8081/`
CI/CD pipeline trigger test
---

## 🏗️ DevOps Architecture

The application follows a containerized microservices-style architecture:

Browser  
→ Nginx (Reverse Proxy – Port 80)  
→ Angular Frontend (Docker Container)  
→ Node.js / Express Backend (Docker Container)  
→ MongoDB (Docker Container)

---

## 🐳 Docker & Containerization

- Backend and frontend are containerized using Docker
- Separate Dockerfiles are created for frontend and backend
- Docker images are built and pushed to Docker Hub

Docker Images:
- prvanchireddy/mean-backend
- prvanchireddy/mean-frontend

---

## 📦 Docker Compose Deployment

Docker Compose is used to manage and run multi-container services:
- Frontend
- Backend
- MongoDB
- Nginx reverse proxy

Command used for deployment:
```bash
docker-compose up -d
