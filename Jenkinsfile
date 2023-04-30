pipeline {
  agent any
  tools {
    nodejs "node"
  }
  stages {
    stage('Build') {
      steps {
        sh 'echo "Building the code"'
      }
    }
    stage('Test') {
      steps {
        sh 'echo "Running ESLint"'
        sh 'npm install eslint --save-dev'
        sh 'eslint --ext .js,.jsx src/'
        recordIssues tool: warningsNg(), 
          aggregatingResults: true, 
          forensicsLimit: 50, 
          healthy: '', 
          unHealthy: '', 
          sourceCodeEncoding: 'UTF-8'
      }
    }
    stage('Deploy') {
      steps {
        sh 'echo "Deploying the code"'
      }
    }
  }
}

