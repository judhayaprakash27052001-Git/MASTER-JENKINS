pipeline {
    agent any

    environment {
        APP_NAME = "portfolio-app"
        ENVIRONMENT = "dev"
    }

    stages {

        stage('Build') {
            steps {
                echo "Building application"
                bat "echo Building %APP_NAME% on branch %BRANCH_NAME%"
            }
        }

        stage('Test') {
            steps {
                echo "Running tests"
                bat "echo Tests passed on %BRANCH_NAME%"
            }
        }

        stage('Use Secret (Token Test)') {
            steps {
                withCredentials([string(credentialsId: 'api1-token', variable: 'API1_TOKEN')]) {
                    bat "echo Secret token injected successfully"
                    // DO NOT print %API1_TOKEN%
                }
            }
        }

        stage('Deploy') {
            when {
                branch 'main'
            }
            steps {
                echo "Deploying application"
                bat "echo Deploying %APP_NAME% to production from MAIN branch"
            }
        }
    }

    post {
        success {
            echo "Pipeline SUCCESS for branch: ${env.BRANCH_NAME}"
        }

        failure {
            echo "Pipeline FAILED for branch: ${env.BRANCH_NAME}"
        }

        always {
            echo "Pipeline FINISHED for branch: ${env.BRANCH_NAME}"
        }
    }
}
