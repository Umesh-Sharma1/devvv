pipeline {
    agent any
    environment {
        MVN_HOME = tool name: 'M3', type: 'maven'
    }
    stages {
        stage('Declarative: Checkout SCM') {
            steps {
                checkout scm
            }
        }
        stage('Build') {
            steps {
                sh '${MVN_HOME}/bin/mvn clean package'
            }
        }
        stage('Test') {
            steps {
                sh '${MVN_HOME}/bin/mvn test'
            }
        }
        stage('Lint') {
            steps {
                sh 'npm install'
                sh 'npm run lint'
            }
        }
        stage('Deploy') {
            steps {
                sh 'ssh user@server "cd /path/to/app && git pull && pm2 restart app"'
            }
        }
    }
}
