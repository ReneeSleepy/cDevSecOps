pipeline {
    agent any
    stages {
        stage('Checkout') {
            steps {
                git branch: 'main', 
                url: 'https://github.com/ReneeSleepy/cDevSecOps.git'
            }
        }
        stage('Install Dependencies') {
            steps {
                sh 'npm install'
            }
        }
        stage('Run Tests') {
            steps {
                sh 'npm test || true' // Continue even if tests fail
            }
        }
        stage('Security Scan') {
            steps {
                sh 'npm audit || true' // Output vulnerability report
            }
        }
    }
    post {
        always {
            archiveArtifacts artifacts: '**/npm-audit.json', allowEmptyArchive: true
        }
    }
}
