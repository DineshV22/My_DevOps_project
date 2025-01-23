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

         stage('Push to Docker Hub') {
            steps {
                echo "Pushing Docker image: ${IMAGE}"
                withCredentials([usernamePassword(credentialsId: 'myid123', usernameVariable: 'DOCKER_USER', passwordVariable: 'DOCKER_PASS')]) {
                    sh 'echo $DOCKER_PASS | docker login -u $DOCKER_USER --password-stdin'
                    sh "docker push ${IMAGE}"
                }
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
