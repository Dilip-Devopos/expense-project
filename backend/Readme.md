🛠️ Jenkins CI Pipeline - Open Source Project
This open-source project demonstrates how to build a Jenkins CI pipeline using various DevSecOps tools integrated into a Docker Agent.

📋 Prerequisites
Ensure the following tools are installed on your Jenkins host machine:

🐙 Git

☕ Java

🔧 Maven

🐳 Docker

🧪 SonarQube (running in a container with volumes)

🐳 Jenkins

🐳 Dockerfile

🔍 Trivy

🛡️ OWASP Dependency-Check

🐳 Create a Docker Agent with Preinstalled Tools
The custom Docker agent should include the following tools:

Git

Maven

Java

SonarQube CLI

Trivy

OWASP Dependency-Check

You can create a Dockerfile including all these tools and build the image for Jenkins usage.

🐳 Install Docker
bash
Copy
Edit
sudo apt update
sudo apt install docker.io -y
sudo usermod -aG docker jenkins
newgrp docker
🔧 Install SonarQube with Docker
bash
Copy
Edit
docker volume create sonarqube_data
docker volume create sonarqube_extensions
docker volume create sonarqube_logs

docker run -d \
  --name sonarqube \
  -p 9000:9000 \
  -v sonarqube_data:/opt/sonarqube/data \
  -v sonarqube_extensions:/opt/sonarqube/extensions \
  -v sonarqube_logs:/opt/sonarqube/logs \
  sonarqube:lts
Check container status:

bash
Copy
Edit
docker ps
docker logs <container-id> -f
SonarQube Default Credentials:

Username: admin

Password: admin

🔐 Generate SonarQube Token
Open SonarQube in your browser: http://<your-sonarqube-host>:9000

Login with:

Username: admin

Password: admin

Navigate to: Your Avatar (top-right) → My Account → Security

Under Generate Tokens, enter a name (e.g., jenkins-token) and click Generate.

Copy the token and save it securely.

🔑 Add SonarQube Token to Jenkins
Open Jenkins: http://<your-jenkins-host>:8080

Navigate to:
Manage Jenkins → Credentials → (global) → Add Credentials

Fill in:

Kind: Secret Text

Secret: Paste the SonarQube token

ID: sonarqube-token

Description: SonarQube auth token

Click OK

🔥 Allow SonarQube Port (Optional)
bash
Copy
Edit
sudo ufw allow 9000/tcp
🔧 Jenkins Configuration
Login to Jenkins and create a new job (type: Pipeline).

In the Pipeline section, paste the pipeline script or link it via Git.

Ensure the following plugins are installed:

Docker Pipeline Plugin

OWASP Dependency-Check Plugin

Add required credentials:

Docker credentials

SonarQube token (as configured above)
