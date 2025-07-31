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

<img width="1920" height="1200" alt="Screenshot from 2025-08-01 00-37-47" src="https://github.com/user-attachments/assets/825b79bf-9270-4982-bf8c-8b27573b7487" />

<img width="1920" height="1200" alt="Screenshot from 2025-08-01 00-37-47" src="https://github.com/user-attachments/assets/d4dfbd85-a7c2-49e8-81fd-4ea0a9a3f12b" />

<img width="1916" height="1199" alt="Screenshot from 2025-08-01 01-11-45" src="https://github.com/user-attachments/assets/7e8ab66f-4d51-411b-8385-7ef6733dab74" />

<img width="1916" height="1199" alt="Screenshot from 2025-08-01 01-12-20" src="https://github.com/user-attachments/assets/32c91054-f3c1-4fad-af56-e2b8bc8a97c7" />

<img width="1916" height="1199" alt="Screenshot from 2025-08-01 01-13-51" src="https://github.com/user-attachments/assets/88f17328-9a46-432a-92f4-05ddc9b0845c" />

<img width="1916" height="1199" alt="Screenshot from 2025-08-01 01-33-10" src="https://github.com/user-attachments/assets/0b25e440-8aee-42fb-9976-23a79e9b5443" />


🙋 Author
Omwoyo John

GitHub: @omwoyojohn

Docker Hub: omwoyojohn

