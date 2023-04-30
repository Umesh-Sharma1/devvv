pipeline {
  agent any
  tools {
    gradle 'Gradle'
  }
  stages {
    stage('Build') {
      steps {
        bat 'gradle.bat build'
      }
    }
    stage('Test') {
      steps {
        bat 'gradle.bat test'
      }
    }
    stage('Deploy') {
      steps {
        bat 'gradle.bat deploy'
      }
    }   
  }
}
