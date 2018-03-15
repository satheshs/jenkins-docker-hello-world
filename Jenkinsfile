pipeline {
    agent {
        docker {image 'gnuchu/hello-world'}
    }
    stages {
        stage('Hello, World') {
            steps {
                echo "Build step"
                sh 'curl localhost:80'
                sh 'curl localhost:5000'
            }
        }
    }
}