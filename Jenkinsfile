pipeline {
    agent {
        docker {image 'gnuchu/hello-world'}
    }
    stage {
        stages {
            steps {
                sh 'curl localhost:80'
            }
        }
    }
}