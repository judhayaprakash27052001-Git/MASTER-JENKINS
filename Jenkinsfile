@Library('shared-lib') _

pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                build("portfolio-app")
            }
        }

        stage('Test') {
            steps {
                test()
            }
        }

        stage('Deploy') {
            when {
                branch 'main'
            }
            steps {
                deploy("production")
            }
        }
    }
}
