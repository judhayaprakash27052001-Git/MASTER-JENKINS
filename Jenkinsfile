pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                build("build")
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
                deploy()
            }
        }
    }
}
