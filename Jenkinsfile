pipeline {
    agent any

    environment {
        APP_ENV = 'test'
    }

    stages {
        stage('Checkout') {
            steps {
                checkout scm
            }
        }

        stage('Build') {
            steps {
                sh 'echo Building'
            }
        }

        stage('Test') {
            steps {
                sh 'echo Running tests'
            }
        }
    }

    post {
        success {
            echo 'All stages passed'
        }

        failure {
            echo 'Something failed'
        }
    }
}
