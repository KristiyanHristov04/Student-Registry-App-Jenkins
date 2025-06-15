pipeline {
    agent any

    stages {
        stage('Checkout Code') {
            steps {
                echo '📥 Checking out source code...'
                checkout scm
            }
        }

        stage('Install Dependencies') {
            steps {
                echo '📦 Installing dependencies...'
                bat 'npm install'
            }
        }

        stage('Start Application') {
            steps {
                echo '🚀 Starting application in background...'
                bat 'start /B npm start'
            }
        }

        stage('Run Tests') {
            steps {
                echo '🧪 Running tests...'
                bat 'npm test'
            }
        }
    }

    post {
        success {
            echo '✅ Pipeline completed successfully!'
        }
        failure {
            echo '❌ Pipeline failed.'
        }
    }
}
