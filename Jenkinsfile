pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                build()
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
