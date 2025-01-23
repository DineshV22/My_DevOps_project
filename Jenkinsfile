pipeline {
    agent any
    
    environment {
        REGISTRY = 'docker.io'                                // DockerHub registry
        REPO = 'dinesh2001v'                                  // Your DockerHub repo
        IMAGE = "${REGISTRY}/${REPO}:${env.BUILD_NUMBER}"     // Full Docker image tag
    }

    stages {
        stage('Clone Repository') {
            steps {
                git branch: 'main', url: 'https://github.com/DineshV22/My_DevOps_project.git'
            }
        }
       
        stage('Build') {
            steps {
                echo 'Building...'
                // Add your build steps here
            }
        }

        stage('Build Docker Image') {
            steps {
                echo "Building Docker image: ${IMAGE}"
                sh "docker build -t ${IMAGE} ."
            }
        }

        stage('Test') {
            steps {
                echo 'Testing...'
                // Add your testing commands here
            }
        }

        stage('Deploy') {
            steps {
                echo 'Deploying...'
                // Add your deployment steps here
            }
        }
    }
}
