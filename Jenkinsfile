pipeline {
    agent any

    environment {
        APP_NAME = "multibranch-app"
    }

    stages {

        stage('Build') {
            steps {
                bat "echo Building %APP_NAME% on branch %BRANCH_NAME%"
            }
        }

        stage('Test') {
            steps {
                bat "echo Testing %APP_NAME% on branch %BRANCH_NAME%"
            }
        }

        stage('Deploy') {
            when {
                branch 'main'
            }
            steps {
                bat "echo Deploying %APP_NAME% from MAIN branch"
            }
        }
    }

    post {
        always {
            echo "Pipeline finished for branch: ${env.BRANCH_NAME}"
        }
    }
}
