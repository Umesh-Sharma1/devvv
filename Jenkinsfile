pipeline {
    agent any

    environment {
        APP_NAME = 'my-app'
        DOCKER_REGISTRY = 'my-registry.com'
    }

    stages {
        stage('Build') {
            steps {
                sh 'mvn clean install'
            }
        }

        stage('Test') {
            steps {
                sh 'mvn test'
            }
        }

        stage('Dockerize') {
            steps {
                sh 'docker build -t $DOCKER_REGISTRY/$APP_NAME .'
                sh 'docker push $DOCKER_REGISTRY/$APP_NAME'
            }
        }

        stage('Deploy') {
            steps {
                
                sh 'ssh user@server "docker-compose up -d"'
            }
        }
    }

    post {
        always {
            archiveArtifacts 'target/*.jar'
            emailext body: "The build of $APP_NAME is complete.",
                     subject: "Build Status: ${currentBuild.result}",
                     to: 'my-email@example.com'
        }
    }
}
