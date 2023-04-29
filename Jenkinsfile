pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        sh 'git clone <repository-url>'
        sh 'mvn clean compile'
      }
    }
    stage('Test') {
      steps {
        sh 'mvn test'
      }
    }
    stage('Deploy') {
      steps {
        sh 'ssh user@server "cd /path/to/deploy && git pull && mvn clean install"'
      }
    }
  }
  post {
    failure {
      echo 'One of the stages failed!'
      mail to: 'team@example.com', subject: 'Pipeline Failed'
    }
  }
}
