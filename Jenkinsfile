pipeline {
    agent {
        docker {image 'gnuchu/hello-world'}
    }
    stages {
        stage {
            steps {
                sh 'curl localhost:80'
            }
        }
    }
}