# 🛒 Yolo-IP2 E-Commerce Project (Omwoyo John Onwong'a, DevOps Engineer, Livinggoods)

This project is my submission for the **IP2 practical assignment**. It is a full-stack e-commerce web application built using the MERN stack, containerized with Docker, and deployed using Docker Compose. The project demonstrates backend-frontend integration, API consumption, MongoDB connectivity, and proper GitHub workflow.

## 🧱 Technology Stack

| Layer      | Tech Used                  |
|------------|----------------------------|
| Frontend   | React (Create React App)   |
| Backend    | Node.js + Express          |
| Database   | MongoDB Atlas              |
| DevOps     | Docker, Docker Compose     |
| Registry   | Docker Hub                 |

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

## 🐳 Docker Hub Images

Both services were containerized, tagged, and pushed to Docker Hub:

| Component | Docker Image |
|-----------|---------------|
| Backend   | [`omwoyojohn/ecommerce-backend`](https://hub.docker.com/r/omwoyojohn/ecommerce-backend) |
| Frontend  | [`omwoyojohn/ecommerce-frontend`](https://hub.docker.com/r/omwoyojohn/ecommerce-frontend) |

<img width="1920" height="1200" alt="Screenshot from 2025-08-01 00-37-47" src="https://github.com/user-attachments/assets/825b79bf-9270-4982-bf8c-8b27573b7487" />

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

<img width="1390" height="768" alt="Screenshot from 2025-08-01 00-35-58" src="https://github.com/user-attachments/assets/36affdf2-6a9b-4f16-bd71-5d26db11bf5c" />

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

<img width="1920" height="1200" alt="Screenshot from 2025-08-01 00-37-47" src="https://github.com/user-attachments/assets/d4dfbd85-a7c2-49e8-81fd-4ea0a9a3f12b" />

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
<img width="1916" height="1199" alt="Screenshot from 2025-08-01 01-11-45" src="https://github.com/user-attachments/assets/7e8ab66f-4d51-411b-8385-7ef6733dab74" />
<img width="1916" height="1199" alt="Screenshot from 2025-08-01 01-12-20" src="https://github.com/user-attachments/assets/32c91054-f3c1-4fad-af56-e2b8bc8a97c7" />
<img width="1916" height="1199" alt="Screenshot from 2025-08-01 01-13-51" src="https://github.com/user-attachments/assets/88f17328-9a46-432a-92f4-05ddc9b0845c" />

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
