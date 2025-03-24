# StudentProject

This is a simple multi-App Django project containerized with Docker and integrated with Jenkins for CI/CD.

## Project Structure
- **Django Project:** `StudentProject`
- **Apps:** `app1`, `app2`
- **Views:** Static views with templates (no database/models)

## Setup & Usage

### Run Locally
1. Clone the repository:
   ```sh
   git clone https://github.com/your-repo/StudentProject.git
   cd StudentProject

2. Install dependecies:
    ```sh
    pip install -r requirements.txt

3. Run the Django development server:
    ```sh
    python manage.py runserver

4. Run the container:
    ```sh
    docker run -p 8000:8000 studentproject

### Docker Hub
The Docker image is available at:  
```sh
docker pull your-dockerhub-username/studentproject
```

## Jenkins CI/CD Pipeline

### Jenkinsfile Automates:
- Code pull from GitHub
- Docker image build
- Push to Docker Hub

### To Run in Jenkins:
1. Configure a **Pipeline Job** in Jenkins.
2. Link the job to this **GitHub repository**.
3. Run the pipeline to automate the deployment.


