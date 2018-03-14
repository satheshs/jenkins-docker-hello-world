pipeline {
    agent {
        docker {image 'gnuchu/hello-world'}
    }
    stages {
        stage('Hello, World') {
            steps {
                sh 'curl localhost:80'
            }
        }
    }
}