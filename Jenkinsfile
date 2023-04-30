pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        sh 'echo "Building the code"'
      }
    }
    stage('Test') {
      steps {
        sh 'echo "Running the tests"'
      }
    }
    stage('Lint') {
      steps {
        sh 'npx eslint .'
      }
    }
    stage('Deploy') {
      steps {
        sh 'echo "Deploying the code"'
      }
    }
  }
}
