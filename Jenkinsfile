pipeline {
    agent any

    stages {

        stage('Checkout Code') {
            steps {
                echo 'Cloning GitHub repository...'
                checkout scm
            }
        }

        stage('Build') {
            steps {
                echo 'Build stage - frontend project'
            }
        }

        stage('Test') {
            steps {
                echo 'No tests configured yet'
            }
        }

        stage('Deploy') {
            steps {
                echo 'Deploy stage (future Docker deploy)'
            }
        }
    }

    post {
        success {
            echo 'Pipeline executed successfully!'
        }
        failure {
            echo 'Pipeline failed!'
        }
    }
}
