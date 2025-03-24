pipeline {
    agent any

    environment {
        IMAGE_NAME = 'atharvakulkarni20/djangoapp'
        CONTAINER_NAME = 'amazing_solomon'
    }

    stages {
        stage('Clone Repository') {
            steps {
                git branch: 'main', url: 'https://github.com/SRCEM-AIM-Class-A/A27_AtharvaKulkarni_DjangoApp.git'
            }
        }

        stage('Build Docker Image') {
            steps {
                bat "docker build -t %IMAGE_NAME% ."
            }
        }

        stage('Push to Docker Hub') {
            steps {
                script {
                    withCredentials([usernamePassword(credentialsId: 'atharvakulkarni20', usernameVariable: 'DOCKER_USER', passwordVariable: 'DOCKER_PASS')]) {
                        bat """
                        echo %DOCKER_PASS% | docker login -u %DOCKER_USER% --password-stdin
                        docker push %IMAGE_NAME%
                        """
                    }
                }
            }
        }

    }
}