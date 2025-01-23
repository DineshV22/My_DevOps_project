pipeline {
    agent 
    


        environment {
        // Add environment variables if needed
        REGISTRY = 'docker.io'                                // DockerHub registry
        REPO = 'https://hub.docker.com/repositories/dinesh2001v'                 // Your DockerHub repo
        IMAGE = "${REGISTRY}/${REPO}:${env.BUILD_NUMBER}"    // Full Docker image tag


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
                echo 'Building Docker image...'
                sh 'docker build -t ${TODO} .'
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
