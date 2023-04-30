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
        bat 'C:\\Users\\lenovo\\AppData\\Roaming\\npm\\npx.cmd eslint .'
      }
    }
    stage('Deploy') {
      steps {
        bat 'echo "Deploying the code"'
      }
    }
  }
}
