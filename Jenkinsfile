pipeline {
    agent any
        environment {
        GIT_URL = 'https://github.com/satheshs/jenkins-docker-hello-world.git'
        }
    stages {
        stage('checkout') {
            steps {
                deleteDir()
                git credentialsId: 'b728e187-9a27-4afd-9aa9-8736634134b4', url: "${GIT_URL}"
            }
        }
        stage('Build the image') {
            steps {
                echo "Build step"
                sh "docker build -t helloworld:latest -f Dockerfile ."
            }
        }
    }
}
