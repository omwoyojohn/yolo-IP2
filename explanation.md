📘 Technical Explanation – Yolo-IP2 E-commerce App
This document explains the design decisions, Docker setup, Git workflow, and key configurations behind my IP2 full-stack e-commerce app.

🧱 Base Images Used
Backend (Node.js + Express)

I chose node:18-alpine for its lightweight footprint and security.

It's optimized for production use with fewer dependencies and faster container builds.

Frontend (React)
Used the same base image for consistency and to keep builds small.

Create React App works smoothly on this image.

🐳 Dockerfile Directives
Both Dockerfiles follow a standard pattern:

WORKDIR /app
COPY package*.json ./
RUN npm install
COPY . .
EXPOSE 3000 # (frontend) or 5000 (backend)
CMD ["npm", "start"]
WORKDIR sets the context inside the container.

COPY brings in only necessary files at each stage to leverage Docker layer caching.

RUN npm install handles dependency installation.

CMD starts the application server.

🔗 Docker Compose Networking
Docker Compose connects both services via a shared bridge network:

services:
  backend:
    container_name: backend
    build: ./backend
    ports:
      - "5000:5000"
    environment:
      - MONGO_URI=...

  frontend:
    container_name: frontend
    build: ./frontend
    ports:
      - "3000:3000"
    depends_on:
      - backend

Key Notes:
depends_on ensures the backend starts before the frontend.

No manual networking config is needed—Docker Compose handles service discovery by name (backend, frontend).

Frontend can make API calls to http://backend:5000.


🔀 Git Workflow & PR Process
I followed a branch-per-task approach:

git checkout -b feature/frontend-setup
# work...
git add .
git commit -m "feat: setup CRA frontend"
git push --set-upstream origin feature/frontend-setup
Every key feature or fix was done in its own branch.

Pull Requests (PRs) were created via GitHub and merged into master.

This kept history clean and ensured modular development.

Branches Used:
feature/frontend-setup

feature/backend-api

fix/docker-compose

docs/readme

docs/explanation

🐞 Debugging Tips
Here are some common issues I faced and how I resolved them:

Issue	Solution
permission denied on Docker socket	Use sudo docker ... or add user to docker group
Missing package.json during build	Ensure COPY is done correctly and in the right context
MongoDB connection errors	Whitelist IP in MongoDB Atlas, use correct URI in .env
Port conflicts	Change local ports in docker-compose.yml if needed

📦 Docker Hub Images
✅ Backend
🔗 omwoyojohn/ecommerce-backend

✅ Frontend
🔗 omwoyojohn/ecommerce-frontend

📸 Screenshot – Docker Hub Push
See attached images

![Docker Hub push screenshot](./screenshots/dockerhub-push.png)
🙋 Author
Omwoyo John

GitHub: @omwoyojohn

Docker Hub: omwoyojohn

