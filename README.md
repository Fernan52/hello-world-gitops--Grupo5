Hello World GitOps Project
This project demonstrates a basic "Hello World" web application that is dockerized and managed using GitOps practices. The application displays a simple message through a containerized web server (Nginx) and integrates Git Hooks to validate Docker builds before committing code changes.
Features
•	GitOps Integration: Uses pre-commit hooks to ensure Docker image builds are validated before code commits.
•	Dockerization: The project is containerized using Docker with a simple Nginx setup.
•	Git Hooks: Git hooks automate the process of validating Docker builds before commits are allowed.
•	Local Deployment: Easily run the project locally with Docker.
Prerequisites
Before running the project, ensure that you have the following installed:
•	Docker: Make sure Docker is installed and running on your machine.
o	Install Docker
•	Git: Install Git to manage version control and execute Git hooks.
o	Install Git
•	Docker Desktop: For Windows and macOS, Docker Desktop is recommended for running Docker containers.
o	Download Docker Desktop
•	Text Editor: Visual Studio Code or any editor to modify project files.
o	Install Visual Studio Code
Installation
Follow the steps below to set up and run the project locally:
1. Clone the Repository
Clone the project to your local machine using Git:
git clone https://github.com/your_username/hello-world-gitops.git
2. Set Up Docker
Ensure that Docker is running on your system. You can verify this by running:
docker info
If Docker is properly set up, it will provide details about your Docker installation.
3. Build the Docker Image
Navigate to the project directory:
cd hello-world-gitops
Build the Docker image:
docker build -t hello-world .
4. Run the Docker Container
Start the Docker container:
docker run -d -p 8080:80 hello-world
5. Access the Application
Open your browser and go to http://localhost:8080. You should see the message "Hello World!".
Using Git Hooks
1. Modifying Files
To see the Git hook in action, make a modification in the index.html file. For example, change the greeting:
<h1>Hello World! Welcome to GitOps 2.0</h1>
2. Commit Changes
Stage and commit the changes:
git add .
git commit -m "Updated greeting in index.html"
The pre-commit hook will run and verify that the Docker build is successful before the commit is allowed. If the build fails, the commit will be blocked, ensuring only valid Docker images are part of your repository.
Uploading to GitHub
If you want to upload your changes to GitHub, follow these steps:
1. Connect Your Local Repository to GitHub
git remote add origin https://github.com/your_username/hello-world-gitops.git
git branch -M main
2. Push the Changes to GitHub
git push -u origin main
Troubleshooting
If you face any issues, here are a few troubleshooting steps:
•	Docker not running: Make sure Docker Desktop is running and configured correctly.
•	Git hook issues: Ensure that the pre-commit hook script is located in the .git/hooks directory and has execution permissions. On Windows, use Git Bash or WSL to execute the hook correctly.
References
•	Docker Documentation: https://docs.docker.com/
•	Git Documentation: https://git-scm.com/doc
•	GitHub Documentation: https://docs.github.com/en/github
