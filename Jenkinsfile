pipeline {
    agent any

    stages {

        stage('Checkout Code') {
            steps {
                echo 'Cloning GitHub repository...'
                checkout scm
            }
        }

        stage('Docker Build') {
            steps {
                echo 'Building Docker image...'
                bat 'docker build -t patient-monitoring-app .'
            }
        }

        stage('Docker Run') {
            steps {
                echo 'Running Docker container...'

                // Stop & remove old container if exists
                bat '''
                docker stop pms-app || exit 0
                docker rm pms-app || exit 0
                '''

                // Run on port 3000 (NOT 8080)
                bat 'docker run -d -p 3000:80 --name pms-app patient-monitoring-app'
            }
        }
    }

    post {
        success {
            echo 'CI/CD Pipeline completed successfully!'
        }
        failure {
            echo 'Pipeline failed!'
        }
    }
}
