pipeline {
    agent {
        docker {image 'gnuchu/hello-world'}
    }
    stages {
        stage('Hello, World') {
            steps {
                echo "Build step"
                sh 'ls -l'
            }
        }
    }
}