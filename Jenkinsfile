pipeline {
    agent any
        environment {
        GIT_URL = 'git@github.com:satheshs/jenkins-docker-hello-world.git'
        }
    stages {
        stage('checkout') {
            steps {
                deleteDir()
                git branch: 'master',
                        url: "${GIT_URL}"
            }
        }
        stage('Hello, World') {
            steps {
                echo "Build step"
            }
        }
    }
}
