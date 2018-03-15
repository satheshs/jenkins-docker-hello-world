pipeline {
    agent {
        docker {
            image 'gnuchu/hello-world'
            args '-p 5000:80'
        }
    }
    stages {
        stage('Hello, World') {
            steps {
                echo "Build step"
                sh 'ps -ef'
            }
        }
    }
}