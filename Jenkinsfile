pipeline {
    agent any
        environment {
        GIT_URL = 'git@github.com:satheshs/jenkins-docker-hello-world.git'
        }
        stage('checkout') {
            steps {
                deleteDir()
                git branch: 'master',
                        url: "${GIT_URL}"
            }
        }
    }
    stages {
        stage('Hello, World') {
            steps {
                echo "Build step"
            }
        }
    }
}
