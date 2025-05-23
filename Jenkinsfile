pipeline {
    agent any
    stages {
        stage('Checkout') {
            steps {
                git branch: 'main', url: 'https://github.com/ReneeSleepy/cDevSecOps.git'
            }
        }
        stage('sample') {
            steps {
                echo 'Pipeline running...'
            }
        }
    }
}

