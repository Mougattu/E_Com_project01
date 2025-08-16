# Ecommerce Website

A simple **Flask-based ecommerce web application** containerized with Docker and configured for CI/CD using **Jenkins**, **AWS CodeBuild**, and **AWS CodeDeploy**.  

This project includes automation scripts, infrastructure files, and unit tests to demonstrate modern DevOps practices.

---

## 🚀 Features
- Flask application with a basic landing page (`/`)
- Unit tests with Python `unittest`
- Dockerized application (`Dockerfile`)
- CI/CD support:
  - **Jenkinsfile** for Jenkins pipeline builds
  - **buildspec.yml** for AWS CodeBuild
  - **appspec.yml** for AWS CodeDeploy
- Ready for cloud deployment (AWS ECS/EC2)

---

## 📂 Project Structure
.
├── appspec.yml # AWS CodeDeploy configuration
├── buildspec.yml # AWS CodeBuild configuration
├── Dockerfile # Docker image build instructions
├── Jenkinsfile # Jenkins pipeline definition
├── LICENSE # License information
├── README.md # Project documentation
├── test_app.py # Unit tests
├── web.py # Flask application entrypoint
└── templates/
└── test.html # HTML template rendered by Flask

## ⚙️ Prerequisites
- Python 3.8+
- Flask (`pip install flask`)
- Docker
- AWS CLI (if deploying to AWS)
- Jenkins (if using Jenkins pipeline)

## ▶️ Running Locally

 Clone the repository:
   ```bash
   git clone https://github.com/your-repo/ecommerce-website.git
   cd ecommerce-website
   
Install dependencies:
pip install flask

Run the Flask app:
python web.py

Application runs at: http://localhost:80

🧪 Running Tests
Unit tests are included in test_app.py.

Run them with:
python -m unittest test_app.py

🐳 Docker Support
Build Docker image:
docker build -t ecommerce-app .
Run container:
docker run -p 80:80 ecommerce-app

🔄 CI/CD Pipelines
Jenkins
Jenkinsfile defines a multi-stage pipeline for:
Build
Test
Dockerize
Deploy

AWS CodeBuild & CodeDeploy
buildspec.yml → Build/test configuration for AWS CodeBuild

appspec.yml → Deployment instructions for AWS CodeDeploy

📜 License
This project is licensed under the MIT License. See the LICENSE file for details.

🙌 Acknowledgments
Based on AWS sample applications for CI/CD pipelines with Flask and Docker.

