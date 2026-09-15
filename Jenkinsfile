pipeline {
    agent any

    parameters {
        string(
            name: 'VERSION',
            defaultValue: '1.0',
            description: 'Version to deploy'
        )

        choice(
            name: 'ENVIRONMENT',
            choices: ['staging', 'production'],
            description: 'Target environment'
        )

        booleanParam(
            name: 'SKIP_TESTS',
            defaultValue: false,
            description: 'Skip tests?'
        )
    }

    stages {

        stage('Build') {
            steps {
                echo "Building version ${params.VERSION}"
            }
        }

        stage('Tests') {
            when {
                expression {
                    return !params.SKIP_TESTS
                }
            }

            parallel {

                stage('Unit') {
                    steps {
                        sh 'echo Running unit tests'
                    }
                }

                stage('Integration') {
                    steps {
                        sh 'echo Running integration tests'
                    }
                }
            }
        }

        stage('Deploy') {
            steps {
                echo "Deploying version ${params.VERSION}"
                echo "Environment: ${params.ENVIRONMENT}"
            }
        }
    }
}
