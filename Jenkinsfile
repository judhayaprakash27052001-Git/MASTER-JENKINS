pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                 echo 'Building application'
            }
        }

        stage('Test') {
            steps {
                 echo 'test application'
            }
        }

        stage('Deploy') {
            when {
                branch 'main'
            }
            steps {
                 echo 'successfully application'
            }
        }
    }
}
