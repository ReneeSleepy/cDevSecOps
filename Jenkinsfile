pipeline {
    agent any
    stages {
        stage('Checkout') {
            steps {
                git branch: 'main', url: 'https://github.com/你的GitHub用户名/8.2CDevSecOps.git'
            }
        }
        stage('示范') {
            steps {
                echo 'Pipeline running...'
            }
        }
    }
}
