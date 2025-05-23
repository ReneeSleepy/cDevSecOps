pipeline {
    agent any
    stages {
        stage('Checkout') {
            steps {
                git branch: 'main', 
                url: 'https://github.com/your-github-account/8.2CDevSecOps.git'
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
