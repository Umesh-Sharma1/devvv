pipeline {
    agent any
    stages {
        stage('Checkout') {
            steps {
                checkout scm
            }
        }
        stage('Build') {
            steps {
                sh 'echo "Build step"'
            }
        }
        stage('Test') {
            steps {
                sh 'echo "Test step"'
            }
        }
        stage('Lint') {
            steps {
                sh 'echo "Lint step"'
            }
        }
        stage('Deploy') {
            steps {
                sh 'echo "Deploy step"'
            }
        }
    }
}
