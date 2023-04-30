pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        bat 'echo "Building the code"'
      }
    }
    stage('Test') {
      steps {
        bat 'echo "Running the tests"'
      }
    }
    stage('Lint') {
      steps {
        bat 'npx eslint .'
      }
    }
    stage('Deploy') {
      steps {
        bat 'echo "Deploying the code"'
      }
    }
  }
}
