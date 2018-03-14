pipeline {
    agent {
        docker {image 'hello-world'}
    }
    stages {
        stage('Hello, World') {
            steps {
                //sh 'curl localhost:80'
                echo "Null build step"
            }
        }
    }
}