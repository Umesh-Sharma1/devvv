pipeline {
    agent any

    tools {
        maven 'Maven'
        jdk 'Java'
        sonarqube 'SonarQube'
    }

    stages {
        stage('Checkout') {
            steps {
                checkout scm
            }
        }

        stage('Build') {
            steps {
                bat 'mvn clean install'
            }
        }

        stage('SonarQube Analysis') {
            environment {
                scannerHome = tool 'SonarQube'
            }
            steps {
                bat "${scannerHome}/bin/sonar-scanner"
            }
        }
    }

    post {
        always {
            junit 'target/surefire-reports/**/*.xml'
        }
    }
}
