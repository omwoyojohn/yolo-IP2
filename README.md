# 🛒 Yolo-IP2 E-Commerce Project (Omwoyo John Onwong'a, DevOps Engineer, Livinggoods)

This project is my submission for the **IP2 practical assignment**. It is a full-stack e-commerce web application built using the MERN stack, containerized with Docker, and deployed using Docker Compose. The project demonstrates backend-frontend integration, API consumption, MongoDB connectivity, and proper GitHub workflow.

---

## 🧱 Technology Stack

| Layer      | Tech Used                  |
|------------|----------------------------|
| Frontend   | React (Create React App)   |
| Backend    | Node.js + Express          |
| Database   | MongoDB Atlas              |
| DevOps     | Docker, Docker Compose     |
| Registry   | Docker Hub                 |

---

## 📁 Project Structure

yolo-IP2/
├── backend/ # Express REST API
│ ├── Dockerfile
│ ├── .env
│ └── ...
├── frontend/ # React App
│ ├── Dockerfile
│ └── ...
├── docker-compose.yml # Service orchestration
├── explanation.md # Detailed write-up
└── README.md # This file

---

## 🐳 Docker Hub Images

Both services were containerized, tagged, and pushed to Docker Hub:

| Component | Docker Image |
|-----------|---------------|
| Backend   | [`omwoyojohn/ecommerce-backend`](https://hub.docker.com/r/omwoyojohn/ecommerce-backend) |
| Frontend  | [`omwoyojohn/ecommerce-frontend`](https://hub.docker.com/r/omwoyojohn/ecommerce-frontend) |

---

## 🚀 Running the Project with Docker Compose

> Ensure Docker and Docker Compose are installed on your system.

1. Clone the Repository

git clone https://github.com/omwoyojohn/yolo-IP2.git
cd yolo-IP2

2. Start the App
docker compose up --build

3. Access the Services
🖥️ Frontend: http://localhost:3000

🖥️ Backend: http://localhost:5000

🔐 MongoDB Configuration
Create a .env file inside the backend/ folder and add your MongoDB URI:

MONGO_URI=mongodb+srv://omwoyojohn:<your_password>@cluster0.mongodb.net/?retryWrites=true&w=majority
Replace <your_password> with the actual password for your MongoDB user.

✅ Completed Tasks
 Initialized Git repository with project structure

 Created and containerized the frontend using React

 Developed and containerized backend using Express and MongoDB

 Used Docker Compose to orchestrate both services

 Connected backend to MongoDB Atlas

 Pushed Docker images to Docker Hub

 Documented the process in README.md and explanation.md

🌿 Git Workflow
I have created and implemented each task in its own branch for clarity and traceability.

# Example: creating frontend setup branch
git checkout -b feature/frontend-setup
# make changes
git add .
git commit -m "feat: setup React frontend"
git push --set-upstream origin feature/frontend-setup
Pull requests were created and merged to the main branch after each milestone.

🖼️ Screenshots
See attached screenshots

UI running in browser

Terminal showing successful Docker builds and pushes

API responses in Postman or browser

📘 Additional Notes
Services are loosely coupled and can be scaled independently.

Proper .dockerignore and .gitignore fils were used.

Networking is handled via Docker Compose default bridge.

The MongoDB URI is managed securely via environment variables.

👤 Author
Omwoyo John, DevOps Engineer, Livinggoods

GitHub: @omwoyojohn

Docker Hub: omwoyojohn
